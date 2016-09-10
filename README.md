
## Quickstart to run Apache Tomcat 8 on OpenShift##

#### Added support for Java 1.8 and Apache Ant 1.9 ####

Apache Tomcat 8 adds support for lots of Java EE 7 features like WebSockets, Servlet 3.1, JSP 2.3, Expression Language 3.0, as well as additional Tomcat-specific features. There is not much documentation around all that will be added in Apache Tomcat 8 but I found these presentation [slides](http://archive.apachecon.com/eu2012/presentations/06-Tuesday/RN-ApacheEE/aceu-2012-tomcat-8-preview.pdf) useful.  Samples running Apache Tomcat 8 on OpenShift can be found at http://tomcat8-cix.rhcloud.com/ and http://tomcat8-cix.rhcloud.com/examples

1. First create an OpenShift DIY application with your desired appname (here, using "tomcat8"):
```
rhc app create tomcat8 diy
```

2. Add git remote to Tomcat 8 OpenShift quickstart and pull code from it.
```
cd tomcat8
git remote add upstream https://github.com/shekhargulati/openshift-tomcat8-quickstart.git
git pull -s recursive -X theirs upstream master
```
If you get an error saying ```fatal: refusing to merge unrelated histories``` use
```
git pull -s recursive -X theirs upstream master --allow-unrelated-histories
```
3. Push the code to OpenShift. 
```
git push
```

4. Check that Apache Tomcat 8 is up and running by going to http://tomcat8-{domain}.rhcloud.com. Replace {domain} with your own domain name.

5. Tomcat's examples will also be deployed. You can view them under http://tomcat8-{domain}.rhcloud.com/examples.
