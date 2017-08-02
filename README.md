# filebeat-module-proftpd
This is a module for [Filebeat](https://www.elastic.co/products/beats/filebeat) to ingest the Proftpd's xferlog log file. 

## Quick and dirty recipe to make it work: 
 * Install the filebeat package (Debian: filebeat). 
 * Follow the [Filebeat Developer guide: creating a new module](https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-modules-devguide.html) to prepare a new module. 
 * First, clone the [Beats](https://github.com/elastic/beats) repository. 
 * Copy the entire `proftpd` directory (from filebeat-module-proftpd) into the `beats/filebeat/module` directory of the Beats repository. 
 * Run the `make update` to generate `filebeat.template-es2x.json`, `filebeat.template-es6x.json` and `filebeat.template.json` and copy them to `/etc/filebeat` (or wherever they belong to).
 * Copy the entire `proftpd` directory to `/usr/share/filebeat/module/`  
    ``cp -a proftpd /usr/share/filebeat/module/``
 * Restart the filebeat service. 
 * Et voilà, your xferlog is nicely indexed in Elasticsearch. 

This is an early revision. It works but still lacks some documentation and might have some rough edges. Feedback is very much appreciated. 

It has been tested with Filebeat version 5.5.1. 
