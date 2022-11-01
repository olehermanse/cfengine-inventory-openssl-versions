This module adds the inventory attribute _OpenSSL version(s)_, a string list of OpenSSL version numbers found installed on the system.
It looks for OpenSSL in a few different ways:

* Executables:
  * Runs the `openssl version` command
* Package managers:
  * `apt` - uses `apt-cache policy openssl` command
  * `brew` - uses `brew list --versions openssl` command
  * `yum` - uses `yum list installed openssl` command

The inventory attribute can be used in Inventory reports and conditions within Mission Portal:

![](https://raw.githubusercontent.com/olehermanse/cfengine-inventory-openssl-versions/main/inventory-openssl-versions-mp-screenshot.png)

Note that in CFEngine Enterprise, you have software inventory available by default, which takes all software names and version numbers from the chosen package manager (for example `apt`).
Using the module provides an alternative - it looks for OpenSSL in more places, and adds it to _Inventory_, which is not the standard place for installed software versions.
See this blog post for more information:

https://cfengine.com/blog/2022/november-2022-critical-vulnerabilities-in-openssl-3/
