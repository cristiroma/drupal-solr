# Apache Solr customized for Drupal site

This Apache Solr 4.x distribution has been customized to work out of the box with a Drupal 7 installation. Contains the schema distributed with the search_api_solr module

# How to use it

1. Download one of the releases
2. Unpack and run ./start within the directory

Visit the Apache Solr administration interface @ http://localhost:8983/solr. 

# Notes

1. This is a multi-core setup. By default core0 is available.
2. To create an additional core, copy core0 to another directory and edit NEWCORE/core.properties to assign a name to the core (directory name) and restart the container
3. To change default Jetty port, edit ``start`` shell script and adjust the jetty.port to the desired value
