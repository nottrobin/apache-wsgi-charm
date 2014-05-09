Apache WSGI charm
==

This is a [Juju](https://juju.ubuntu.com/) [charm](https://juju.ubuntu.com/charms/) for setting up an [Apache](http://httpd.apache.org/) [mod_wsgi](http://modwsgi.readthedocs.org/en/latest/) server for a basic [Python](https://www.python.org/) [WSGI](http://wsgi.readthedocs.org/en/latest/) app.

Usage
---

Hopefully, this charm will eventually be included in the [Juju charm repository](https://jujucharms.com/), so you can use it with simply `juju deploy apache-wsgi`, but for now you'll need to clone it to use it:

### Cloning

Clone the charm into your `trusty` folder within your charms directory, with the name `django-legal`, e.g.:

``` bash
mkdir -p ~/charms/trusty && cd charms
git clone git@github.com:nottrobin/apache-wsgi-charm.git trusty/apache-wsgi
```

### Preparing

You'll need a zipped tarball of your project for running with the app - e.g. `project.tar.gz`. Then you can include it is a config option:

``` bash
juju set local:trusty/apache-wsgi project_file="$(base64 project.tar.gz)"
juju deploy local:trusty/apache-wsgi
```
