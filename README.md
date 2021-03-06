# GeoIP API for Go

This package wraps the [libgeoip C library](http://www.maxmind.com/app/c) for
access from Go (golang). [![Build Status](https://travis-ci.org/abh/geoip.png?branch=master)](https://travis-ci.org/abh/geoip)

Install with `go get github.com/abh/geoip` and use [godoc
geoip](http://godoc.org/github.com/abh/geoip) to read the documentation.

There's a small example in the `ex/` subdirectory.

You can download the free [GeoLite
Country](http://www.maxmind.com/app/geoip_country) database or you can
[subscribe to updates](http://www.maxmind.com/app/country).

The package is compatible with Go 1.3 and 1.4. Older versions work
with older versions of Go.

## Examples

	file := "/usr/share/GeoIP/GeoIP.dat"

	gi, err := geoip.Open(file)
	if err != nil {
		fmt.Printf("Could not open GeoIP database\n")
	}

	if gi != nil {
		country, netmask := gi.GetCountry("207.171.7.51")
	}

	// Setup gi6 by opening the optional IPv6 database and then...
	country := gi6.GetCountry("2607:f238:2::5")
	fmt.Println(country)


## Contact

Copyright 2012-2015 Ask Bjørn Hansen <ask@develooper.com>. The package
is MIT licensed, see the LICENSE file. Originally based on example code
from blasux@blasux.ru.
