#osmbox

The main purposed of this box is to create an environment that makes it easy to create historical mapping tiles in OpenStreetMap.

#####The final vagrant box is on [ATLAS](https://atlas.hashicorp.com/omnitom/boxes/osmbox) and is named omnitom/osmbox
#####Install Vagrant and see [Getting Started](http://docs.vagrantup.com/v2/getting-started/index.html) 
#####example:
```Batchfile
$ vagrant init omnitom/osmbox
$ vagrant up
```
#####Building osmbox yourself:

Three different packer templates are meant to be run in order. This is done so new features can be added in an incremental fashion.

Install [packer](https://www.packer.io/intro/getting-started/setup.html) first. 

-packer build osmbox-step1-install-os.json

This will output a osmbox-step1 .ovf and .vmdk file in the newly created output-virtualbox-iso directory

-packer build osmbox-step2-install-software.json

This will output a .ovf file in the newly created output-virtualbox-ovf directory

-packer build osmbox-step3-configure-system.json

The final .ovf file will be inside the output-virtualbox-ovf3 directory. The final Vagrant box file will be inside the step3-box directory.

##What's installed

-ubuntu 12.04 desktop (credit to: https://github.com/boxcutter/ubuntu)

###system_packages:
  - build-essential
  - git
  - curl
  - make
  - vim
  - unzip
  - nodejs 
  - graphicsmagick
  - libevent-dev
  - nginx
  - clang 
  - whois
  - python-setuptools
  - python-dateutil
  - python-software-properties 
  - python-gdal 
  - python-mapnik2 
  - python-pyproj
  - python-dev 
  - python-imaging
  - python-virtualenv
  - libpq-dev
  - libgdal1h
  - libgdal-dev
  - postgresql-9.1
  - postgresql-9.1-postgis-2.0
  - postgresql-contrib-9.1
  - zlib1g-dev
  - libexpat1
  - libexpat1-dev
  - libxml2
  - libxml2-dev
  - libgeos-dev
  - libgeos++-dev
  - libprotobuf7
  - libprotobuf-dev
  - protobuf-compiler
  - libsparsehash-dev
  - libboost-dev
  - libgdal1-dev
  - libproj-dev
  - subversion
  - doxygen
  - graphviz
  - pgadmin3
  - libosmpbf-dev
  - osm2pgsql
  - tilemill 
  - libmapnik 
  - gdal-bin
  - mapnik-utils
  - qgis
  - openjdk-7-jdk 
  - proj 
  - libprotobuf-c0-dev

  ###repos:

  - osmium
  - osm-history-splitter
  - openstreetmap-carto
  - openstreetmap-history
  - protobuf
  - protobuf-c

  ###openstreetmap-history gemfile installs:

  - mongo 1.11.1
  - bson 1.11.1
  - bson_ext 1.11.1
  - rgeo 0.3.20
  - descriptive_statistics 2.5.1
  - htmlentities 4.3.3
  - jekyll 2.5.3
  - pbf_parser 0.2.0
  - nokogiri 1.6.6.2
  - nori 2.4.0
  - rspec 3.1.0
  - byebug

  ###protobuf and protobuf-c are both compiled and installed

  ###Ubuntu Personal Package Archives (PPAs):

  - ubuntugis/ppa
  - kakrueger/osm-unstable
  - developmentseed/mapbox

