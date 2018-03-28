# ipfs-dist-install

> install distributions from https://dist.ipfs.io

This shell script installs binaries from https://dist.ipfs.io. It is not safe, as it trusts the website to provide the right files. A better version would check hashes or signatures. It is not efficient, as it always re-downloads. A better version would download through a local ipfs node, and therefore avoid downloading the same content multiple times.

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Examples](#examples)
- [Contribute](#contribute)
- [License](#license)

## Install

```sh
wget -q https://raw.githubusercontent.com/jbenet/ipfs-dist-install/master/ipfs-dist-install
chmod +x ipfs-dist-install
mv ipfs-dist-install /usr/local/bin/ipfs-dist-install
ipfs-dist-install
```

## Usage

```sh
USAGE
  ipfs-dist-install <program> [<version>] [<install-path>]
  installs a given program binary at a local install path

  <version>         should be a version as used in https://dist.ipfs.io
                    if empty, use latest available semver release
  <install-path>    should be a local file system path
                    if empty, use /usr/local/bin

OPTIONS
  -h, --help        print usage information
  -v, --verbose     print execution log
  -l, --list        list available versions for <program>

EXAMPLES
  # install latest ipfs-cluster-service release
  > ipfs-dist-install ipfs-cluster-service
  installed /usr/local/bin/ipfs-cluster-service (v0.3.4)

  # show all versions for gx
  > ipfs-dist-install gx --list
  v0.6.0
  v0.7.0
  v0.8.0
  v0.8.0
  v0.9.0
  v0.10.0
  v0.11.0
  v0.11.0
  v0.12.0
  v0.12.1

  # install latest rc for gx-go ipfs-cluster-ctl
  > ipfs-dist-install ipfs-cluster-ctl v0.3.5-rc1
  installed /usr/local/bin/ipfs-cluster-ctl (v0.3.5-rc1)

CONTRIBUTE
  Please file issues, pull-requests, and more at https://github.com/jbenet/ipfs-dist-install
```

## Contribute

Feel free to join in. All welcome. Open an [issue](https://github.com/ipfs/install-go-ipfs/issues)!

This repository falls under the IPFS [Code of Conduct](https://github.com/ipfs/community/blob/master/code-of-conduct.md).

### Want to hack on IPFS?

[![](https://cdn.rawgit.com/jbenet/contribute-ipfs-gif/master/img/contribute.gif)](https://github.com/ipfs/community/blob/master/contributing.md)

## License

MIT
