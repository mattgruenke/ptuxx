# ![Boleo](img/Boleo_logo.png)

Boleo is an *unofficial* C++ utility library, for use with the C interface of
Google's Project Tango.  It was written with the objective of making the C
interface easier and safer to use, especially in conjunction with useful C++
standard library facilities and select 3rd party libraries (OpenCV and PCL).


## Features ##

Function templates are provided for accessing TangoConfig entries, featuring:

* Compile-time type safety
* Exception-based error handling


Error handling utilities:

* TangoException is derived from std::system_error, in order to facilitate 
  propagation of API errors via exceptions.
* TangoErrorCategory facilitates error message lookup, within the context of
  exception handling.
* ThrowError() and ThrowIfError() wrap TangoErrorType error codes in
  TangoExceptions and throw.
* BOLEO_THROW_IF_ERROR() wraps ThrowIfError(), using the parameter as the error
  description (similar to assert()).
* SafeCall() trampoline functions provide convenient last-resort exception
  handling.


Point Cloud Library interoperability:

* Conversion from TangoPointCloud to pcl::PointCloud< T >.


## Documentation ##

API documentation is provided via doxygen.  If you have it installed, build the
'doc' target.  You'll find the results in doc/html/ of the build area.  During
installation, these are copied to ${CMAKE_INSTALL_PREFIX}/share/doc/boleo/html/.

Otherwise, you can download the docs package from the
[releases](https://github.com/mattgruenke/boleo/releases) section of the Github
page.


### Header Files ###

Details are distributed among the respective header files, with usage examples
often appearing in the file descriptions, themselves.  The public header files
are:

* exceptions.hpp - exception class & utilities for TangoErrors.
* safe_call.hpp - exception-handling support for JNI methods.
* config.hpp - utilities for working with TangoConfig.
* pcl.hpp - interoperability with Point Cloud Library.


## License ##

Distributed under the Boost Software License, Version 1.0.
See accompanying file LICENSE_1_0.txt or copy at <http://www.boost.org/LICENSE_1_0.txt>


## API Stability ##

Everything prior to v1.0 is subject to change.  After that, only a recompile
should be needed to upgrade user code to new releases with the same major
revision.

Since this is intended to be distributed with your app, no guarantees are made
about binary compatibility, between any two releases.


## More Information ##

The current home of this library is <https://github.com/mattgruenke/boleo>

For more on Google's Project Tango, see <https://developers.google.com/tango/>

