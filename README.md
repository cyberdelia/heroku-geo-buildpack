Heroku buildpack: geo
=====================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that
vendors main geo/gis libraries like geos, proj and gdal.

You will use this buildpack with other major buildpack such as Ruby buildpack.

Usage
-----

Example usage:

```
$ heroku buildpacks:set https://github.com/cyberdelia/heroku-geo-buildpack.git
$ heroku buildpacks:add heroku/ruby
```

Run `heroku buildpacks` to make sure that `heroku-geo-buildpack` is added before
the language buildpacks.

```
$ heroku buildpacks
=== sushi Buildpack URLs
1. https://github.com/cyberdelia/heroku-geo-buildpack.git
2. heroku/ruby
```

Testing
-------

For Geo Django:

```python
>>> from django.contrib.gis import gdal
>>> gdal.HAS_GDAL
True
```

For rgeo:

```ruby
>>> require 'rgeo'
>>> RGeo::CoordSys::Proj4.supported?
=> true
>>> RGeo::Geos.supported?
=> true
```
