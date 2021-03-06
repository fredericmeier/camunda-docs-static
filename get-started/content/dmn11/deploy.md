---

title: 'Evaluate, Deploy and Test the DMN 1.1 decision table'
weight: 40

menu:
  main:
    name: "Evaluate, Deploy and Test"
    parent: "get-started-dmn"
    identifier: "get-started-dmn-deploy"
    pre: "Use Java Code to evaluate the decision table, then deploy the web application to Apache Tomcat and test it with Cockpit."

---

In this step, we use Java Code to evaluate the decision table. Then we deploy the web application to Apache Tomcat and test it with Cockpit.

# Evaluate the Decision Table

To directly evaluate the decision table after deployment, add the following method to your DishApplication class:

```java
package org.camunda.bpm.getstarted.dish;

import org.camunda.bpm.application.PostDeploy;
import org.camunda.bpm.application.ProcessApplication;
import org.camunda.bpm.application.impl.ServletProcessApplication;
import org.camunda.bpm.engine.DecisionService;
import org.camunda.bpm.engine.ProcessEngine;
import org.camunda.bpm.engine.variable.VariableMap;
import org.camunda.bpm.engine.variable.Variables;

@ProcessApplication("Dish App DMN")
public class DishApplication extends ServletProcessApplication {

  @PostDeploy
  public void evaluateDecisionTable(ProcessEngine processEngine) {

    DecisionService decisionService = processEngine.getDecisionService();

    VariableMap variables = Variables.createVariables()
      .putValue("season", "Summer");

    decisionService.evaluateDecisionTableByKey("dish", variables);
  }

}
```

{{< get-tag repo="camunda-get-started-dmn" tag="Step-4" >}}

# Build the Web Application with Maven

Select the `pom.xml` in the Package Explorer, perform a right-click and select `Run As / Maven Install`. This will generate a WAR file named `dish-dmn-0.1.0-SNAPSHOT.war` in the `target/` folder of your Maven project.

{{< note title="Hint" class="info" >}}
If the `dish-dmn-0.1.0-SNAPSHOT.war` file is not visible after having performed the Maven build, you need to refresh the project (F5) in eclipse.
{{< /note >}}


# Deploy to Apache Tomcat

In order to deploy the process application, copy-paste the `dish-dmn-0.1.0-SNAPSHOT.war` from your Maven project to the `$CAMUNDA_HOME/server/apache-tomcat/webapps` folder.

Check the log file of the Apache Tomcat server. If you see the following log message, the deployment was successful:

<pre class="console">
INFO org.camunda.commons.logging.BaseLogger.logInfo
ENGINE-07015 Detected @ProcessApplication class 'org.camunda.bpm.getstarted.dish.DishApplication'
INFO org.camunda.commons.logging.BaseLogger.logInfo
ENGINE-08024 Found processes.xml file at ../webapps/dish-dmn-0.1.0-SNAPSHOT/WEB-INF/classes/META-INF/processes.xml
INFO org.camunda.commons.logging.BaseLogger.logInfo
ENGINE-08023 Deployment summary for process archive 'dish-dmn':

        dish.dmn

INFO org.camunda.commons.logging.BaseLogger.logInfo
ENGINE-08050 Process application Dish App DMN successfully deployed
</pre>


# Verify the Deployment with Cockpit

Now, use Cockpit to check if the decision table is successfully deployed. Go to [http://localhost:8080/camunda/app/cockpit](http://localhost:8080/camunda/app/cockpit). Log in with *demo / demo*. Your decision table *Dish* should be listed on the dashboard.

{{< img src="../img/cockpit-dish-dmn.png" >}}


# Verify the Evaluation with Cockpit

On the Dashboard, click on the deployed decision table *Dish*. This opens a dialog where you see when the decision table was evaluated. 

{{< img src="../img/cockpit-decision-overview-dish-dmn.png" >}}

If you click on the id, you can see the historic data of the evaluation. The matched rules are highlighted and the input and output values are listed in the table below.

{{< img src="../img/cockpit-decision-history-dish-dmn.png" >}}

Verify that the 4th rule was matched since the *season* variable was set to "Summer".

# Next Steps

Congratulations, you have now sucessfully set up a project with a DMN decision table.

Next,

* see how you can evaluate the decision using the [REST API](/manual/reference/rest/decision-definition/post-evaluate/),
* learn more about DMN by reading the [DMN Reference](/manual/reference/dmn11/),
* learn more about the [Decision API exposed by Camunda Process Engine](/manual/user-guide/process-engine/decisions/),
* check how you can invoke the decision from a [BPMN Business Rule Task](/manual/reference/bpmn20/tasks/business-rule-task/),
* and a [CMMN Decision Task](/manual/reference/cmmn11/tasks/decision-task/).
