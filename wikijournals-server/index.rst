*******************
Wikijournals Server
*******************

===========
Description
===========

Wikijournals-server is a web application, based on Semantic Mediawiki. This application allow collecting articles, publishers, publications and authors in a semantic database. The following functions are available:

* Saving semantic attributes for articles like persons, companies and locations
* Searching for articles, publications, publishers and authors by using semantic attributes
* Basic social network functions for registered users (f.e. user board for sending internal messages)

============
Requirements
============

* Linux Server (for example Ubuntu 18)
* Webserver: Apache > 2.0
* Database: MySQL >= 5.7
* Scripting Language: PHP >= 7.0
* Minimum space on server: 100 MB
* Installed Composer (Dependency Manager for PHP)
* Installed Git
* Existing empty Database in MySQL

=================
Pre-Install Tasks
=================

* Clone wikijournals git repo => git clone https://github.com/swertschak/wikijournals.git
* Create empty database in MySQL (if not exists)
* Note the following database parameters for the installation

    - Database name
    - Database user
    - Database user password


============
Installation
============

Installation per Shell Script
=============================

* Open Terminal
* Change to the wikijournals code directory (the cloned git repo)
* execute command tools/Install_Wikijournals.sh as sudo with the follwing 9 parameters in this order

    - html directory
    - wikijournals directory
    - dbuser
    - dbpass
    - dbserver
    - dbname
    - wikiuser
    - wikipwd
    - wikiname

Sample
------

.. code-block::

   sudo sh tools/Install_Wikijournals.sh /var/www/html wikijournals_3 wikiuser mypassword localhost wikijournals_3 Administrator myadminpasswd wikijournals

.. DANGER::
   Please note: The script Install_Wikijournals.sh must be run under a user, who has write access for the web directory on the server.


Manual Installation
===================

Install Mediawiki
-----------------

* Download current Mediawiki version from mediawiki.org
* Uncompress the mediawiki archive
* Upload the uncompressed archive to the web server f.i. /htdocs/wikijournals
* Ensure access to the web directory including sub-directories for the web user (f.i. www-data)
* For example per chown command: sudo chown -cR www-data:www-data wikijournals
* Perform normal mediawiki installation (see https://www.mediawiki.org/wiki/Manual:Installation_guide)

Install Foreground Theme
------------------------

* Download Foreground (git clone https://github.com/thingles/foreground.git)
* Install Foreground, see https://github.com/thingles/foreground/
* Set Foreground as Default Skin (see https://www.mediawiki.org/wiki/Manual:$wgDefaultSkin)

Install Semantic Mediawiki
--------------------------

* see https://www.semantic-mediawiki.org/wiki/Help:Installation

Install Semantic Extensions
-------------------------------

* `Semantic Compound Queries <https://www.mediawiki.org/wiki/Extension:Semantic_Compound_Queries>`_
* `Semantic Drilldown <https://www.mediawiki.org/wiki/Extension:Semantic_Drilldown>`_
* `Page Forms <https://www.mediawiki.org/wiki/Extension:Page_Forms>`_
* `Semantic Internal Objects <https://www.mediawiki.org/wiki/Extension:Semantic_Internal_Objects>`_
* `Semantic Maps <https://www.mediawiki.org/wiki/Extension:Semantic_Maps>`_
* `Semantic Result Formats <https://www.mediawiki.org/wiki/Extension:Semantic_Result_Formats>`_


Install Mediawiki Extensions
----------------------------

* `Maps <https://www.mediawiki.org/wiki/Extension:Maps>`_
* `Admin Links <https://www.mediawiki.org/wiki/Extension:Admin_Links>`_
* `Data Transfer <https://www.mediawiki.org/wiki/Extension:Data_Transfer>`_
* `External Data <https://www.mediawiki.org/wiki/Extension:External_Data>`_
* `Header Tabs <https://www.mediawiki.org/wiki/Extension:Header_Tabs>`_
* `MyVariables <https://www.mediawiki.org/wiki/Extension:MyVariables>`_
* `Page Schemas <https://www.mediawiki.org/wiki/Extension:Page_Schemas>`_
* `Variables <https://www.mediawiki.org/wiki/Extension:Variables>`_
* `Widgets <https://www.mediawiki.org/wiki/Extension:Widgets>`_

Install Wikijournals Structure
------------------------------

* Open terminal
* Change to wikijournals directory on the web server
* Change to maintenance directory
* Copy wikijournalsStructure.xml from the wikijournals_structure directory to the maintenance dir
* execute php importDump.php < wikijournalsStructure.xml

======
Update
======

Todo: Add update
