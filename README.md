# TFL
Plan a Journey - TFL Overflow
selenium-cucumber-java-maven
selenium-cucumber : Automation Testing Using Java

selenium-cucumber is a behavior driven development (BDD) approach to write automation test script to test Web. It enables you to write and execute automated acceptance/unit tests. It is cross-platform, open source and free. Automate your test cases with minimal coding.

Documentation
-Installation: 
Prerequisites: 
Java
Maven
Eclipse
Eclipse Plugins
Maven
Cucumber

Setting up selenium-cucumber-java
Install Java and set path.
Install Maven and set path.
Clone respective repository or download zip.
maven : https://github.com/selenium-cucumber/selenium-cucumber-java-maven-example

Running features
Goto project directory.

Use "mvn test" command to run features.

Use "mvn test -Dbrowser=browser_name" to run features on specific browser.

browser_name can be one of following but make sure that browser’s driver file are present and specified in system variable. -- ff -- chrome -- ie -- safari

Use mvn test -Dcucumber.options="classpath:features/my_first.feature" to run specific feature if you have multiple feature files.

Use mvn test -Dcucumber.options="–-plugin html:target/result-html" to generate a HTML report.

Use mvn test -Dcucumber.options="–-plugin json:target/result-json" to generate a JSON report.

Now Write your own tests in feature file using Predefined Steps .


Framework Architecture:
src/test/resources/features - all the cucumber features files (files .feature ext) goes here.
src/test/java/userStepDefinition - you can define step defintion under this package for your feature steps.
src/test/java/env - this package contains cucumber runner (RunCukeTest.java) where you can configure your glue code location (step defintions), define test result output format.(html, json, xml). Hooks where you can configure all before and after test settings Hooks.java, DriverUtil.java contains code for intializing driver instances for respective driver.
src/main/java/platformConfigs - If you want to run your test on saucelab and browserstack platforms, you need to add its configuration such as username, access key here.
src/main/java/browserConfig - When you run your test on remote browser/platform you have to provide capabilities and platform information here.
src/main/java/appUnderTest - If you are testing mobile based application you can keep your app build here.

Writing a test:
The cucumber features goes in the features library and should have the ".feature" extension.

You can start out by looking at features/my_first.feature. You can extend this feature or make your own features using some of the predefined steps that comes with selenium-cucumber.

Predefined steps:
By using predefined steps you can automate your test cases more quickly, more efficiently and without much coding.

Running test:
Go to your project directory from terminal and hit following commands

mvn test (defualt will run on local chrome browser)
mvn test "-Dbrowser=chrome" (to use any other browser)
mvn test -Dcucumber.options="classpath:features/my_first.feature" to run specific feature.
mvn test -Dcucumber.options="–-plugin html:target/result-html" to generate a HTML report.
mvn test -Dcucumber.options="–-plugin json:target/result-json" to generate a JSON report.

Running test On remote browser/platform:
To run test on saucelab, browserstack or any other remote browser you need to create browser config file under src/main/java/browserConfig


To run on browserstack create config file with name preceding with browserstack

browserstack_windows_chrome.properties
browserstack_mac_firefox.properties
mvn test "-Dconfig=browserstack_mac_firefox"

Add Maven Dependencies
