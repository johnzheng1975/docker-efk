FROM docker.elastic.co/elasticsearch/elasticsearch-oss:6.2.4
COPY bin/ bin/
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install -b com.floragunn:search-guard-6:6.2.4-23.0
RUN cd /usr/share/elasticsearch/plugins/search-guard-6/tools && chmod 755 ./install_demo_configuration.sh && ./install_demo_configuration.sh -y 
RUN cd /usr/share/elasticsearch/plugins/search-guard-6/tools && ls -al && chmod +x *.sh 
RUN sleep 1 && cat /usr/share/elasticsearch/config/elasticsearch.yml
