# Logback #

**WildFly**

# Install: #

### copy ###
*  standalone/configuration/logging.properties ([source](https://github.com/leandrodelsole/wildfly-logback-subsystem/blob/master/src/test/java/examples/logging.properties))

### copy or create yours ###
*  standalone/configuration/logback-default.xml ([sample](https://github.com/leandrodelsole/wildfly-logback-subsystem/blob/master/src/test/java/examples/logback-default.xml))
   * caution: not all logback syntax is supported in this file, see known issues

### standalone/configuration/standalone.xml ###
*  remove &lt;extension module="org.jboss.as.logging"/&gt;
*  add &lt;extension module="me.janario.logback"/&gt;
 
*  remove &lt;subsystem xmlns="urn:jboss:domain:logging:2.0"&gt;...&lt;/subsystem&gt;
*  add &lt;subsystem xmlns="urn:me.janario.logback:1.0"/&gt;
 
* copy target/modules/system/layers/logback to wildfly-8.2.0.Final/modules/system/layers/logback
* copy target/modules/layers.conf to wildfly-8.2.0.Final/modules/layers.conf


### Known Issues ###
* After stop LoggerContext old Logger still with a reference of it(stoped and no more contextual)
* Improve integration with LoggerContext logger-selector (levels and appenders)
* https://jira.qos.ch/browse/LOGBACK-1077

# Releases #
For each new release developed, it must be created manually in GitHub releases tab.
There should be written a changelog and `target/modules.zip` file must be uploaded on the release.
This file is generated in `mvn clean package` run.