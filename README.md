#osmbox

The main purposed of this box is to create an environment that makes it easy to create historical mapping tiles in OpenStreetMap.

#####The final vagrant box is on [ATLAS](https://atlas.hashicorp.com/omnitom/boxes/osmbox) and is named omnitom/osmbox
#####Install Vagrant and see [Getting Started](http://docs.vagrantup.com/v2/getting-started/index.html) example:
```Batchfile
$ vagrant init omnitom/osmbox
$ vagrant up
```



Three different packer templates are meant to be run in order. This is done so new features can be added in an incremental fashion.

-install packer
-packer build osmbox-step1-install-os.json

This will output a osmbox-step1 .ovf and .vmdk file in the newly created output-virtualbox-iso directory

-packer build osmbox-step2-install-software.json

This will output a .ovf file in the newly created output-virtualbox-ovf directory

-re-name the output-virtualbox-ovf directory output-virtualbox-ovf2

-packer build osmbox-step3-configure-system.json

The final .ovf file will be inside the output-virtualbox-ovf directory. The final Vagrant box file will be inside the step3-box directory.

##What's installed

-ubuntu 12.04 desktop (credit to: https://github.com/boxcutter/ubuntu)

###system_packages:
  - build-essential
  - git
  - libevent-dev
  - nginx
  - python-setuptools
  - clang 
  - python-software-properties 
  - whois
  - python-gdal 
  - python-mapnik2 
  - python-pyproj
  - python-dev 
  - libpq-dev
  - python-virtualenv
  - libgdal1h
  - libgdal-dev
  - make
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
  - vim
  - unzip
  - python-dateutil
  - graphicsmagick
  - doxygen
  - graphviz
  - pgadmin3
  - libosmpbf-dev
  - osm2pgsql
  - tilemill 
  - libmapnik 
  - nodejs 
  - gdal-bin
  - mapnik-utils
  - qgis
  - django
  - psycopg2

  ###repos:

  - osmium
  - osm-history-splitter
  - openstreetmap-carto

  ###Ubuntu Personal Package Archives (PPAs):

  - ubuntugis/ppa
  - kakrueger/osm-unstable
  - developmentseed/mapbox

