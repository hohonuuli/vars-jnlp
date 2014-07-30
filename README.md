# VARS-JNLP

Build a JNLP enabled set of vars-redux applications.

## Build Prerequisites
1. [Ant](https://ant.apache.org/)
2. [Maven](https://maven.apache.org/)

## How To Use

1. Check out the VARS source code and run `mvn install`. If you're using a custom database you may need to specify a profile to include your database properties. e.g. `mvn install -P dev`.
2. [Configure a keystore](https://weblogs.java.net/blog/2005/05/20/signing-jars-javanet-web-start-applications)
3. Modify _src/site/filter/mbari.properties_ with your keystore parameters.
4. Run the following from a terminal/shell/console: `ant clean;mvn package;ant`. This will generate your JNLP files and signed jars into _target/site_

You will need to manually edit the JNLP files that are built for deployment specifics. For example, if you need to use a specific database driver. Most everything is correct but you may need to prune unwanted dependenices (like derby) and change the title of the application.

__NOTE__: Depending on the version of java that you a running you may need to add your server to Java site exception list before your computer will allow the web start application to run. Instructions for editing the site exception list are found at [https://www.java.com/en/download/exception_sitelist.jsp](https://www.java.com/en/download/exception_sitelist.jsp)