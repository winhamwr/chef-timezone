# DESCRIPTION

This cookbook uses the `tzdata` package to update your system timezone.

It is only tested on Debian/Ubuntu, but would be easy to adapt and pull
requests are welcome.

# REQUIREMENTS

Requires the opscode `system_packages` cookbook to enable installation
of the `tzdata` package.

# ATTRIBUTES

* `timezone[:timezone]`- The name of the timezone to configure. Eg. `America/New_York`.
  This value will be used as your `/etc/timezone` and the corresponding zoneinfo file
  will be symlinked to your `/etc/localtime`.
  Default: `UTC`
* `timezone[:zoneinfo_dir]`- Directory containing the tree of zoneinfo files.
  Default: `/usr/share/zoneinfo/`, which is the `tzdata` package default.

# USAGE

## 'default' recipe

Installs the `tzdata` package and updates the timezone using
`dpkg-reconfigure tzdata` if needed.

