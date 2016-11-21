# DHCP config for Anonymity Distribution Gateways #

Prevents DHCP from modifications of /etc/resolv.conf by shipping a
configuration file.

In context of Anonymity Distribution Gateways, it is useful to obtain network
configuration for the interface to connect to the internet from a virtual
machine or hardware router to avoid usability issues with manual static
network configuration. At the same time, Anonymity Distribution Gateways
usually do not need a functional system DNS resolver (/etc/resolv.conf),
pointing to a clearnet DNS resolver, because ideally all the Gateway's traffic
including its own DNS is routed through the anonymity network as well.

Usually the Gateway's firewall should ensure, that the Gateway will not leak
it's own DNS requests. However, preventing DHCP from setting /etc/resolv.conf
to a functional clearnet DNS resolver is useful as defense in depth. Also in
case the Gateways system DNS resolver points to the anonymizer, it is crucial,
that it does not get modified by DHCP.

(This package description has been [automatically](https://github.com/Whonix/whonix-developer-meta-files/blob/master/debug-steps/packaging-helper-script) extracted and mirrored from `debian/control`.)

# Generic Readme #
## Readme Version ##

[Generic Readme](https://github.com/Whonix/whonix-developer-meta-files/blob/master/README_generic.md) Version 0.3

## Cooperating Anonymity Distributions ##

[Generic Readme](https://github.com/Whonix/whonix-developer-meta-files/blob/master/README_generic.md) beings here. Have a look into the `man` sub folder (if available).

The functionality of this package was once exclusively available in the [Whonix](https://www.whonix.org) ([github](https://github.com/Whonix/Whonix)) anonymity distribution.

Because multiple projects and individuals stated interest in various of Whonix's functionality (examples: [Qubes OS](http://qubes-os.org/trac) ([discussion](https://groups.google.com/forum/#!topic/qubes-devel/jxr89--oGs0)); [piratelinux](https://github.com/piratelinux) ([discussion](https://github.com/adrelanos/VPN-Firewall/commit/6147f0e606377f5a801e98daf22e24ba2c750a21#commitcomment-6360713))), it's best to share as much source code as possible, it's best to share certain characteristics [(such as /etc/hostname etc.) among all anonymity distributions](https://mailman.boum.org/pipermail/tails-dev/2013-January/002457.html)) Whonix has been split into [multiple separate packages](https://github.com/Whonix).

## Generic Packaging ##

Files in `etc/...` in root source folder will be installed to `/etc/...`, files in `usr/...` will be installed to `/usr/...` and so forth. This should make renaming, moving files around, packaging, etc. very simple. Packaging of most packages looks very similar.

## How to use outside of Debian or derivatives ##

Although probably due to generic packaging not very hard. Still, this requires developer skills. [Ports](https://en.wikipedia.org/wiki/Porting) welcome!

## How to Build deb Package ##

See comments below and [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

* Replace `apparmor-profile-torbrowser` with the actual name of this package (equals the root source folder name of this package after you git cloned it).
* You only need [config-package-dev](https://packages.debian.org/wheezy/config-package-dev), when it is listed in the `Build-Depends:` field in `debian/control`.
* Many packages do not have signed git tags yet. You may request them if desired.
* We might later use a [documentation template](https://www.whonix.org/wiki/Template:Build_Documentation_Build_Package).

## How to install in Debian using apt-get ##

Binary packages are available in Whonix's APT repository. By no means you are required to use the binary version of this package. This might be interesting for users of Debian and derivatives. **Note, that usage of this package outside of Whonix is untested and there is no maintainer that supports this use case.**

1\. Get [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

2\. Add Whonix's Signing Key to apt-key.

```
gpg --export 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA | sudo apt-key add -
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org jessie main" > /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install this package. Replace `package-name` with the actual name of this package.

```
sudo apt-get install package-name
```

## Cooperation ##

Most welcome. [Ports](https://en.wikipedia.org/wiki/Porting), distribution maintainers, developers, patches, forks, testers, comments, etc. all welcome.

## Contact ##

* Professional Support: https://www.whonix.org/wiki/Support#Professional_Support
* Free Forum Support: https://www.whonix.org/forum
* Github Issues
* twitter: https://twitter.com/Whonix

## Donate ##

* [Donate](https://www.whonix.org/wiki/Donate)
