---
title: "Azure Sentinel 5-Minute Implementation"
keywords: implementation
tags: [quickstart]
sidebar: mydoc_sidebar
permalink: guides_implementation.html
---

{% include note.html content="This repository is a community project and does not serve as official Microsoft documentation - feedback and comments are much appreciated. For official Azure Sentinel documentation, <a alt='Azure Sentinel Documentation' href='https://docs.microsoft.com/en-us/azure/sentinel/'>click here</a>." %}

## Overview

These brief instructions will help you get started quickly with Azure Sentinel - ie. a simple and typical deployment. For more advanced deployments, additional considerations may need to be made, refer to <a alt='techcommunitypost' href='https://techcommunity.microsoft.com/t5/azure-sentinel/best-practices-for-designing-an-azure-sentinel-or-azure-security/ba-p/832574'>this techcommunity post</a> for more.

### 1 - Creating a Workspace

<table>
<colgroup>
<col width="10%" />
<col width="30%" />
<col width="60%" />
</colgroup>
<thead>
<tr class="header">
<th>Step</th>
<th>Illustration</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">1A</td>
<td markdown="span">Navigate to <a alt='azureportal' href='https://portal.azure.com'>portal.azure.com</a></td>
<td markdown="span">
![1a](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1a.png?raw=true)</td>
</tr>
<tr>
<td markdown="span">1B</td>
<td markdown="span">In the search bar, type `Azure Sentinel`</td>
<td markdown="span">![1b](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1b.png?raw=true)</td></td>
</tr>
<tr>
<td markdown="span">1C</td>
<td markdown="span">Click on `Add`</td>
<td markdown="span">![1c](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1c.png?raw=true)</td></td>
</tr>
<tr>
<td markdown="span">1D</td>
<td markdown="span">Create a new workspace</td>
<td markdown="span">![1d](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1d.png?raw=true)</td></td>
</tr>
<tr>
<td markdown="span">1E</td>
<td markdown="span">Specify the **Subscription**, **Resource Group**, **Instance Name** and **Region**.</td>
<td markdown="span">![1e](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1e.png?raw=true)</td></td>
</tr>
<tr>
<td markdown="span">1F</td>
<td markdown="span">**Pay-as-you-go** is the default pricing tier, you can switch to **Capacity Reservation** later if necessary, see <a alt='capres' href='https://ko-sharon.github.io/AzSentinel/guides_capres.html'>here</a>.</td>
<td markdown="span">![1f](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1f.png?raw=true)</td></td>
</tr>
<tr>
<td markdown="span">1G</td>
<td markdown="span">[optional] Specify tags if relevant.</td>
<td markdown="span">![1g](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1g.png?raw=true)</td></td>
</tr>
<tr>
<td markdown="span">1H</td>
<td markdown="span">Click **Create** after validation has passed.</td>
<td markdown="span">![1h](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1h.png?raw=true)</td></td>
</tr>
<tr>
<td markdown="span">1I</td>
<td markdown="span">Click **Add** once the new instance appears.</td>
<td markdown="span">![1i](https://github.com/ko-sharon/AzSentinel/blob/gh-pages/images/guides/implementation/config_1i.png?raw=true)</td></td>
</tr>
</tbody>
</table>

