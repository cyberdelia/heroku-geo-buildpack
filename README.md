Heroku buildpack: geo
=====================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that
vendors main geo/gis libraries like geos, proj and gdal.

It is meant to be used in conjunction with other buildpacks as part of a
[multi-buildpack](https://github.com/ddollar/heroku-buildpack-multi).

Usage
-----

Example usage:

    $ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git

    $ cat .buildpacks
    https://github.com/cyberdelia/heroku-geo-buildpack.git#1.1
    https://github.com/heroku/heroku-buildpack-ruby.git#v79


Don't forget to pin buildpack versions you want to use in your .buildpacks file.

Testing
-------

For Geo Django:

>>> from django.contrib.gis import gdal
>>> gdal.HAS_GDAL
True

For rgeo:

>>> require 'rgeo'
>>> RGeo::CoordSys::Proj4.supported?
=> true
>>> RGeo::Geos.supported?
=> true
