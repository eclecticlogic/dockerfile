# Amazon Dynamodb local container

FROM openjdk:8u151-jdk-slim

MAINTAINER Karthik Abram <karthik@eclecticlogic.com>

RUN mkdir /dynamodb
ADD http://dynamodb-local.s3-website-us-west-2.amazonaws.com/dynamodb_local_latest.tar.gz /dynamodb
RUN cd /dynamodb && \
 	tar -xvzf dynamodb_local_latest.tar.gz && \
 	rm -f dynamodb_local_latest.tar.gz && \
 	mkdir data 

RUN groupadd -r dynamo && useradd -r -g dynamo dynamo

USER dynamo

#VOLUME /dynamodb/data
EXPOSE 8000
WORKDIR /dynamodb
ENTRYPOINT ["java", "-Djava.library.path=./DynamoDBLocal_lib", "-jar", "./DynamoDBLocal.jar", "-dbPath", "/dynamodb/data"]
