# cy-es032017


# Elasticsearch
  - Home: https://www.elastic.co/
  - Download home: https://www.elastic.co/downloads/elasticsearch
  - Elasticsearch version: 2.4.4
    - tar_url: https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.4.4/elasticsearch-2.4.4.tar.gz

  - Cluster:
    - Node1: 24
      tags:
    - Node2: 105
      tags:

  - Install cluster
    - update cache: sudo apt-get update -y
    - install java8
      `ssh -v ubuntu@<ip> < scripts/install_java8.sh`
    - validate if java8 is installed??
        `ssh -v ubuntu@<ip> < 'javac -version'`
    - get installer tarball
      - wget https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.4.4/elasticsearch-2.4.4.tar.gz

    - setup node
      - directory: `mkdir -p /opt/elasticsearch`
      - `cp ~ubuntu/elasticsearch-2.4.4.tar.gz  /opt/elasticsearch/`
      - extract tarball in `/opt/elasticsearch`
        ```
        tar xvzf elasticsearch-2.4.4.tar.gz
        ```
      - alternatives: https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html
      - setup user `useradd elastic`
      - setup permissions ` chown -Rvf elastic:elastic /opt/elasticsearch/`
      - open elasticsearch.yml `vim config/elasticsearch.yml'
        - change `network.host: 0.0.0.0`

      - increase max_map_count, run command: `sysctl -w vm.max_map_count=262144`

      - install plugins
        - hq: http://www.elastichq.org/, https://github.com/royrusso/elasticsearch-HQ
        - head: https://github.com/mobz/elasticsearch-head
        - kopf: https://github.com/lmenezes/elasticsearch-kopf

      - add node to cluster
        - 
