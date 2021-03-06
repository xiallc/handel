Handel 1.1 is built with SCons+swtoolkit. The version requirements of
particular dependencies are not all strict, but the more swtoolkit
ages, the more likely we are to get stuck on a version of SCons. When
in doubt, use the version listed.

1. Install the latest Python27 Windows installer from [python.org] or
   using Chocolately. The x86-64 version is fine on a 64-bit system.
2. Update setup tools:
   python -m pip install -U pip setuptools wheel
3. Install Python requirements: =pip install pyyaml pywin32=
4. Install SCons 2.X. `pip install SCons==2.5.1`. There is also a Windows
   installer. If manually installing from the source release, run
   `python setup.py install --standard-lib`.
5. For hammer.bat (swtoolkit's main script, included in Handel) to
   work, `set SCONS_DIR=c:\python27\lib\site-packages\scons-2.5.1`.

Tests in t_api run with Ruby 2.3+. You will need both x86 and x64
versions of Ruby in order to test both builds of Handel. For each
version, `gem install ffi`.

tools/releaser requires more Ruby gems: tenjin win32-api wrong.

Building with scons
===================

Handel has many flags that map to defines in the compilation environment. A
little experimentation may be needed to get the set that supports only the
products you need.

The incldued bulid script can be used to invoke SCons build environment.

Here's an example for microDXP USB2:

   build --udxp --no-udxps --no-xw --no-serial --no-xmap --no-stj --no-mercury --no-saturn --verbose

Another example to build the examples with default option:

   build --samples

To search for other flags, search "SetBitFromOption" in main.scons.



Resources:

* [python.org](https://www.python.org/downloads/)
* [swtoolkit examples](https://code.google.com/p/swtoolkit/wiki/Examples)
* [swtoolkit glossary](https://code.google.com/p/swtoolkit/wiki/Glossary#COMPONENT_LIBRARY_PUBLISH)
* [SCons manual](http://www.scons.org/doc/production/HTML/scons-man.html)
