<center>

[![PowerShellGallery Version](https://img.shields.io/powershellgallery/v/PSWinReportingV2.svg?style=for-the-badge)](https://www.powershellgallery.com/packages/PSWinReportingV2)

[![PowerShellGallery Platform](https://img.shields.io/powershellgallery/p/PSWinReportingV2.svg?style=for-the-badge)](https://www.powershellgallery.com/packages/PSWinReportingV2)
[![PowerShellGallery Preview Version](https://img.shields.io/powershellgallery/vpre/PSWinReportingV2.svg?label=powershell%20gallery%20preview&colorB=yellow&style=for-the-badge)](https://www.powershellgallery.com/packages/PSWinReportingV2)

![Top Language](https://img.shields.io/github/languages/top/evotecit/PSWinReporting.svg?style=for-the-badge)
![Code](https://img.shields.io/github/languages/code-size/evotecit/PSWinReporting.svg?style=for-the-badge)
[![PowerShellGallery Downloads](https://img.shields.io/powershellgallery/dt/PSWinReportingV2.svg?style=for-the-badge)](https://www.powershellgallery.com/packages/PSWinReportingV2)

</center>

# PSWinReporting

**PSWinReporting** is a little PowerShell module that solves problem of monitoring and reading **Windows Events**. It allows you to set up monitoring of **Domain Controllers** (and from **2.X** any other servers) for events that happen on them. By default it comes with **built-in Active Directory** events supports, but since **2.0** you can configure it to monitor basically anything. You can set up reporting on any types of events and have emails delivered with summary of hourly, daily, weekly, monthly or quarterly changes. It also supports sending notifications to Microsoft Teams, Slack, and Discord. Make sure to go thru related articles as they have all the KNOW HOW which is quite useful if you want to get everything from this module.

Full project description is available at my website - [Full project description](https://evotec.xyz/hub/scripts/pswinreporting-powershell-module/).

Currently there are 2 branches of of PSWinReporting

- [x] Legacy branch - available in PS Gallery as [PSWinReporting](https://www.powershellgallery.com/packages/PSWinReporting/) - `Install-Module -Name 'PSWinReporting' -Force`
- [x] Master branch - available in PS Gallery as [PSWinReportingV2](https://www.powershellgallery.com/packages/PSWinReportingV2/) - `Install-Module -Name 'PSWinReportingV2' -Force`

I've decided that both PowerShell modules can coexist together, especially foor scenarios for people who want to switch, but don't want to do it right away. This way you can keep using old version as is, and slowly fix your other stuff, or use new `Find-Events` command. Commands are slightly renamed for V2 release.

## PSWinReportingV2 - Master Edition

Master edition is complete rewrite and a new beginning. It provides same functionality as **Legacy 1.X** version and then some more.

- [x] Ability to translate report and have it suite your needs
- [x] Ability to completely modify events monitoring
- [x] Ability to monitor any servers, for any events using simple to use schema
- [x] Ability to target multiple servers, computers or files at the same time

At this moment there is no documentation for PSWinReportingV2 except for those articles below. Feel free to explore Examples if you're eager to try new version. Otherwise fallback to PSWinReporting **Legacy Edition**.

- [x] [Find-Events - The only PowerShell Command you will ever need to find out who did what in Active Directory](https://evotec.xyz/the-only-powershell-command-you-will-ever-need-to-find-out-who-did-what-in-active-directory/)


### Built-in Active Directory Reports

PSWinReporting comes with predefined, built-in reports. They are used for `Find-Events`. Those also come defined in example configuration script which you can use straight away after verifying everything is as per your requirement.

- [x] ComputerChangesDetailed
- [x] ComputerCreatedChanged
- [x] ComputerDeleted
- [ ] EventsReboots - least prepared report. Not really useful at this moment.
- [x] GroupChanges
- [x] GroupChangesDetailed
- [x] GroupCreateDelete
- [x] GroupEnumeration
- [x] GroupMembershipChanges
- [x] GroupPolicyChanges
- [x] LogsClearedOther
- [x] LogsClearedSecurity
- [x] UserChanges
- [x] UserChangesDetailed
- [x] UserLockouts
- [x] UserLogon
- [x] UserLogonKerberos
- [x] UserStatus
- [x] UserUnlocked


### Built-in Reporting Times

PSWinReporting comes with predefined report times. This means you can simply use **True/False** to enable/disable report or in case of `Find-Events` simply choose it from a list

- [x] CurrentDay
- [x] CurrentDayMinusDayX
- [x] CurrentDayMinuxDaysX
- [x] CurrentHour
- [x] CurrentMonth
- [x] CurrentQuarter
- [x] CustomDate
- [x] Everything
- [x] Last14days
- [x] Last3days
- [x] Last7days
- [x] OnDay
- [x] PastDay
- [x] PastHour
- [x] PastMonth
- [x] PastQuarter


## PSWinReporting - Legacy Edition

***Legacy edition*** will continue it's life as ***1.X.X***. If you want to keep on using it, feel free, but it's highely encouraged to use ***2.x.x*** when it's fully functional with all features. Code is available as [Legacy Branch](https://github.com/EvotecIT/PSWinReporting/tree/Legacy). Following links can help understanding how it works and how to set it up:

-   [Review of features coming in 2.0 along with some features description for the current version](https://evotec.xyz/pswinreporting-1-8-split-of-branches-legacy-vs-new-hope/) - Overview of configuration and features.
-   [Review of new features in PSWinReporting 1.7](https://evotec.xyz/pswinreporting-forwarders-microsoft-teams-slack-microsoft-sql-and-more/) - Lots of changes, review required. Microsoft Teams, Slack, SQL and forwarders support
-   [Review of new features in PSWinReporting 1.0](https://evotec.xyz/pswinreporting-1-0-is-out/) - Lots of changes, review required.
-   [Last version of Get-EventsLibrary.ps1](https://evotec.xyz/get-eventslibrary-ps1-monitoring-events-powershell/) - This is actual code base for the old version. Just in caseâ€¦
-   [Blog post about version 0.8](https://evotec.xyz/whats-new-event-monitoring-0-8/) - Updates from feedback. Last version before name change.
-   [Blog post about version 0.7](https://evotec.xyz/whats-new-event-monitoring-v0-7/) - Updates from feedback.
-   [Blog post about version 0.6](https://evotec.xyz/whats-new-event-monitoring-v0-6/) - Updates from feedback.
-   [Blog post about initial version and the differences in monitoring approach](https://evotec.xyz/monitoring-active-directory-changes-on-users-and-groups-with-powershell/)

Following AD Events are supported:

-   [x] Group create, delete, modify (Who / When / What)
-   [x] Group membership changes (Who / When / What)
-   [x] User changes (Who / When / What)
-   [x] User created / deleted (Who / When)
-   [x] User password changes (Who / When)
-   [x] User lockouts (Who / When / Where)
-   [x] Computer Created / Modified (Who / When / Where)
-   [x] Computer Deleted (Who / When / Where)
-   [x] Event Log Backup (Who / When)
-   [x] Event Log Clear (Who / When)

Features:

-   [x] Support for Event Forwarding - monitoring one event log instead of scanning all domain controllers
-   [x] Support for Microsoft Teams - Sending events as they happen to Microsoft Teams (only supported when forwarders are in use)
-   [x] Support for Slack - Sending events as they happen to Slack (only supported when forwarders are in use)
-   [x] Support for Microsoft SQL - Sending events directly to SQL (some people prefer it that way)
-   [x] Support for backing up old archived logs (moves logs from Domain Controllers into chosen place)
-   [x] Support for re-scanning logs from files - a way to recheck your logs for missing information

### Example - Script running

![image](https://evotec.xyz/wp-content/uploads/2018/06/2018-06-10_11-20-08.gif.pagespeed.ce.xrLSOGTIkk.gif)

### Example - Email Report

![image](https://evotec.xyz/wp-content/uploads/2018/06/PSWinReporting1.0-Example1.png)

### Example - Microsoft Teams

![image](https://evotec.xyz/wp-content/uploads/2018/09/img_5b9e830101081.png)

### Example - Slack

![image](https://evotec.xyz/wp-content/uploads/2018/09/img_5b9e7041638f5.png)
