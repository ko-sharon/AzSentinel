---
title: "SOC in a Box - Infrastructure Package"
keywords: coming soon
tags: [quickstart]
sidebar: mydoc_sidebar
permalink: SOCinaBOX_infra.html
toc: false
---

## Infrastructure Content Package

Common infrastructure data sources (e.g. Windows Security Events, Syslog, etc.)

For a quickstart guide on how to enable Data Connectors / Analytics Rules / Workbooks, click <a alt='implementation' href='https://ko-sharon.github.io/AzSentinel/guides_implementation.html'>here</a>.

<ul id="profileTabs" class="nav nav-tabs">
    <li class="active"><a class="noCrossRef" href="#connectors" data-toggle="tab">Connectors</a></li>
    <li><a class="noCrossRef" href="#analyticsrules" data-toggle="tab">Analytics Rules</a></li>
    <li><a class="noCrossRef" href="#workbooks" data-toggle="tab">Workbooks</a></li>
</ul>
  <div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="connectors" markdown="1">
## Connectors

* Amazon Web Services
* DNS
* Security Events
* Syslog
* Windows Firewall
* Azure Active Directory

</div>

<div role="tabpanel" class="tab-pane" id="analyticsrules">
    <h2>Analytics </h2>
<ul>
<li> Advanced Multistage Attack Detection</li>
<li> Known Phosphorus group domains/IP</li>
<li> Known IRIDIUM IP</li>
<li> Known GALLIUM domains and hashes</li>
<li> Known Strontium group domains</li>
<li> Full Admin policy created and then attached to Roles, Users or Groups</li>
<li> Monitor AWS Credential abuse or hijacking</li>
<li> Changes to internet facing AWS RDS Database instances</li>
<li> Anomalous sign-in location by user account and authenticating application</li>
<li> Suspicious application consent similar to PwnAuth</li>
<li> Distributed Password cracking attempts in AzureAD</li>
<li> Sign-ins from IPs that attempt sign-ins to disabled accounts</li>
<li> Time series anomaly for data size transferred to public internet</li>
<li> High count of connections by client IP on many ports</li>
<li> Potential DGA detected</li>
<li> Rare client observed with high reverse DNS lookup count</li>
<li> Process execution frequency anomaly</li>
<li> RDP Nesting</li>
<li> Security Event log cleared</li>
<li> Group added to built in domain local or global group</li>
<li> Powershell Empire cmdlets seen in command line</li>
<li> User account enabled and disabled within 10 mins</li>
<li> Rare RDP Connections</li>
<li> Scheduled Security Events</li>
<li> Network endpoint to host executable correlation</li>
<li> AD account with don't expire password - disabled</li>
<li> New internet-exposed SSH endpoints</li>
<li> Anomalous SSH Login Detection</li>
    </ul>
</div>

<div role="tabpanel" class="tab-pane" id="workbooks">
    <h2>Workbooks</h2>
<ul>
<li> Security Operations Efficiency</li>
<li> Azure AD Audit, Activity and Sign-in logs</li>
<li> AWS Network Activities</li>
<li> AWS User Activities</li>
<li> DNS</li>
<li> Event Analyzer</li>
<li> Identity & Access</li>
<li> Insecure Protocols</li>
<li> Security Status</li>
</ul>
</div>
</div>


