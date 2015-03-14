# WSO2 CEP 3.1.0

# Pull base image.
FROM damajor/dockerimgs:oracle-java8

# Install Java.
RUN \
  apt-get update && \
  apt-get install -y unzip wget

# Fetch the wso2is package
RUN wget --user-agent="fido" \
  --output-document /opt/wso2cep.zip \
  --referer="http://connect.wso2.com/wso2/getform/reg/new_product_download" \
  http://product-dist.wso2.com/products/complex-event-processor/3.1.0/wso2cep-3.1.0.zip

RUN wget --user-agent="fido" \
  --output-document /opt/wso2mb.zip \
  --referer="http://connect.wso2.com/wso2/getform/reg/new_product_download" \
  http://product-dist.wso2.com/products/message-broker/2.2.0/wso2mb-2.2.0.zip

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Define working directory.
#WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

RUN unzip /opt/wso2cep.zip -d /opt
RUN unzip /opt/wso2mb.zip -d /opt

RUN cp /opt/wso2mb-2.2.0/client-lib/* /opt/wso2cep-3.1.0/repository/components/lib/

RUM rm -fr /opt/wso2cep.zip /opt/wso2mb.zip /opt/wso2mb-2.2.0

RUN \
  echo "export PATH=${JAVA_HOME}/bin:${PATH}" >> /etc/bash.bashrc

# Define default command.
CMD ["/opt/wso2cep-3.1.0/bin/wso2server.sh"]
