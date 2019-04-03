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
## How to install `anon-gw-dhcp-conf` using apt-get ##

1\. Add [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg adv --keyserver hkp://ipv4.pool.sks-keyservers.net:80 --recv-keys 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org buster main" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `anon-gw-dhcp-conf`.

```
sudo apt-get install anon-gw-dhcp-conf
```

## How to Build deb Package ##

Replace `apparmor-profile-torbrowser` with the actual name of this package with `anon-gw-dhcp-conf` and see [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Payments ##

`anon-gw-dhcp-conf` requires [payments](https://www.whonix.org/wiki/Payments) to stay alive!
