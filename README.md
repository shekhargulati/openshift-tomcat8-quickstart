## Quickstart to run Apache Tomcat 8 on OpenShift##

Apache Tomcat 8 will be adding support for lot of Java EE 7 features like WebSockets , upgrading to Servlet 3.1, JSP 2.3 , Expression language 3.0, and some tomcat specific features. There is not much documentation around all the features that will be added in Apache Tomcat 8 but I found this presentation [slides](http://archive.apachecon.com/eu2012/presentations/06-Tuesday/RN-ApacheEE/aceu-2012-tomcat-8-preview.pdf) useful.The sample running Apache Tomcat 8 on OpenShift is available at http://tomcat8-cix.rhcloud.com/ and http://tomcat8-cix.rhcloud.com/examples

1. First create OpenShift diy application with name tomcat8
```
rhc app create tomca8 diy
```

2. Add git remote to Tomcat 8 OpenShift quickstart and pull code from it.
```
cd tomca8
git remote add upstream https://github.com/shekhargulati/openshift-tomcat8-quickstart.git
git pull -s recursive -X theirs upstream master
```

3. Push the code to OpenShift. 
```
git push
```

4. Check the Apache Tomcat 8 is up and running by going to http://tomcat8-{domain}.rhcloud.com. Replace domain with your own domain name.

5. The examples samples are also deployed. You can view the sample app under http://tomcat8-{domain}.rhcloud.com/examples