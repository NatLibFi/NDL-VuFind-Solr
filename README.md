# NDL-VuFind-Solr

Solr 5 for NDL-VuFind2 (Finna 2)

This is for the most parts vanilla Solr 5. The following changes have been made:

- Solr distribution is in vendor directory
- Solr home (set in solr.in.finna.sh[.sample]) is ./vufind which contains the Finna VuFind core configs
- The following libraries have been added to vendor/server/solr-webapp/webapp/WEB-INF/lib (putting them in vufind/lib doesn't seem to work, probably because of SOLR-4852 and SOLR-6188, and trying workaround still doesn't let JTS load properly):
  - jts
  - jtsio
- The vendor/docs directory has been removed

## Installation

### Prerequisites

1. Install libvoikko (see the first three steps at https://github.com/NatLibFi/SolrPlugins/wiki/Voikko-plugin)

### Solr

1. Put the files somewhere
2. Add user solr
3. chown the files and directories to solr user
4. Copy vufind/solr.in.finna.sh.sample to vufind/solr.in.finna.sh and edit as required
5. Use the following command to start Solr manually:

    `SOLR_INCLUDE=vufind/solr.in.finna.sh vendor/bin/solr start`

6. To enable startup via system init and management with service command in RHEL 6.x, copy vufind/solr.finna-init-script to file /etc/init.d/solr, make it executable, change the paths in it and execute the following commands:

    `chkconfig --add solr`

    `chkconfig solr on`

7. Start solr with command

    `service solr start`

8. Check the logs at server/logs for any errors
