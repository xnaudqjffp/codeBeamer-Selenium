Selenium-Maven-Template
=======================

[![Join the chat at https://gitter.im/Ardesco/Selenium-Maven-Template](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Ardesco/Selenium-Maven-Template?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

A maven template for Selenium 3 that has the latest dependencies so that you can just check out and start writing tests in four easy steps. If you like what you see have a look at my Selenium book [Mastering Selenium Webdriver](https://www.amazon.co.uk/Mastering-Selenium-WebDriver-Mark-Collin/dp/1784394351).

1.	Open a terminal window/command prompt
2.	Clone this project.
3.	`cd Selenium-Maven-Template` (Or whatever folder you cloned it into)
4.	`mvn clean verify`

All dependencies should now be downloaded and the example google cheese test will have run successfully (Assuming you have Firefox installed in the default location)

### What should I know?

-	To run any unit tests that test your Selenium framework you just need to ensure that all unit test file names end, or start with "test" and they will be run as part of the build.
-	The maven failsafe plugin has been used to create a profile with the id "selenium-tests". This is active by default, but if you want to perform a build without running your selenium tests you can disable it using:

	```
	mvn clean verify -P-selenium-tests
	```

-	The maven-failsafe-plugin will pick up any files that end in IT by default. You can customise this is you would prefer to use a custom identifier for your Selenium tests.

### Anything else?

Yes you can specify which browser to use by using one of the following switches:

-	-Dbrowser=firefox
-	-Dbrowser=chrome
-	-Dbrowser=ie
-	-Dbrowser=edge
-	-Dbrowser=opera
-	-Dbrowser=htmlunit
-	-Dbrowser=phantomjs

You don't need to worry about downloading the IEDriverServer, MicrosoftWebDriver, chromedriver , operachromium, or wires binaries, this project will do that for you automatically.

Not got PhantomJS? Don't worry that will be automatically downloaded for you as well!

You can specify a grid to connect to where you can choose your browser, browser version and platform:

-	-Dremote=true
-	-DseleniumGridURL=http://{username}:{accessKey}@ondemand.saucelabs.com:80/wd/hub
-	-Dplatform=xp
-	-Dbrowser=firefox
-	-DbrowserVersion=44

You can even specify multiple threads (you can do it on a grid as well!):

-	-Dthreads=2

You can also specify a proxy to use

-	-DproxyEnabled=true
-	-DproxyHost=localhost
-	-DproxyPort=8080

If the tests fail screenshots will be saved in ${project.basedir}/target/screenshots

If you need to force a binary overwrite you can do:

-	-Doverwrite.binaries=true

### It's not working!!!

You have probably got outdated driver binaries, by default they are not overwritten if they already exist to speed things up. You have two options:

-	`mvn clean verify -Doverwrite.binaries=true`
-	Delete the `selenium_standalone_binaries` folder in your resources directory

### From install to Tests

-	**Note: you must install JAVA and set up jdk before install Maven**

### Maven install

-	aven install on your localhost or remote test server

-	Download Maven install bin or zip in this url:  
	`http://maven.apache.org/download.cgi`

-	Extract distribution archive in any directory  
	`unzip apache-maven-3.3.9-bin.zip` or`tar xzvf apache-maven-3.3.9-bin.tar.gz
	`

-	Add the `/bin` directory of the created directory `apache-maven-3.3.9` to the `PATH` environment variable

-	Confirm with `mvn -v` in a new shell. The result should look similar to

```
Apache Maven 3.3.3 (7994120775791599e205a5524ec3e0dfe41d4a06; 2015-04-22T04:57:37-07:00)  
Maven home: /opt/apache-maven-3.3.3  
Java version: 1.8.0_45, vendor: Oracle Corporation  
Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home/jre  
Default locale: en_US, platform encoding: UTF-8  
OS name: "mac os x", version: "10.8.5", arch: "x86_64", family: "mac"  
```

### Start Build and Run Test

-	NOTE: Follow below command in **Linux shell** or **Windows cmd** and you should run this command in Selenium Proejct folder

-	Start compile (compile result will be created in `target/classe` ):

```
mvn compile
```

-	Run test classe :  

```
mvn test
```

-	Create package file about compile result :  

```
  mvn package
```

-	Distribute on your localhost :  

```
  mvn install
```

-	Distribute on your remote server:  

```
mvn deploy
```

-	Clean your Maven build data:  

```
  mvn clean
```
