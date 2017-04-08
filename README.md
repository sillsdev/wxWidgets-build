wxWidgets-build
===============

Three scripts are provided:

* `build-and-install`
* `build-branch`
* `install-branch`

`build-and-install` is used to configure and build (or rebuild) *wxWidgets* and install the result in `/opt/wx/VERSION`. Output from the various stages is redirected to files instead of the terminal.

`build-branch` and `install-branch` are used together but allow the building and installation to be done separately. Builds of different source branches are stored in separate subdirectories, and can be reinstalled as needed. Now that the installation prefix in `/opt` includes a version number, it's not usually necessary to use this approach, but if multiple wx source branches are using the same wx version number, it might still be useful, because the build directory name used by `build-and-install` doesn't use the branch name, only the wx version.
