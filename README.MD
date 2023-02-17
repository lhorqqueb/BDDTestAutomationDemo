# BDDTestAutomation
Production ready BDD test automation framework based on Junit and Selenium Java

### I would love to show you the framework in detail. Please contact me for a demo.

### Dependencies
This automation framework depends on the following
external libraries:
* **junit**: for running a test.
* **selenium-java**: for browser automation through Java code.
* **webdrivermanager**: for managing webdriver executable files through Java code.
* **cucumber-java**: Cucumber support for java language.
* **cucumber-jvm-deps**: Cucumber support for java runtime environment.
* **cucumber-junit**: Cucumber support for junit test framework.
* **datafaker**: for generating randomized test data on the fly.

### Framework Project Structure Diagram
```
|-features                         #  all feature files are stored here
|-images                           #  all images are stored here
|-report                           #  all the generated reports are here
|-src
    |---test
        |----java                  #  all the java source files needs to stored in this folder
            |-[+]stepdefinitions   #  java class package, all the step definitions classes will be stored here
            |-[+]utility           #  java class package, all the utility classes will be stored here
            |-TestRunner           #  java class, links feature files and step definitions, used to run feature files
|-.gitignore                       #  git ignore config file
|-pom.xml                          #  project object model file for the maven software
|-READMD.md                        #  you are currently viewing this file
```

![screenshot](/images/BDDframeworkscreenshot.png)

### Execution Triggers
Executing specific tests
```
mvn clean test -Dcucumber.options="--tags @smoke"
```
<br/>

If you want to trigger more than one test,
just add desired cucumber tags separated with space
```
mvn clean test -Dcucumber.options="--tags @smoke @regression @e2e"
```
<br/>

If you want to trigger test(s) with preferred browser,
you can do so with specifying the browser type
```
mvn clean test -Dcucumber.options="--tags @smoke" -Dbrowser=chrome
```

|Browser         |Option String                  |
|----------------|-------------------------------|
|Chrome Headless |`-Dbrowser=headless`           |
|Google Chrome   |`-Dbrowser=chrome`             |
|Mozilla Firefox |`-Dbrowser=firefox`            | 
|Microsoft Edge  |`-Dbrowser=edge`               |  


## Inner Works of the Framework
This is a diagram that details the internal structure of the framework. Multiple parts of the
code work together to bring successful automated test executions.

![screenshot](/images/BDDinternalstructure.png)


### Generating the report
After the test execution, you can generate beautiful Cluecumber HTML test report by executing the
following maven command:
```
mvn cluecumber-report:reporting
```

## How to view the report
All the test execution reports are available as an HTML report on following folder after test execution.
Please navigate to the report folder, click the generated-report folder, and open the index.html file
with your preferred browser.
```
 report
   |--[generated-report] 
        |----index.html
```
![screenshot](/images/BDDreportscreenshot.png)