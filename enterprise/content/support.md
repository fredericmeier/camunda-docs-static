---

title: 'Camunda Enterprise Support Guide'
weight: 30

menu:
  main:
    name: "Support"
    identifier: "enterprise-support"

---

This guide is intended to help you get the support you need quickly and conveniently. This document includes information about contacting technical support, description of response times, and online resources.


# How to Create an Support Issue

Based on the agreed SLA (Service Level Agreement), you can contact our support service with your questions, wishes and problems.
To create a new support issue, follow the instructions below. To shorten the processing time, please provide us with as much information as possible.

{{< img src="../img/jira-create-support-issue.png" title="Create Support Issue" >}}

* Go to our [JIRA support system](https://app.camunda.com/jira/browse/SUPPORT)
* Select `Create Issue`
* Select `Support` as **project** and choose the desired [issue type]({{< relref "#issue-types" >}}).
* Give the ticket a meaningful **summary**
* You can give your ticket a [**priority**]({{< relref "#priority-level" >}}) depending on how urgent the issue is for you. 
* Provide us with a date in case of important **deadlines** that need to be reached.
* Enter a detailed **description** of your issue. In case of Bug Reports please use the template (Reproduce steps, Problem, Expected behavior, etc.). Make use of the [JIRA text formatting]({{< relref "#text-formatting" >}}) in order to represent code snippets in a better readable way.
* **Attachments** like screenshots, log files, stack traces or BPMN files help us to find and reproduce your bug faster.
* For bug reports and help requests, it is important to know which **environment** you use. Inform us about the used Camunda BPM platform version, application server, database and everything else that seems to be important for your issue.


## Issue Types

We distinguish three types of issues:

<table class="table table-bordered">
  <thead>
  <tr class="success">
    <th>Issue Type</th>
    <th>Description</th>
    <th>Important Notes</th>
  </tr>
  </thead>
  <tbody>
  <tr>
    <td>Bug Report<img class="img-responsive" src="../img/jira-bug-report.png"/></td>
    <td>File a Bug Report if a feature of the system doesn't work properly.</td>
    <td>Do not file Feature Requests as Bug Reports, even if you think that it is a really vital feature without which the product seems unusable.</td>
  </tr>
  <tr>
    <td>Feature Request<img class="img-responsive" src="../img/jira-feature-request.png"/></td>
    <td>Any missing features can be filed here.</td>
    <td>A Feature Request might be declined with an explanation about why it will not be part of the product. Otherwise, it is usually placed on the road-map and we inform you about status changes. Please add some information about your use case and why the feature is important to you.</td>
  </tr>
  <tr>
    <td>Help Request<img class="img-responsive" src="../img/jira-help-request.png"/></td>
    <td>File any questions you have that are unrelated to Bug Reports or Feature Requests as Help Requests.</td>
    <td></td>
  </tr>
  </tbody>
</table>


## Priority Level

You can prioritize issues depending on the impact of a bug on your system. Please note that according to your SLA's, a prioritization is only possible for bug tickets. Feature Requests and Help Requests are always prioritized as L3 - Default.

<table class="table table-bordered">
  <thead>
  <tr class="success">
    <th>Priority Level</th>
    <th>Description</th>
    <th>Important Notes</th>
  </tr>
  </thead>
  <tbody>
  <tr>
    <td>L1 <img class="img-responsive" src="../img/jira-blocker.png"/>Blocker</td>
    <td>Core components (i.e., process engine) of Camunda BPM do not work at all/produce critical errors that prevent usage in production mode.</td>
    <td><b>Bug Tickets only! Production mode only!</b></td>
  </tr>
  <tr>
    <td>L2 <img class="img-responsive" src="../img/jira-major.png"/>Critical</td>
    <td>Usage of Camunda BPM seriously affected, a workaround is urgently needed. </td>
    <td><b>Bug Tickets only!</b></td>
  </tr>
  <tr>
    <td>L3 <img class="img-responsive" src="../img/jira-minor.png"/>Default</td>
    <td>Non-critical errors, Help Requests, Feature Requests</td>
    <td>Bug Tickets, Feature Requests, Help Requests</td>
  </tr>
  </tbody>
</table>


## Text Formatting

JIRA offers the possibility to format text fields and comments using the Wiki Style Renderer. This offers a variety of formatting options, among which the option of adding preformatted code to your issues. To display a preview of your text in formatted form, hit the preview button at the bottom left of text fields.
You can click the help icon or go to the JIRA [Text Formatting Notation Help](https://jira.atlassian.com/secure/WikiRendererHelpAction.jspa?section=all) to find additional information.


## Visibility of JIRA Tickets

JIRA tickets will be shared with all your support contacts automatically.

{{< img src="../img/jira-watcher.png" title="JIRA Watcher" >}}

By clicking the watcher bubble you can see who is following the ticket. Here you can add or remove watchers. Please note that you can only add users who are entitled Camunda enterprise support contacts, otherwise you will get an error message stating that the user with that email address is not found.

