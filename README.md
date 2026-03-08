# Application Manager
The Application Manager plugin provides centralized management and an overview of all accounts in the application process.


Main features include:

- Overview of all application accounts

- Individual checklist for the application process

- Automatic acceptance tool (WoB) that accepts applications and moves accounts to the appropriate group


All three features can be individually enabled or disabled in the plugin settings.

## Overview of all accounts in the application process
The plugin creates a dedicated overview page displaying all accounts in the application process. These are divided into two groups:

- <b>Application Pending</b> - Accounts that have not yet created an application topic in the designated area appear here.

- <b>Under Correction</b> - Accounts whose application topic has already been created in the designated area appear here.


The overview displays important information:

- How many days remain on the deadline
- How many extensions have already been made
- Which team member is making the correction

In the settings, you can:

- completely disable the option to extend the deadline
- set the maximum number of extensions
- configure whether users can extend the deadline themselves
- whether users can see the number of extensions made by other accounts

Additionally, a <b>correction period</b> can be activated. This starts automatically as soon as a team member creates a correction post in the application thread (via a special input option when submitting a post). Here, too, you can optionally specify whether users can extend the deadline themselves.

As soon as a team member takes over an application, this is also displayed in the overview. If desired, you can specify in the settings how many days team members have to address each application. If this deadline is missed, a notification banner will automatically appear for the relevant team member to ensure no application is overlooked.

In addition, automatic banner notifications can be set up to inform users well in advance of the application or revision deadline.

In the ACP (RPG Extensions » Accounts in the Application Process), you can also edit the data of individual accounts – deadline dates, number of extensions, or the assigned team member. This simplifies management for individual requests and eliminates the need to access the database.

### Note!

This overview and management feature is not compatible with the <a href="https://github.com/katjalennartz/application_ucp" target="_blank">Profiles in the UCP of risuena</a>.

## Checklist
The plugin offers a flexible checklist function that allows you to make certain information mandatory for accounts in the application process. Each person in the application process sees a personal to-do list in the forum header, indicating which tasks set by the team still need to be completed. This allows applicants to keep track of what they still need to do. The checklist colors are entirely controlled via CSS and can be customized to match your forum's design. The checkmarks and crosses are simple symbols treated like text characters. These symbols can be modified and replaced in the language file if needed. The checklist is fully configured via the ACP (RPG Extensions » Application Checklist). It is organized into groups, each containing its own items.<br>
<br>
<b>Example:</b>

- Group: Graphics - Items: Avatar, Mini Icon, Profile Banner

- Group: Personal - Items: Nickname, Posting Frequency, Discord Tag<br>

<br>

<b>Groups have:</b><br>
- a title
- optional description (HTML is allowed)
- a freely definable sort order<br>

<br>

<b>Items have:</b><br>

- their own title
- a sort order within the group
- a data collection option

<br>

<b>Data Collection Options for Items</b><br>
For each checklist item, you can define <b>how it is checked</b> whether it is fulfilled:<br>
- Profile field (MyBB)

- Brief field (<a href="https://github.com/katjalennartz/application_ucp" Profiles in the UCP - risuena)

- Birthday field (MyBB)

- Upload element (<a href="https://github.com/little-evil-genius/Upload-System" target="_blank">Upload system - little.evil.genius</a>)

- Custom PHP query - for more customized checks (e.g., job lists)

### Custom PHP queries (for special cases)
Not all information can be checked with the standard options. For such cases, you can define your own database queries. Example: <a href="https://github.com/katjalennartz/jobliste/tree/main" target="_blank">Job list from risuena</a><br>

- Database tagbelle: Name of the table where the entries are stored (jl_entry)

- UID column: Name of the column where the user IDs are stored (je_uid)

- Validation column: Name of the column used to check if an entry exists (je_position)

- Multiple entry (optional): Specifies how many times an entry must occur (e.g., 2 for two jobs). If left blank, one entry is sufficient.




