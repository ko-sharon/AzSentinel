---
title: "Authentication"
sidebar: mydoc_sidebar
permalink: schema_authentication.html
toc: true
---

## SecurityEvent Authentication

### Audit Logon Activities
Within the windows SecurityEvent logs, there are <a alt='auditlogon' href='https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/audit-logon'>a few Event IDs</a> that provide you a view of user attempts (successful or failed) to log on to a computer and how.
* <a alt='EID4624' href='https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4624'>EventID 4624 (S)</a> - An account was successfully logged on.
* <a alt='EID4625' href='https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4625'>EventID 4625 (F)</a> - An account failed to log on.
* <a alt='EID4648' href='https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4648'>EventID 4648 (S)</a> - A logon was attempted using explicit credentials.
* <a alt='EID4675' href='https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4675'>EventID 4675 (S)</a> - SIDs were filtered.

### What does Logon Type mean?
Within these Audit Logon Activities, two other columns of interest exist - (A) LogonType; (B) LogonTypeName. Full reference can be found <a alt='LogonType' href='https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4624#logon-types-and-descriptions'>here</a>.

<table>
<colgroup>
<col width="10%" />
<col width="30%" />
<col width="60%" />
</colgroup>
<thead>
<tr class="header">
<th>LogonType</th>
<th>LogonTypeName</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td markdwn="span">0</td>
<td markdwn="span">System</td>
<td markdwn="span">Used only by the System account, for example at system startup.</td>
</tr>
<tr>
<td markdwn="span">2</td>
<td markdwn="span">Interactive</td>
<td markdwn="span">A user logged on to this computer.</td>
</tr>
<tr>
<td markdwn="span">3</td>
<td markdwn="span">Network</td>
<td markdwn="span">A user or computer logged on to this computer from the network.</td>
</tr>
<tr>
<td markdwn="span">4</td>
<td markdwn="span">Batch</td>
<td markdwn="span">Batch logon type is used by batch servers, where processes may be executing on behalf of a user without their direct intervention.</td>
</tr>
<tr>
<td markdwn="span">5</td>
<td markdwn="span">Service</td>
<td markdwn="span">A service was started by the Service Control Manager.</td>
</tr>
<tr>
<td markdwn="span">7</td>
<td markdwn="span">Unlock</td>
<td markdwn="span">This workstation was unlocked.</td>
</tr>
<tr>
<td markdwn="span">8</td>
<td markdwn="span">NetworkCleartext</td>
<td markdwn="span">A user logged on to this computer from the network. The user's password was passed to the authentication package in its unhashed form. The built-in authentication packages all hash credentials before sending them across the network. The credentials do not traverse the network in plaintext (also called cleartext).</td>
</tr>
<tr>
<td markdwn="span">9</td>
<td markdwn="span">NewCredentials</td>
<td markdwn="span">A caller cloned its current token and specified new credentials for outbound connections. The new logon session has the same local identity, but uses different credentials for other network connections.</td>
</tr>
<tr>
<td markdwn="span">10</td>
<td markdwn="span">RemoteInteractive</td>
<td markdwn="span">A user logged on to this computer remotely using Terminal Services or Remote Desktop.</td>
</tr>
<tr>
<td markdwn="span">11</td>
<td markdwn="span">CachedInteractive</td>
<td markdwn="span">A user logged on to this computer with network credentials that were stored locally on the computer. The domain controller was not contacted to verify the credentials.</td>
</tr>
<tr>
<td markdwn="span">12</td>
<td markdwn="span">CashedRemoteInteractive</td>
<td markdwn="span">Same as RemoteInteractive. This is used for internal auditing.</td>
</tr>
<tr>
<td markdwn="span">13</td>
<td markdwn="span">CachedUnlock</td>
<td markdwn="span">Workstation logon.</td>
</tr>
</tbody>
</table>


## Azure AD Authentication

### SigninLogs - Succeeded or Failed?
Within the Azure AD SigninLogs table, the column ResultType contains the Error Code of the sign in activity. To extend a column signifying whether it was a successful or failed login:

```
// To add a column representing successful / failed login status
SigninLogs
| extend FailureOrSuccess = iff(ResultType in ("0", "50125", "50140", "70043", "70044"), "Success", "Failure")
```

### SigninLogs - Error Code Description
For more information on any specific Error Code, look up the number in <a alt='ErrorCode' href='https://login.microsoftonline.com/error'>this link</a>.

