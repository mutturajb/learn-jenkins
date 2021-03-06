# Chapter 8: Creating  Build Job for a Java Project

In this chapter, we are going to create a job to build/compile a sample java application with maven.

## Creating Maven Project

To create a build project,
* From New Item, select **Maven Project** and provide it a name e.g. "build"

![Maven Project](images/chap8/maven_proj.png)

* From the configuration screen, scroll to Source Code Management, select GIT and provide repository URL

e.g. https://github.com/schoolofdevops/demo

![GIT SCM](images/chap8/scm_git.png)

From **Build Triggers** select **Poll SCM**. Lets configure it to poll every 5 minutes using the following schedule

```
H/5 * * * *

```
![Poll SCM](images/chap8/poll_scm.png)


* Scroll down to Build step and you should see Root POM selected since its a Maven Project. In the Goals and options section, provide **compile** as a goal.

![Poll SCM](images/chap8/goal_compile.png)

In addition to compile, following are the goals Maven project could take.

1. validate
1. compile - compile source code
1. test - unit tests
1. package - build jar/war
1. integration-test
1. verify
1. install
1. deploy


* Save the job and clicl on **Build Now**.  Following is a snippet from the output of the build job.



```
[INFO] Compiling 1 source file to /var/jenkins_home/workspace/build/target/classes
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 10.216 s
[INFO] Finished at: 2016-04-27T17:11:30+00:00
[INFO] Final Memory: 19M/240M
[INFO] ------------------------------------------------------------------------
Waiting for Jenkins to finish collecting data
[JENKINS] Archiving /var/jenkins_home/workspace/build/pom.xml to com.example.app/maven-app/3.0-release/maven-app-3.0-release.pom
channel stopped
Finished: SUCCESS

```
