---
title: "What is SOC in a Box?"
keywords: SOCinaBox
tags: [quickstart]
sidebar: mydoc_sidebar
permalink: SOCinaBOX_overview.html
toc: false
---

## Rationale
While tailored SIEM implementations are immensely beneficial to an enterprise (and we continue to strive towards that), however there may be instances where an enterprise could be:
* <b>New to SIEM</b> and would like to know how to quickly extract value from data
* <b>New to Azure Sentinel</b> and would like to learn how to navigate within the product and assess its features

The intention of SOC in a Box is to provide guidance around what configurations can be made within Azure Sentinel, reducing the time to deploy and ensuring a structured outcome. The content packages outline which Connectors, Analytics Rules and Workbooks should be enabled - depending on the data sources an enterprise has, one or more content packages can be deployed. 

<table>
<colgroup>
<col width="30%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Content Package</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span"><a alt='Azure' href='https://ko-sharon.github.io/AzSentinel/SOCinaBOX_azure.html'>Azure</a></td>
<td markdown="span">Common Azure services data (e.g. Azure Activity, NSG Flow logs, diagnostic logs, etc.)</td>
</tr>
<tr>
<td markdown="span"><a alt='M365' href='https://ko-sharon.github.io/AzSentinel/SOCinaBOX_m365.html'>M365</a></td>
<td markdown="span">Common Microsoft suite data sources (e.g. AAD, Office 365, MTP solutions, etc)</td>
</tr>
<tr>
<td markdown="span"><a alt='Infra' href='https://ko-sharon.github.io/AzSentinel/SOCinaBOX_infra.html'>Infrastructure</a></td>
<td markdown="span">Common infrastructure data sources (e.g. Windows Security Events, Syslog, etc.)</td>
</tr>
</tbody>
</table>

In these content packages, only a subset of all the native Connectors / Analytics Rules / Workbooks are enabled, these are the typically essential ones (based on a generic enterprise profile) - the remainder can always be enabled if deemed relevant.

For content packages on more advanced use cases, refer to the `Advanced Content` section in the navigation bar on the left.

![alt text](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/SOCinaBOX/SOCinaBOX.svg?raw=true)

