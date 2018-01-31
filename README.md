**This project has been deprecated in favor of https://github.com/cristiroma/local-development-stack**

# Apache Solr customized for Drupal site

This Apache Solr 4.x distribution has been customized to work out of the box with a Drupal 7 installation. Contains the schema distributed with the search_api_solr module

# How to use it

1. Download one of the releases
2. Unpack and run ./start within the directory

Visit the Apache Solr administration interface @ http://localhost:8983/solr

# Notes

1. This is a multi-core setup. By default core0 is available
2. To create an additional core, copy core0 to another directory and edit NEWCORE/core.properties to assign a name to the core (directory name) and restart the container
3. To change default Jetty port, edit ``start`` shell script and adjust the ``-Djetty.port`` option to the desired value



# Production deployment guidelines no-brainer

Security considerations

1. Create a special system daemon account
	``sudo useradd -r -s /bin/false java``

2. All the directories must be owned by root:root
	``chown -R root:root drupal-solr/``

3. Make only the following directories writable by the 'java; account
	``
	chown -R java:java drupal-solr/logs
	chown -R java:java drupal-solr/tmp
	chown -R java:java drupal-solr/cores/core0/data
	``

Do the last line for each core.

4. Disable access to http://localhost:8983/ from outside - Solr by default has no security configured!