``` ### Dependencies between Group Points and Profile Information

Many forums have applicants with different groups (e.g., werewolves, witches, vampires) who must provide specific information.

This plugin allows you to display points within a group based on specific profile information.

Example:

- Werewolves - Required fields: Imprint, Species, Rank
- Witches - Required fields: Magic Type, Animal

- Vampires - Required fields: Transformation Day, Ability

How it works:

- Activate the "Specific Checklist Points" option for the group.

- Select a profile field or character sheet field as the selection source.

- For each item in this group, specify the condition for which field value it should appear (e.g., "Witch").

A selection field with fixed values ​​is best to avoid typos and inconsistent entries. This ensures that the applicant only sees the items relevant to their selection during the application process.

### Note!

The checklist can be easily combined with the <a href="https://github.com/katjalennartz/application_ucp" target="_blank">profiles in risuena's UCP</a>.

## Automatic WoB Tool
The automatic WoB tool ("Welcome on Board") allows you to accept applicants with just one click.

The WoB tool is displayed at the end of the application thread. If a specific team member has already been assigned to an application, the tool is only visible to that team member. If no team member is specified, all team members with the appropriate permissions can view and use the tool.

The following functions are available:

- Change user groups: During the WoB process, the primary user group of the account is automatically changed from the application group to the defined target group for accepted accounts. Secondary groups can also be automatically adjusted if needed.

- Post automatic reply: Optionally, a reply can be automatically posted to the application thread during the WoB (Word of Mouth) process.

There are two options:

1. A fixed text, defined in the settings, is posted directly.

2. A pre-written text that the team member can edit before posting – this allows flexibility to add, for example, individual greetings or notes.

Save WoB date:

You can specify a column in the users table to save the date of the WoB entry. This allows you to track when the account was accepted at any time.

### Note!

The WoB tool is not compatible with the <a href="https://github.com/katjalennartz/application_ucp" target="_blank">profiles in the risuena UCP</a>.


# Prerequisite

- The ACP module <a href="https://github.com/little-evil-genius/rpgstuff_modul" target="_blank">RPG Stuff</a> must be installed.

- The <a href="https://doylecc.altervista.org/bb/downloads.php?dlid=26&cat=2" target="_blank">Accountswitcher</a> from doylecc must be installed.

# Transferring Applicants from Other Systems
If your forum previously used a different plugin for managing applicants, this plugin offers a simple way to transfer existing data to the new system. Currently, transfers from the following plugins are supported:

- <a href="https://github.com/aheartforspinach/Bewerberuebersicht">Applicant Overview from aheartforspinach</a>
- <a href="https://github.com/Ales12/applicationoverview">Applicant Overview from Ales</a>

To perform the transfer, proceed as follows:


1. Navigate to the transfer page: In the ACP, you will find the menu item "Transfer Applicants" in the "RPG Extensions" module. Click on this item to open the transfer page.

2. Select the old plugin: On the transfer page, you can select the system from which you want to transfer the data. Select the appropriate plugin and continue.<br><br>
3. <b>Complete the transfer process:</b><br>After you have selected the plugin, the transfer process will begin. All relevant data will be automatically transferred to the new database table. You will receive a confirmation once the transfer is complete. Always report any problems in the SG support thread!<br><br>
4. <b>Uninstall the old system:</b><br>After the transfer has been successfully completed, you can safely uninstall the old system, as all data has now been transferred to the new one.New plugins have been transferred.

# Database Changes
Added table:

- application_checklist_fields
- application_checklist_groups
- application_manager

# New language files
- deutsch_du/admin/application_manager.lang.php
- deutsch_du/application_manager.lang.php

<br>
<b>NOTE:</b><br>
This can also be used for deutsch_sie if the ACP and forum are not running in deutsch_du.



# Database Changes

Added table:

- application_manager.lang.php ... # Settings
- Application group
- Team group
- Excluded accounts
- Application forum
- Nickname
- Application checklist
- Application deadlines
- Application period
- Application extension period
- Maximum number of application deadline extensions
- Self-extension
- Visible application deadline extensions
- Notification of expiring application deadline
- Correction deadline
- Correction period
- Correction deadline extension period
- Maximum number of correction deadline extensions
- Self-extension
- Visible correction deadline extensions
- Notification of expiring correction deadline
- Team reminder for open applications
- Automatic WoB
- Primary groups
- Secondary groups
- Automatic acceptance text
- Acceptance text
- Save WoB date<br>
<br>
<b>NOTE:</b><br>

The plugin is compatible with the classic MyBB profile fields and/or the <a href="https://github.com/katjalennartz/application_ucp">Risuena profile plugin</a>.

# New template group within the design templates
- Application manager

# New templates (not global!)
- applicationmanager_banner
- applicationmanager_checklist
- applicationmanager_checklist_banner
- applicationmanager_checklist_group
- applicationmanager_checklist_points
- applicationmanager_forumdisplay_button
- applicationmanager_forumdisplay_corrector
- applicationmanager_overview
- applicationmanager_overview_correction
- applicationmanager_overview_correction_legend
- applicationmanager_overview_correction_legend_period
- applicationmanager_overview_correction_period
- applicationmanager_overview_none
- applicationmanager_overview_open
- applicationmanager_showthread_correction
- applicationmanager_showthread_corrector
- applicationmanager_wob
- applicationmanager_wob_additionalgroup
- applicationmanager_wob_text
- applicationmanager_wob_usergroup<br><br>
<b>NOTE:</b><br>

All templates were largely coded without a table structure. The layout has been adapted to a MyBB default design.

# New Variables

- forumdisplay_thread: {$applicationPlus} & {$application_corrector}

- header: {$application_checklist} & {$application_openAlert} & {$application_team_reminder} & {$application_deadline_reminder} & {$application_expired}

- newreply: {$application_correction}

- showthread: {$application_wob} & {$application_corrector} & {$application_correction}

- editpost: {$application_hidden}

# New CSS - application_manager.css

It will be automatically added to every existing and new design. It's a good idea to save it – even in the default design. Is the stylesheet missing from the master style after a MyBB upgrade? In the ACP module "RPG Extensions," you'll find the menu item "Check Stylesheets" and can add the stylesheet from any installed plugins.

``css

.application_manager_checklist {

background: #fff;

width: 100%;

margin: auto auto;

border: 1px solid #ccc;

padding: 1px;

-moz-border-radius: 7px;

-webkit-border-radius: 7px;

border-radius: 7px;

}

.application_manager_checklist-headline {

background: #0066a2 url(../../../images/thead.png) top left repeat-x;

color: #ffffff;

border-bottom: 1px solid #263c30;

padding: 8px; 
-moz-border-radius-topleft: 6px; 
-moz-border-radius-topright: 6px; 
-webkit-border-top-left-radius: 6px; 
-webkit-border-top-right-radius: 6px; 
border-top-left-radius: 6px; 
border-top-right-radius: 6px;
}

.application_manager_checklist-headline span { 
font-size: 10px;
}

.application_manager_checklist-headline a:link,
.application_manager_checklist-headline a:visited,
.application_manager_checklist-headline a:active,
.application_manager_checklist-headline a:hover { 
color: #ffffff;
}

.application_manager_checklist-group { 
background: #f5f5f5; 
border: 1px solid; 
border-color: #fff #ddd #ddd #fff; 
padding: 5px 10px; 
display: flex; 
align-items: center; 
flex-wrap: nowrap; 
justify-content: flex-start; 
gap: 5px;
}

.application_manager_checklist-group_status { 
width: 2%; 
text-align: center; 
font-size: 20px;
}

.application_manager_checklist-group_content-points { 
font-size: 11px;
}

.application_manager_checklist_groupUncheck,
.application_manager_checklist_fieldUncheck { 
color: #c80000;
}

.application_manager_checklist_groupCheck,
.application_manager_checklist_fieldCheck { 
color: #15a200;
}

.application_manager_smalltext { 
font-size: 11px;
}

.application_manager_overview-desc { 
text-align: justify; 
line-height: 180%; 
padding: 20px 40px; 
background: #f5f5f5; 
border: 1px solid; 
border-color: #fff #ddd #ddd #fff;
}

.application_manager_overview_legend { 
background: #0f0f0f url(../../../images/tcat.png) repeat-x; 
color: #fff; 
border-top: 1px solid #444; 
border-bottom: 1px solid #000; 
padding: 7px; 
display: flex; 
flex-wrap: nowrap; 
justify-content: space-between; 
gap: 10px;
}

.application_manager_overview_applications { 
display: flex; 
flex-wrap: nowrap; 
justify-content: space-between; 
gap: 10px; 
padding: 7px; 
text-align: center; 
background: #f5f5f5; 
border: 1px solid; 
border-color: #fff #ddd #ddd #fff;
}
.application_manager_overview_legend_div,
.application_manager_overview_applications_div { 
width: 100%;
}

.application_manager_wob_headline { 
background: #0066a2 url(../../../images/thead.png) top left repeat-x; 
color: #ffffff; 
border-bottom: 1px solid #263c30; 
padding: 8px; 
-moz-border-radius-topleft: 6px; 
-moz-border-radius-topright: 6px; 
-webkit-border-top-left-radius: 6px; 
-webkit-border-top-right-radius: 6px; 
border-top-left-radius: 6px; 
border-top-right-radius: 6px;
}

.application_manager_wob { 
display: flex; 
flex-wrap: nowrap; 
justify-content: center; 
gap: 20px; 
text-align: left; 
margin-bottom: 10px;
}

.application_manager_wob-textarea { 
background: #f5f5f5; 
border: 1px solid; 
border-color: #fff #ddd #ddd #fff; 
text-align: center; 
padding: 5px; 
-moz-border-radius-bottomright: 6px; 
-webkit-border-bottom-right-radius: 6px; 
border-bottom-right-radius: 6px; 
-moz-border-radius-bottomleft: 6px; 
-webkit-border-bottom-left-radius: 6px; 
border-bottom-left-radius: 6px;
}

.application_manager-accpop { 
position: fixed; 
top: 0; 
left: 0; 
width: 100%; 
height: 100%; 
background: rgba(0, 0, 0, 0.6); 
display: none; 
align-items: center; 
justify-content: center; 
z-index: 9999;
}

.application_manager-accpop:target { 
display: flex;
}

.application_manager-pop { 
width: 400px; 
text-align: left; 
background: #fff; 
display: inline-block; 
vertical-align: middle; 
position: relative; 
z-index: 2; 
-webkit-box-sizing: border-box; 
-moz-box-sizing: border-box; 
box-sizing: border-box; 
-webkit-border-radius: 8px; 
-moz-border-radius: 8px; 
-o-border-radius: 8px; 
-ms-border-radius: 8px; 
border-radius: 8px; 
-webkit-box-shadow: 0 0 10px #000; 
-moz-box-shadow: 0 0 10px #000; 
-o-box-shadow: 0 0 10px #000; 
-ms-box-shadow: 0 0 10px #000; 
box-shadow: 0 0 10px #000; 
animation: fadeInScale 0.3s ease-out;
}

.application_manager-closepop { 
position: absolute; 
top: -12.5px; 
right: -12.5px; 
display: block; 
width: 30px; 
height: 30px; 
text-indent: -9999px; 
background: url(../../../images/close.png) no-repeat 0 0;
}

@keyframes fadeInScale { 
from { 
opacity: 0; 
transform: scale(0.9); 
} 
to { 
opacity: 1; 
transform: scale(1); 
}

}

```

# Setting User Group Permissions

To ensure all admin accounts have access to manage the checklist and applicants in the ACP, the permissions must be adjusted once under the Users & Groups » Administrator Permissions » User Group Permissions tab. The permissions for the Application Manager are located in the 'RPG Extensions' tab.


` ... # Links
<b>ACP</b><br>
index.php?module=rpgstuff-application_manager<br>
index.php?module=rpgstuff-application_manager_user<br>
<br>
<b>Overview of all accounts in the application process</b><br>
misc.php?action=application_manager

# Demo
## Checklist
<img src="https://stormborn.at/plugins/application_manager_checkliste_acp.png">
<img src="https://stormborn.at/plugins/application_manager_checkliste_index.png">
<img src="https://stormborn.at/plugins/application_manager_checkliste_contentfield.png">

## Overview
<img src="https://stormborn.at/plugins/application_manager_overview_acp.png">
<img src="https://stormborn.at/plugins/application_manager_overview.png">

## WoB tool
<img src="https://stormborn.at/plugins/application_manager_wob.png">
