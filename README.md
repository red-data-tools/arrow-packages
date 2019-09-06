# README

https://packages.red-data-tools.org/ provides packages for Red Data
Tools related projects including Apache Arrow and Apache Parquet.

## Supported packages

  * OpenCV GLib (C API)

## Supported platforms

There are packages for the following platforms:

  * Debian GNU/Linux buster
  * Ubuntu 18.04 LTS
  * Ubuntu 19.04

## Package repository

https://packages.red-data-tools.org/ provides packages. You need to
enable the package repository before you install packages.

### Debian GNU/Linux

Install `apt-transport-https` to support HTTPS APT repository:

```console
% sudo apt install -y -V apt-transport-https
```

Run the following command lines to add apt-lines for APT repository on
packages.red-data-tools.org:

```console
% sudo apt install -y -V lsb-release wget
% sudo wget -O /usr/share/keyrings/red-data-tools-keyring.gpg https://packages.red-data-tools.org/$(lsb_release --id --short | tr 'A-Z' 'a-z')/red-data-tools-keyring.gpg
% sudo tee /etc/apt/sources.list.d/red-data-tools.list <<APT_LINE
deb [signed-by=/usr/share/keyrings/red-data-tools-keyring.gpg] https://packages.red-data-tools.org/$(lsb_release --id --short | tr 'A-Z' 'a-z')/ $(lsb_release --codename --short) main
deb-src [signed-by=/usr/share/keyrings/red-data-tools-keyring.gpg] https://packages.red-data-tools.org/$(lsb_release --id --short | tr 'A-Z' 'a-z')/ $(lsb_release --codename --short) main
APT_LINE
% sudo apt update
```

### Ubuntu

Install `apt-transport-https` to support HTTPS APT repository:

```console
% sudo apt install -y -V apt-transport-https
```

Run the following command lines to add apt-lines for APT repository on
packages.red-data-tools.org:

```console
% sudo apt install -y -V lsb-release
% sudo wget -O /usr/share/keyrings/red-data-tools-keyring.gpg https://packages.red-data-tools.org/$(lsb_release --id --short | tr 'A-Z' 'a-z')/red-data-tools-keyring.gpg
% sudo tee /etc/apt/sources.list.d/red-data-tools.list <<APT_LINE
deb [signed-by=/usr/share/keyrings/red-data-tools-keyring.gpg] https://packages.red-data-tools.org/$(lsb_release --id --short | tr 'A-Z' 'a-z')/ $(lsb_release --codename --short) universe
deb-src [signed-by=/usr/share/keyrings/red-data-tools-keyring.gpg] https://packages.red-data-tools.org/$(lsb_release --id --short | tr 'A-Z' 'a-z')/ $(lsb_release --codename --short) universe
APT_LINE
% sudo apt update
```

### CentOS

```console
% sudo yum install -y https://packages.red-data-tools.org/centos/red-data-tools-release-latest.noarch.rpm
```

## OpenCV GLib

This section describes how to install
[OpenCV GLib](https://github.com/red-data-tools/opencv-glib) package.

### Debian GNU/Linux

```console
% sudo apt install -y -V libopencv-glib-dev
```

### Ubuntu

```console
% sudo apt install -y -V libopencv-glib-dev
```

## For packages.red-data-tools.org administrator

### How to deploy

```console
% sudo apt install -V ansible
% rake deploy
```

## For package creators

### Debian GNU/Linux and Ubuntu

Here are command lines to build .deb files and update APT repository:

```console
% git submodule update --init
% rake apt
```

### CentOS

Here are command lines to build .rpm files and update Yum repository:

```console
% git submodule update --init
% rake yum
```

## License

Apache-2.0

Copyright 2017-2019 Kouhei Sutou \<kou@clear-code.com\>

See LICENSE and NOTICE for details.
