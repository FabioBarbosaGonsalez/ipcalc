About
=====


The ipcalc module provides tools for IP address manipulation and calculation,
allowing operations such as iterating over hosts, checking network membership,
calculating netmasks, and converting addresses to integers.

Classes:
    IP: Represents an IP address (IPv4 or IPv6).
    Network: Represents an IP network, supporting iteration and membership tests.

Example:
   
    >>> import ipcalc
    >>> for x in ipcalc.Network('172.16.42.0/30'):
    ...     print(str(x))
    ...
    172.16.42.1
    172.16.42.2

    >>> subnet = ipcalc.Network('2001:beef:babe::/48')
    >>> print(str(subnet.network()))
    2001:beef:babe:0000:0000:0000:0000:0000
    >>> print(str(subnet.netmask()))
    ffff:ffff:ffff:0000:0000:0000:0000:0000

    >>> '192.168.42.23' in ipcalc.Network('192.168.42.0/24')
    True

    >>> int(ipcalc.IP('fe80::213:ceff:fee8:c937'))
    338288524927261089654168587652869703991

Args:
    address (str): The IP address or network in CIDR notation.
    version (int, optional): The IP version (4 or 6). Defaults to auto-detection.

Returns:
    Network or IP object depending on the class initialized.

Raises:
    ValueError: If the provided address is invalid.
    TypeError: If an unsupported argument type is passed.




Bugs/Features
=============

You can issue a ticket in GitHub: https://github.com/tehmaze/ipcalc/issues

[![Build Status](https://travis-ci.org/tehmaze/ipcalc.svg?branch=master)](https://travis-ci.org/tehmaze/ipcalc)
[![Code Health](https://landscape.io/github/tehmaze/ipcalc/master/landscape.svg)](https://landscape.io/github/tehmaze/ipcalc/master)
