JBoss BPM Suite Rewards Demo
============================
This is the HR employee rewards demo that provides examples of human task integration, form designer
and a custom email work item handler.

There are several options available to you for using this demo; local, containerized or on any OpenShift installation.


Option 1 - Install on your machine
----------------------------------
1. [Download and unzip.](https://github.com/eschabell/bpms-rewards-demo/archive/master.zip)

2. Add products to installs directory.

3. Run 'init.sh' or 'init.bat' file. 'init.bat' must be run with Administrative privileges.

4. Follow instructions provided in console to start JBoss BPMS Server.

   ```
   # To view automated email notifications, start provided server as root/admin (see Notes below):
   #
   $ sudo java -jar support/fakeSMTP.jar 
   ```

   In fakeSMTP GUI click 'START SERVER' button or you will get 'Could not connect to SMTP host' errors. This does not prevent 
   the process from working, it just fails to send an email notification.

Login to http://localhost:8080/business-central  (u:erics / p:bpmsuite1!).



Option 2 - Install on Red Hat OpenShift installation
----------------------------------------------------
The following steps can be used to install this demo on any OpenShift installation:

1. [App Dev Cloud with JBoss BPM Rewards Demo](https://github.com/redhatdemocentral/rhcs-rewards-demo)


Option 3 - Generate containerized installation
----------------------------------------------
The following steps can be used to configure and run the demo in a container

1. [Download and unzip.](https://github.com/eschabell/bpms-rewards-demo/archive/master.zip)

2. Add product installer to installs directory.

3. Copy contents of support/docker directory to the project root.

4. Build demo image.

	```
	docker build -t eschabell/bpms-rewards-demo .
	```
5. Start demo container

	```
	docker run -it -p 8080:8080 -p 9990:9990 eschabell/bpms-rewards-demo
	```

Login to http://:localhost:8080/business-central (u:erics / p:bpmsuite1!)


Notes
-----
This project is pre-loaded into the JBoss BPM Suite, after starting it you can login,
examine the rule, process, and data model from within the various product components.

After claiming the user task as a manager (to approve or deny the award), if task completion takes longer
than 1 minutes it will te reassigned back into the group so other managers can claim it. The short time frame
of 1 minutes is for demo purposes, should talk about days to complete instead as if a manager that claimed a
task got sick and failed to complete the claimed task.

Optional: A task notification has also been setup to alert the members of the group responsible if a task sits longer than 2 minutes
without being started (claimed). This is an email notification which you can view using the provided simple java SMTP server 
'fakeSMTP.jar' (from https://nilhcem.github.io/FakeSMTP), just start as root/admin user to catch sent notifications in the
mailbox window provided:

   ```
   $ sudo java -jar support/fakeSMTP.jar 
   ```

   In fakeSMTP GUI click 'START SERVER' button or you will get 'Could not connect to SMTP host' errors. This does not prevent 
   the process from working, it just fails to send an email notification.

There is a workshop [available online](http://bpmworkshop-onthe.rhcloud.com) that will show you how to build this demo from scratch. 


Supporting Articles
-------------------
- [App Dev in the Cloud - HR Employee Rewards Application on OpenShift](http://www.schabell.org/2017/01/appdev-in-cloud-hr-employee-rewards-app-openshift.html)

- [How to put the JBoss HR Employee Rewards project into the Cloud](http://www.schabell.org/2016/05/howto-put-jboss-hr-employee-rewards-into-cloud.html)

- [Quick Tour #6: Build & run a JBoss BPM Suite project (video)](http://www.schabell.org/2015/10/quick-tour-6-build-and-run-project.html)

- [Quick Tour #5: How to import a project into JBoss BPM Suite (video)](http://www.schabell.org/2015/09/quick-tour-5-how-to-import-project.html)

- [7 Steps to Your First Process with JBoss BPM Suite Starter Kit](http://www.schabell.org/2015/08/7-steps-first-process-jboss-bpmsuite-starter-kit.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 19 Automated e-mail task notifications)](http://www.schabell.org/2015/03/redhat-jboss-bpmsuite-online-workshop-lab19-automate-task-notification.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 18 Automate Task Reassignment)](http://www.schabell.org/2015/03/redhat-jboss-bpmsuite-online-workshop-lab18-automate-task-reassignment.html)

- [3 shockingly easy ways into JBoss rules, events, planning & BPM](http://www.schabell.org/2015/01/3-shockingly-easy-ways-into-jboss-brms-bpmsuite.html)

- [Jump Start Your Rules, Events, Planning and BPM Today](http://www.schabell.org/2014/12/jump-start-rules-events-planning-bpm-today.html)

- [5 Handy Tips From JBoss BPM Suite For Release 6.0.3](http://www.schabell.org/2014/10/5-handy-tips-from-jboss-bpmsuite-release-603.html)

- [How To Duplicate Artifacts In JBoss BPM Suite in 3 Easy Steps](http://www.schabell.org/2014/10/how-to-duplicate-artifacts-within-jboss-bpmsuite-in-3-easy-steps.html)

- [Launching Into the Clouds With 2 New OpenShift Primer bpmPaaS Quickstarts](http://www.schabell.org/2014/10/launching-into-clouds-with-2-new-openshift-primer-bpmpaas-quickstarts.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 17 Running Rewards Project)](http://www.schabell.org/2014/09/redhat-jboss-bpmsuite-online-workshop-lab17-running-rewards-project.html)

- [Red Hat JBoss BPM Suite - all product demos updated for version 6.0.2.GA release](http://www.schabell.org/2014/07/redhat-jboss-bpmsuite-product-demos-6.0.2-updated.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 16 Creating User Task Forms)](http://www.schabell.org/2014/06/redhat-jboss-bpmsuite-online-workshop-rewards-lab16-user-task-forms.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 15 Completing Process Details)](http://www.schabell.org/2014/06/redhat-jboss-bpmsuite-online-workshop-rewards-lab15-process-details.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 14 Create Rewards Process)](http://www.schabell.org/2014/06/redhat-jboss-bpmsuite-online-workshop-rewards-lab14-rewards-process.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 13 - Creating Domain Model)](http://www.schabell.org/2014/06/redhat-jboss-bpmsuite-online-workshop-rewards-lab13-creating-domain-model.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 12 Creating Rewards Project)](http://www.schabell.org/2014/05/redhat-jboss-brms-online-workshop-coolstore-lab12-designing-rewards-process.html)

- [Red Hat JBoss BPM Suite - Online Workshop Building a Rewards Demo (Lab 11 Installing BPM Suite)](http://www.schabell.org/2014/05/redhat-jboss-brms-online-workshop-coolstore-lab11-installing-bpmsuite.html)


Released versions
-----------------
See the tagged releases for the following versions of the product:

- v2.3 - Forked back from JBoss Demo Central for updating to JBoss BPM Suite 6.4.0, JBoss EAP 7.0.0, rewards demo installed locally, containerized or on any OpenShift installation.

- v2.2 - JBoss BPM Suite 6.3.0 on JBoss EAP 6.4.7 with travel agency installed and RH CDK on OSE Cloud install option.

- v2.1 - JBoss BPM Suite 6.2.0-BZ-1299002 on JBoss EAP 6.4.4 with rewards demo installed and RH CDK on OSE Cloud install option.

- v2.0 - JBoss BPM Suite 6.2.0-BZ-1299002 on JBoss EAP 6.4.4 with rewards demo installed.

- v1.9 - JBoss BPM Suite 6.2.0, JBoss EAP 6.4.4 and rewards demo installed.

- v1.8 - JBoss BPM Suite 6.1.0 installer with rewards demo installed.

- v1.7 - JBoss BPM Suite 6.0.3 installer with automated task email notifications.

- v1.6 - JBoss BPM Suite 6.0.3 installer with automated task reassignment.

- v1.5 - JBoss BPM Suite 6.0.3 installer with optional containerized installation.

- v1.4 - moved to JBoss Demo Central, updated windows init.bat support and one click install button.

- v1.3 - JBoss BPM Suite 6.0.3 installer with rewards demo installed.

- v1.2 - JBoss BPM Suite 6.0.2 installer used, with rewards demo installed.

- v1.1 - JBoss BPM Suite 6.0.2, JBoss EAP 6.1.1, and migrated from BRMS 5.3.

- v1.0 - JBoss BPM Suite 6.0.1, JBoss EAP 6.1.1, and migrated from BRMS 5.3.


[![Video Rewards Run](https://raw.githubusercontent.com/eschabell/erics-images/master/brms_bpms_workshop/image309.png)](http://vimeo.com/ericschabell/bpms-hr-employee-rewards-demo-run)

![Process](https://raw.githubusercontent.com/eschabell/bpms-rewards-demo/master/docs/demo-images/rewards-process.png)

![Process & Task Dashboard](https://raw.githubusercontent.com/eschabell/bpms-rewards-demo/master/docs/demo-images/mock-bpm-data.png)

