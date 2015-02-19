# NDL-VuFind-Solr
Solr 4 for NDL-VuFind / NDL-VuFind2

## Installation

### Prerequisites

1. Install libvoikko (see the first three steps at https://github.com/NatLibFi/SolrPlugins/wiki/Voikko-plugin)

### Solr

1. Put the files somewhere
2. Add user solr
3. chown the files and directories to solr user
4. Copy solr.sh.sample to solr.sh and edit paths (especially JETTY_PATH)
5. Copy etc/jetty.xml.sample to etc/jetty.xml
6. Copy etc/realm.properties.sample to etc/realm.properties
7. Copy vufind/solr.xml.discovery_sample to vufind/solr.xml
8. To enable startup via system init and management with service command in RHEL 6.x, copy solr-rhel.sample to /etc/init.d/solr, make it executable and execute the following commands:
    
    `chkconfig --add solr`
    
    `chkconfig solr on`

9. Start solr with command
    
    `service solr start`

10. Check the logs logs/jetty.log and logs/solr.log for any errors
