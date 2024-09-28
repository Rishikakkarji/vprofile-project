FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN wget http://34.237.245.68:8081/repository/vprofile-repo/QA/vproapp/2-24-09-23_17-39/vproapp-2-24-09-23_17-39.war

FROM tomcat:9-jre11

RUN rm -rf /usr/local/tomcat/webapps/*

COPY --from=BUILD_IMAGE /vproapp-2-24-09-23_17-39.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
