# EECS 281 Makefile

A Makefile for EECS 281 projects that supports compilation, submission tarball creation, sync to CAEN Linux, and more.

See [this video](https://www.youtube.com/watch?v=n-ZmFjCp1QY) for information on how to use the Makefile.

## Quick Start
Download into the directory containing your project source code.
```console
$ wget https://raw.githubusercontent.com/eecs281staff/Makefile/main/Makefile
```

Edit these lines in the Makefile.  Your values might be different, check the project spec for required file names.
```make
UNIQNAME = not_awdeorio
# ...
IDENTIFIER  = copy_me_from_project_spec
# ...
PROJECTFILE = main.cpp
# ...
EXECUTABLE = main
```

**Shortcut:** You can skip updating `PROJECTFILE` if your `main()` function is in one of these filenames: `main.cpp`, `project0.cpp`, `project1.cpp`, `project2.cpp`, `project3.cpp`, `project4.cpp`, or `<EXECUTABLE>.cpp`.

If your project has additional dependencies, update the dependencies section at the bottom of the `Makefile`.

You should be able to compile and run your main file.
```console
$ make
$ ./main
hello world!
```

## More
```console
$ make help
```
