# wjbtools
Assorted scripts for managing Gentoo systems.

## portage-rebuild
```
usage: portage-rebuild [-h] [-c COUNT] [-a] [-p] [-m AGE] [-A ADDPACKAGES]
                       [--local LOCALPACKAGES] [-R DELPACKAGES] [-s] [-L] [-P]
                       [-N]

Rebuild the oldest installed packages

options:
  -h, --help            show this help message and exit
  -c COUNT, --count COUNT
                        The number of packages to find and build, default 50.
  -a, --ask             Whether to do emerge --ask
  -p, --pretend         Do not run emerge, just list what would be merged.
  -m AGE, --months AGE  Build packages which are this age (months) or older
  -A ADDPACKAGES, --add ADDPACKAGES
                        Package name to add to the ignored list. May be
                        repeated.
  --local LOCALPACKAGES
                        Package name to add to the local ignore list. These
                        packages are not rebuilt while in pump mode - usually
                        want to specify packages which do not build
                        successfully in pump mode. May be repeated.
  -R DELPACKAGES, --remove DELPACKAGES
                        Package name to delete from the ignored list. May be
                        repeated.
  -s, --strip-versions  Strip version numbers, i.e. ignore the version numbers
                        of the installed packages and just build the current
                        ones. For those rare occasions when portage thinks an
                        obsolete version of a package will do.
  -L, --list            List the ignored packages
  -P, --pump            Compile in pump mode from now. Should be enabled on
                        distcc clients.
  -N, --normal          Compile in normal mode from now, i.e. not pump mode.
                        If this PC is not a distcc client.
```
## purge-distfiles
```
usage: purge-distfiles [-h] [--purge] [--verbose]

Purge unused files from a shared distfiles directory. Run the command from
each PC to generate the list of distfiles that it uses. The list files, named
after the PC, are saved under the distfiles directory. Run the command using
the --purge option from one of the PCs to remove any distfiles not needed by
any PC.

options:
  -h, --help     show this help message and exit
  --purge        Purge all unused dist files. When not set, generate the in-
                 use distfile list for this PC.
  --verbose, -v  Print the list of files that will be removed.
```
## splot
```
usage: splot [-h] [-t SHOWPKG] [-l LIMIT] [-r]

List emerge times for current or specific package

options:
  -h, --help            show this help message and exit
  -t SHOWPKG, --time SHOWPKG
                        report the emerge times for the given package
  -l LIMIT, --limit LIMIT
                        limit the number of events to be listed
  -r, --remaining       Show the list of remaining builds
```
