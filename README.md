# EECS 281 Makefile

A Makefile for EECS 281 projects that supports compilation, submission
tarball creation, sync to CAEN Linux, and more. This file is parameterized
and requires a student uniqname, and a project identifier and the name of the
executable produced (as provided from a project spec). Optional parameters
allow the specification of the filename where `main()` can be found, and the
custom naming of the directory where files can be synchronized on CAEN for
testing.

Since the primary usage of `Makefile` by students is during the development
cycle, the first or default `make` target is `debug`, so the following
commands are equivalent, and both create a file named `<executable>_debug`:

```
$ make
...creates <executable>_debug
$ make debug
...creates <executable>_debug
```

Also included in this project is `server-Makefile`, a parameterized version
of the Makefile used by the EECS 281 autograder (AG). This provides two
targets that are used when grading student submissions:

- `release`: A speed optimized build that is used for correctness, timing,
  and memory usage grading; creates a file named `<executable>`, as defined
  in the Makefile
- `debug`: A similar build that also includes the maximum amount of debug
  symbols for use by valgrind on the AG, if the release build terminates
  abnormally; creates a file named `<executable>_debug`, as defined in the
  Makefile

See [this video](https://www.youtube.com/watch?v=n-ZmFjCp1QY) for information on how to use the Makefile.

## Quick Start

Download into the directory containing your project source code.

```console
$ wget https://raw.githubusercontent.com/eecs281staff/Makefile/main/Makefile
Downloads `Makefile` to your current directory, overwriting any existing file...
```

Edit these lines in the Makefile.  Your values might be different, check the project spec for required file names.

```make
UNIQNAME = not_awdeorio
# ...
IDENTIFIER  = copy_me_from_project_spec
# ...
EXECUTABLE = main
# ...
PROJECTFILE = main.cpp
```

**Shortcut:** You can skip updating `PROJECTFILE` if your `main()` function is in one of these filenames: `main.cpp`, `project0.cpp`, `project1.cpp`, `project2.cpp`, `project3.cpp`, `project4.cpp`, or `<EXECUTABLE>.cpp`.

If your project has additional dependencies, update the dependencies section at the bottom of the `Makefile`.

You should be able to compile and run your main file.

```console
$ make
$ ./main_debug
hello world!
```

## More Information

```console
$ make help
EECS281 Advanced Makefile Help
...
```
