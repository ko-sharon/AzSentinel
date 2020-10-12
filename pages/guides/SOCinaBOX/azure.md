---
title: "SOC in a Box - Azure Package"
keywords: coming soon
tags: [quickstart]
sidebar: mydoc_sidebar
permalink: SOCinaBOX_azure.html
toc: false
---

## Azure Content Package

Common Azure services data (e.g. Azure Activity, Azure Security Center, Azure Firewall, etc.)

<ul id="profileTabs" class="nav nav-tabs">
    <li class="active"><a class="noCrossRef" href="#connectors" data-toggle="tab">Connectors</a></li>
    <li><a class="noCrossRef" href="#analyticsrules" data-toggle="tab">Analytics Rules</a></li>
    <li><a class="noCrossRef" href="#workbooks" data-toggle="tab">Workbooks</a></li>
</ul>
  <div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="connectors" markdown="1">
## Connectors

* Azure Activity
* Azure Security Center
* Azure Security Center for IoT
* Azure Active Directory
* Azure Firewall
* Azure Web Application Firewall
* Security Events

</div>

<div role="tabpanel" class="tab-pane" id="analyticsrules">
    <h2>Analytics </h2>
<ul>
<li> Advanced Multistage Attack Detection</li>
<li> Suspicious number of resource creation or deployment activies</li>
<li> Suspicious granting of permissions to an account</li>
<li> Process execution frequency anomaly</li>
<li> RDP Nesting</li>
<li> Security Event log cleared</li>
<li> Group added to built in domain local or global group</li>
<li> Powershell Empire cmdlets seen in command line</li>
<li> User account enabled and disabled within 10 mins</li>
<li> Rare RDP Connections</li>
<li> Scheduled Security Events</li>
<li> AD account with don't expire password - disabled</li>
<li> Known Phosphorus group domains/IP</li>
<li> Known IRIDIUM IP</li>
<li> Known GALLIUM domains and hashes</li>
<li> Known Strontium group domains</li>
<li> Anomalous sign-in location by user account and authenticating application</li>
<li> Suspicious application consent similar to PwnAuth</li>
<li> Distributed Password cracking attempts in AzureAD</li>
<li> Sign-ins from IPs that attempt sign-ins to disabled accounts</li>
    </ul>
</div>

<div role="tabpanel" class="tab-pane" id="workbooks">
    <h2>Workbooks</h2>
<ul>
<li> Security Operations Efficiency</li>
<li> Azure Activity</li>
<li> ASC Compliance and Protection</li>
<li> Azure AD Audit, Activity and Sign-in logs</li>
<li> Insecure Protocols</li>
<li> Identity & Access</li>
</ul>
</div>
</div>


