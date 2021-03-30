# bsdiff-bspatch

`bsdiff` and `bspatch` are a pair of tools for building and applying patches to binary files. Originally created by **Colin Percival**.

This repo is a somewhat maintained forks of bsdiff and bspatch utilities (with a few pre-built binaries for less mainstream platforms).

## License, Credits and attribution

Original author: Colin Percival. <br>
Original paper: [Naïve Differences of Executable Code.](http://www.daemonology.net/papers/bsdiff.pdf) <br>
Author's website: http://www.daemonology.net/bsdiff/.

LICENSE: [BSD 2-clause](LICENSE)

Repo maintainer: [Sayem Shafayet](https://github.com/iShafayet)

## Compiling

**Linux**: Kernel 2.6.23 or above is required. <br>
**MacOS**: Build error regarding `u_char`/`<uchar.h>` not supported. <br>
**BSD**: Not tested, but should work as expected as it was the original target. <br>
**Windows**: Not tested yet.

You will need a C compiler. Following is an example with `gcc` for Amazon Linux 2.

```sh
sudo yum groupinstall "Development Tools"
```

Then simply run in the repo's root directory.
```sh
make
```

## Usage

### Generating patch

```sh
bsdiff oldfile newfile patchfile
```
This will compare `newfile` with `oldfile` and store the patch in `patchfile`.

`patchfile` wll be overwritten if already exists.

### Applying patch

```sh
bspatch oldfile newfile patchfile
```
This will apply patch in `patchfile` on top of `oldfile` and will create `newfile`.

`newfile` wll be overwritten if already exists.

