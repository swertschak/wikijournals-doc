****************************************************
Einrichtung Elastic Search für Mediawiki (Ubuntu 18)
****************************************************

===========================
Installation Elastic Search
===========================

**Step 1: Import Elasticsearch GPG Key**

.. code-block::

   wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -

**Step 2: Add Elasticsearch 5.x APT repository**

.. code-block::

   echo "deb https://artifacts.elastic.co/packages/5.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-5.x.list

**Step 3: Install OpenJDK**

.. code-block::

   sudo apt update && sudo apt upgrade
   sudo apt install apt-transport-https uuid-runtime pwgen openjdk-8-jre-headless

**Step 4: Update apt package index ans Install Elasticsearch 5.x**

.. code-block::

   sudo apt update
   sudo apt install elasticsearch

**Step 5: First Configuration of Elasticsearch**

Open config file /etc/elasticsearch/elasticsearch.yml
Set correct cluster name for your application:

.. code-block::

   cluster.name: my-application

Default minimum memory set for JVM is 2gb, if your server has small memory size, change this value:

.. code-block::

   sudo nano /etc/elasticsearch/jvm.options

Change

.. code-block::

   -Xms2g
   -Xms2g

to

.. code-block::

   -Xms512m
   -Xms512m

After modification of the configuration, Elasticsearch can be started:

.. code-block::

    sudo systemctl daemon-reload
    sudo systemctl enable elasticsearch.service
    sudo systemctl restart elasticsearch.service

Check status:

.. code-block::

    sudo systemctl status elasticsearch.service


========================
Installation of Elastica
========================

see https://www.mediawiki.org/wiki/Extension:CirrusSearch#Elastica

============================
Installation of CirrusSearch
============================

**Requirements**

* ElasticSearch
* Curl
* php-curl

see https://www.mediawiki.org/wiki/Extension:CirrusSearch#CirrusSearch


=============================
Configuration of CirrusSearch
=============================

see https://www.mediawiki.org/wiki/Extension:CirrusSearch#Configuration
