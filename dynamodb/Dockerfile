
# Amazon Dynamodb local container

FROM dockerfile/java:oracle-java8

MAINTAINER Karthik Abram <karthik@eclecticlogic.com>

RUN mkdir /dynamodb && cd /dynamodb && \
 	wget -nv http://dynamodb-local.s3-website-us-west-2.amazonaws.com/dynamodb_local_latest.tar.gz && \
 	tar -xvzf dynamodb_local_latest.tar.gz && \
 	rm -f dynamodb_local_latest.tar.gz && \
 	mkdir data 

RUN groupadd -r dynamo && useradd -r -g dynamo dynamo

USER dynamo

VOLUME /dynamodb/data
EXPOSE 8000
WORKDIR /dynamodb
ENTRYPOINT ["java", "-Djava.library.path=./DynamoDBLocal_lib", "-jar", "./DynamoDBLocal.jar", "-dbPath", "./data"]