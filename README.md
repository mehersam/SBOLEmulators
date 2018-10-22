SBOLRunners
=============

SBOLRunners is a collection of test applications of SBOL supporting software. These runners can be tested using the 
[SBOLTestRunner](https://github.com/mehersam/SBOLTestRunner) tool which determines an application's level of compliance 
with the SBOL standard. 

Retrieving SBOL Test Runners
============================

1. [Create](https://github.com/) a GitHub account.
2. [Setup](https://help.github.com/articles/set-up-git) Git on your machine.
3. [Clone](https://help.github.com/articles/cloning-a-repository/) the SBOLRunners GitHub repository to your machine.
4. Each runner is a separate submodule. To retrieve each submodule, use the following command within the directory the runner wanted.

```
git submodule update --init --recursive
```

### Compiling and Packaging each Test Runner 

1. [Setup](http://maven.apache.org/download.cgi) Apache Maven. A tutorial on using Apache Maven is provided [here](http://maven.apache.org/guides/getting-started/index.html).

2. In the command line, change to the directory of the runner needed (e.g. ```cd /path/to/libSBOLjRunner```) and execute the following command

```
mvn package
```

This will compile the libSBOLjRunner source files, package the compiled source into a libSBOLjRunner JAR file (```libSBOLjRunner-<version>-SNAPSHOT-withDependencies.jar```), and place the JAR file into the ```core2/target``` sub-directory. 

Submitting a SBOL Test Runner
=============================

To submit a SBOL Test Runner, the application must be compatible to run with the SBOLTestRunner. 

1. The test runner application must be executable from the commandline
2. If the application follows a simple round-trip test, two commandline arguments are required : an SBOL input file and a file path for the retrieved file 
3. If the application follows a complex round-trip test, three commandline arguments are required : an SBOL input file, a file path for the retrieved file, and a file path for the emulated file. 
4. A thorough README explaining how to run the tester application from the commandline is required. If there are additional commandline arguments to be passed to the application, please explain in the README. 
5. [Fork](https://help.github.com/articles/fork-a-repo/) this repository.  
6. Test the application using the [SBOLTestRunner](https://github.com/mehersam/SBOLTestRunner) tool.  
7. If the application is compatible with the SBOLTestRunner, submit a [pull request](https://help.github.com/articles/creating-a-pull-request-from-a-fork/). 
