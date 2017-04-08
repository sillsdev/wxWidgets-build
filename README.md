wxWidgets-build
===============

Three scripts are provided:

* `build-and-install`
* `build-branch`
* `install-branch`

`build-and-install` is used to configure and build (or rebuild) *wxWidgets* and install the result in `/opt/wx/VERSION`. Output from the various stages is redirected to files instead of the terminal.

`build-branch` and `install-branch` are used together but allow the building and installation to be done separately. Builds of different source branches are stored in separate subdirectories, and can be reinstalled as needed. Now that the installation prefix in `/opt` includes a version number, it's not usually necessary to use this approach, but if multiple wx source branches are using the same wx version number, it might still be useful, because the build directory name used by `build-and-install` doesn't use the branch name, only the wx version.

The two build scripts take an optional argument specifying the location of the `wxWidgets` source directory. If the script is located in the source directory itself, this parameter can be omitted because it defaults to the current directory. However, it can be useful to have the source and the build scripts in sibling directories:

```
.../wxWidgets/
.../wxWidgets-build/
```

In this case the build scripts would be run with a parameter of `../wxWidgets`.

Additional parameters will be passed directly to `make`, so a parallel build can be accomplished with:

```
./build-and-install ../wxWidgets -j5
```

`install-branch` takes one parameter, the name of the branch (which is also the name of the build directory). If no parameter is given, it attempts to use the name of the currently checked-out branch in `../wxWidgets`.
