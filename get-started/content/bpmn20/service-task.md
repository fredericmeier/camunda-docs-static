---

title: 'Invoking a Java Class from a BPMN 2.0 Service Task'
weight: 60

menu:
  main:
    name: "Java Service Task"
    parent: "get-started-pa"
    identifier: "get-started-pa-java-service-task"
    pre: "Invoke a Java Class from a BPMN 2.0 Service Task."

---


In the last section of this tutorial we learn how to invoke a Java class from a BPMN 2.0 service task.


# Add a Service Task to the Process

Use the Camunda Modeler to add a service task after the user task. To do so, select the activity shape (rectangle) and drag it onto a sequence flow (see screenshot). Name it *Process Request*. Change the activity type to *Service Task* by clicking on it and using the wrench button.


{{< img src="../img/modeler-service-task1.png" >}}


# Add a JavaDelegate Implementation

Now we need to add the actual service task implementation. In the Eclipse project, add a class named `ProcessRequestDelegate` implementing the `JavaDelegate` interface:

```java
public class ProcessRequestDelegate implements JavaDelegate {

  private final static Logger LOGGER = Logger.getLogger("LOAN-REQUESTS");

  public void execute(DelegateExecution execution) throws Exception {
    LOGGER.info("Processing request by '"+execution.getVariable("customerId")+"'...");
  }

}
```


# Configure the Class in the Process

Use the properties view to reference the service task in the process (see screenshot). You need to provide the fully qualified classname of your class in the *Java Class* property field.

{{< img src="../img/modeler-service-task2.png" >}}

Save the process model and update it in Eclipse. Build, deploy and execute the process application. After completing the *Approve Loan* step, check the logfile of the Apache Tomcat server:

<pre class="console">
INFO org.camunda.bpm.getstarted.loanapproval.ProcessRequestDelegate.execute
Processing request by 'GFPE-23232323'...
</pre>

{{< note title="Classloading with a shared process engine" >}}
The process engine resolves the ProcessRequestDelegate class from the application classloader. This allows you to

* have a different classloader for each Process Application,
* bundle libraries inside your application,
* (re-)deploy the application at runtime (without stopping / restarting the process engine).

{{< /note >}}

{{< get-tag repo="camunda-get-started" tag="Step-5" >}}
