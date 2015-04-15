# NDL-VuFind-Solr

Solr 5 for NDL-VuFind2 (Finna 2)

This is for the most parts vanilla Solr 5. The following changes have been made:

- Solr home (set in solr.in.finna.sh[.sample]) is ./vufind which contains the Finna VuFind core configs
- The following libraries have been added to server/solr-webapp/webapp/WEB-INF/lib:
  - icu4j
  - jna
  - jts
  - jtsio
  - libvoikko
  - lucene-analyzers-icu (from contrib/analysis-extras/lucene-libs/)
  - solrvoikko2
- The docs directory has been removed

## Installation

### Prerequisites

1. Install libvoikko (see the first three steps at https://github.com/NatLibFi/SolrPlugins/wiki/Voikko-plugin)

### Solr

1. Put the files somewhere
2. Add user solr
3. chown the files and directories to solr user
4. Copy bin/solr.in.finna.sh.sample to bin/solr.in.finna.sh and edit as required
5. To enable startup via system init and management with service command in RHEL 6.x, copy bin/init.d/solr.finna to /etc/init.d/solr, make it executable, change the paths in it and execute the following commands:

    `chkconfig --add solr`

    `chkconfig solr on`

6. Start solr with command

    `service solr start`

7. Check the logs at server/logs for any errors
