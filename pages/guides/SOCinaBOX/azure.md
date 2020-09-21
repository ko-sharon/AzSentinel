---
title: "SOC in a Box - Azure Package"
keywords: coming soon
tags: [quickstart]
sidebar: mydoc_sidebar
permalink: SOCinaBOX_azure.html
toc: false
---

## Azure Content Package

Common Azure services data (e.g. Azure Activity, NSG Flow logs, diagnostic logs, etc.).

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
    <h2>Analytics Rules</h2>

* Advanced Multistage Attack Detection
* Suspicious number of resource creation or deployment activies
* Suspicious granting of permissions to an account
* Process execution frequency anomaly
* RDP Nesting
* Security Event log cleared
* Group added to built in domain local or global group
* Powershell Empire cmdlets seen in command line
* User account enabled and disabled within 10 mins
* Rare RDP Connections
* Scheduled Security Events
* AD account with don't expire password - disabled
* Known Phosphorus group domains/IP
* Known IRIDIUM IP
* Known GALLIUM domains and hashes
* Known Strontium group domains
* Anomalous sign-in location by user account and authenticating application
* Suspicious application consent similar to PwnAuth
* Distributed Password cracking attempts in AzureAD
* Sign-ins from IPs that attempt sign-ins to disabled accounts

</div>

<div role="tabpanel" class="tab-pane" id="workbooks">
    <h2>Workbooks</h2>

* Security Operations Efficiency
* Azure Activity
* ASC Compliance and Protection
* Azure AD Audit, Activity and Sign-in logs
* Insecure Protocols
* Identity & Access

</div>
</div>


