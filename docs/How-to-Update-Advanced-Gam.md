# Updating GAMADV-XTD3
Use these steps to update your version of GAMADV-XTD3.

- [Downloads](Downloads)
- [GAM Configuration](gam.cfg)
- [Linux and MacOS and Google Cloud Shell](#linux-and-mac-os-and-google-cloud-shell)
- [Windows](#windows)

## Linux and MacOS and Google Cloud Shell

### Download the latest version

This example assumes that GAMADV-XTD3 has been installed in /Users/admin/bin/gamadv-xtd3.
If you've installed GAMADV-XTD3 in another directory, substitute that value in the directions when downloading.

See: [Downloads](Downloads)

In these examples, your Google Super admin is shown as admin@domain.com; replace with the
actual email adddress.

In these examples, the user home folder is shown as /Users/admin; adjust according to your
specific situation; e.g., /home/administrator.

### Update your project with local browser to include the additional APIs that GAMADV-XTD3 uses.
This step may be omitted if you are updating from a recent version.
```
admin@server:/Users/admin/bin/gamadv-xtd3$ gam update project

Enter your Google Workspace admin or GCP project manager email address authorized to manage project(s): gam-project-abc-123-xyz? admin@domain.com

Your browser has been opened to visit:

    https://accounts.google.com/o/oauth2/v2/auth?redirect_uri=http%3A%2F%2Flocalhost%3A8080%2F&response_type=code&client_id=...

If your browser is on a different machine then press CTRL+C,
set no_browser = true in gam.cfg and re-run this command.

Authentication successful.
API: admin.googleapis.com, already enabled...
API: appsactivity.googleapis.com, already enabled...
API: calendar-json.googleapis.com, already enabled...
API: classroom.googleapis.com, already enabled...
API: contacts.googleapis.com, already enabled...
API: drive.googleapis.com, already enabled...
API: gmail.googleapis.com, already enabled...
API: groupssettings.googleapis.com, already enabled...
API: licensing.googleapis.com, already enabled...
API: plus.googleapis.com, already enabled...
API: reseller.googleapis.com, already enabled...
API: siteverification.googleapis.com, already enabled...
API: vault.googleapis.com, already enabled...
Enable 3 APIs
  API: audit.googleapis.com, Enabled (1/3)
  API: groupsmigration.googleapis.com, Enabled (2/3)
  API: sheets.googleapis.com, Enabled (3/3)

admin@server:/Users/admin/bin/gamadv-xtd3$
```
### Update your project without local browser (Google Cloud Shell for instance) to include the additional APIs that GAMADV-XTD3 uses
This step may be omitted if you are updating from a recent version.
```
admin@server:/Users/admin/bin/gamadv-xtd3$ gam config no_browser true save
admin@server:/Users/admin/bin/gamadv-xtd3$ gam update project

Enter your Google Workspace admin or GCP project manager email address authorized to manage project(s): gam-project-abc-123-xyz? admin@domain.com

Go to the following link in a browser on other computer:

    https://accounts.google.com/o/oauth2/v2/auth?redirect_uri=http%3A%2F%2Flocalhost%3A8080%2F&response_type=code&client_id=...

Enter verification code: abc...xyz

Authentication successful.
API: admin.googleapis.com, already enabled...
API: appsactivity.googleapis.com, already enabled...
API: calendar-json.googleapis.com, already enabled...
API: classroom.googleapis.com, already enabled...
API: contacts.googleapis.com, already enabled...
API: drive.googleapis.com, already enabled...
API: gmail.googleapis.com, already enabled...
API: groupssettings.googleapis.com, already enabled...
API: licensing.googleapis.com, already enabled...
API: plus.googleapis.com, already enabled...
API: reseller.googleapis.com, already enabled...
API: siteverification.googleapis.com, already enabled...
API: vault.googleapis.com, already enabled...
Enable 3 APIs
  API: audit.googleapis.com, Enabled (1/3)
  API: groupsmigration.googleapis.com, Enabled (2/3)
  API: sheets.googleapis.com, Enabled (3/3)

admin@server:/Users/admin/bin/gamadv-xtd3$
```
### Update GAMADV-XTD3 client access

You select a list of scopes, GAMADV-XTD3 uses a browser to get final authorization from Google for these scopes and
writes the credentials into the file oauth2.txt.

```
admin@server:/Users/admin/bin/gamadv-xtd3$ ./gam oauth create

Select the authorized scopes by entering a number.
Append an 'r' to grant read-only access or an 'a' to grant action-only access.

[*]  0)  Calendar API (supports readonly)
[*]  1)  Chrome Browser Cloud Management API (supports readonly)
[*]  2)  Chrome Management API - Telemetry read only
[*]  3)  Chrome Management API - read only
[*]  4)  Chrome Policy API (supports readonly)
[*]  5)  Chrome Printer Management API (supports readonly)
[*]  6)  Chrome Version History API
[*]  7)  Classroom API - Course Announcements (supports readonly)
[*]  8)  Classroom API - Course Topics (supports readonly)
[*]  9)  Classroom API - Course Work/Materials (supports readonly)
[*] 10)  Classroom API - Course Work/Submissions (supports readonly)
[*] 11)  Classroom API - Courses (supports readonly)
[*] 12)  Classroom API - Profile Emails
[*] 13)  Classroom API - Profile Photos
[*] 14)  Classroom API - Rosters (supports readonly)
[*] 15)  Classroom API - Student Guardians (supports readonly)
[*] 16)  Cloud Identity Groups API (supports readonly)
[*] 17)  Cloud Storage (Vault Export - read only)
[*] 18)  Contact Delegation API (supports readonly)
[*] 19)  Contacts API - Domain Shared and Users and GAL
[*] 20)  Data Transfer API (supports readonly)
[*] 21)  Directory API - Chrome OS Devices (supports readonly)
[*] 22)  Directory API - Customers (supports readonly)
[*] 23)  Directory API - Domains (supports readonly)
[*] 24)  Directory API - Groups (supports readonly)
[*] 25)  Directory API - Mobile Devices Directory (supports readonly and action)
[*] 26)  Directory API - Organizational Units (supports readonly)
[*] 27)  Directory API - Resource Calendars (supports readonly)
[*] 28)  Directory API - Roles (supports readonly)
[*] 29)  Directory API - User Schemas (supports readonly)
[*] 30)  Directory API - User Security
[*] 31)  Directory API - Users (supports readonly)
[*] 32)  Email Audit API
[*] 33)  Groups Migration API
[*] 34)  Groups Settings API
[*] 35)  License Manager API
[*] 36)  People API (supports readonly)
[*] 37)  People Directory API - read only
[ ] 38)  Pub / Sub API
[*] 39)  Reports API - Audit Reports
[*] 40)  Reports API - Usage Reports
[ ] 41)  Reseller API
[*] 42)  Site Verification API
[*] 43)  Sites API
[*] 44)  Vault API (supports readonly)

     s)  Select all scopes
     u)  Unselect all scopes
     e)  Exit without changes
     c)  Continue to authorization
Please enter 0-44[a|r] or s|u|e|c: c

Enter your Google Workspace admin email address? admin@domain.com

Go to the following link in a browser on this computer or on another computer:

    https://accounts.google.com/o/oauth2/v2/auth?response_type=code&client_id=423565144751-10lsdt2lgnsch9jmdhl35uq4617u1ifp&redirect_uri=http%3A%2F%2F127.0.0.1%3A8080%2F&scope=...

If you use a browser on another computer, you will get a browser error that the site can't be reached AFTER you
click the Allow button, paste "Unable to connect" URL from other computer (only URL data up to &scope required):

Enter verification code or paste "Unable to connect" URL from other computer (only URL data up to &scope required):

The authentication flow has completed.
Client OAuth2 File: /Users/admin/GAMConfig/oauth2.txt, Created

admin@server:/Users/admin/bin/gamadv-xtd3$ 
```
### Update GAMADV-XTD3 service account access.
```
admin@server:/Users/admin/bin/gamadv-xtd3$ ./gam user admin@domain.com check serviceaccount
$ gam user admin@domain.com check serviceaccount
System time status
  Your system time differs from www.googleapis.com by less than 1 second    PASS
Service Account Private Key Authentication
  Authentication                                                            PASS
Service Account Private Key age; Google recommends rotating keys on a routine basis
  Service Account Private Key age: 0 days                                   PASS
Domain-Wide Delegation authentication:, User: admin@domain.com, Scopes: 28
  https://mail.google.com/                                                  PASS (1/28)
  https://sites.google.com/feeds                                            PASS (2/28)
  https://www.googleapis.com/auth/apps.alerts                               PASS (3/28)
  https://www.googleapis.com/auth/calendar                                  PASS (4/28)
  https://www.googleapis.com/auth/classroom.announcements                   PASS (5/28)
  https://www.googleapis.com/auth/classroom.coursework.students             PASS (6/28)
  https://www.googleapis.com/auth/classroom.courseworkmaterials             PASS (7/28)
  https://www.googleapis.com/auth/classroom.profile.emails                  PASS (8/28)
  https://www.googleapis.com/auth/classroom.rosters                         PASS (9/28)
  https://www.googleapis.com/auth/classroom.topics                          PASS (10/28)
  https://www.googleapis.com/auth/cloud-identity                            PASS (11/28)
  https://www.googleapis.com/auth/cloud-platform                            PASS (12/28)
  https://www.googleapis.com/auth/contacts                                  PASS (13/28)
  https://www.googleapis.com/auth/contacts.other.readonly                   PASS (14/28)
  https://www.googleapis.com/auth/datastudio                                PASS (15/28)
  https://www.googleapis.com/auth/directory.readonly                        PASS (16/28)
  https://www.googleapis.com/auth/documents                                 PASS (17/28)
  https://www.googleapis.com/auth/drive                                     PASS (18/28)
  https://www.googleapis.com/auth/drive.activity                            PASS (19/28)
  https://www.googleapis.com/auth/drive.admin.labels                        FAIL (20/28)
  https://www.googleapis.com/auth/drive.labels                              FAIL (21/28)
  https://www.googleapis.com/auth/gmail.modify                              PASS (22/28)
  https://www.googleapis.com/auth/gmail.settings.basic                      PASS (23/28)
  https://www.googleapis.com/auth/gmail.settings.sharing                    PASS (24/28)
  https://www.googleapis.com/auth/keep                                      PASS (25/28)
  https://www.googleapis.com/auth/spreadsheets                              PASS (26/28)
  https://www.googleapis.com/auth/tasks                                     PASS (27/28)
  https://www.googleapis.com/auth/userinfo.profile                          PASS (28/28)
Some scopes FAILED!
To authorize them, please go to:

    https://admin.google.com/ac/owl/domainwidedelegation?clientScopeToAdd=https://mail.google.com/,https://sites.google.com/feeds,https://www.googleapis.com/auth/apps.alerts,https://www.googleapis.com/auth/calendar,https://www.googleapis.com/auth/classroom.announcements,https://www.googleapis.com/auth/classroom.coursework.students,https://www.googleapis.com/auth/classroom.courseworkmaterials,https://www.googleapis.com/auth/classroom.profile.emails,https://www.googleapis.com/auth/classroom.rosters,https://www.googleapis.com/auth/classroom.topics,https://www.googleapis.com/auth/cloud-identity,https://www.googleapis.com/auth/cloud-platform,https://www.googleapis.com/auth/contacts,https://www.googleapis.com/auth/contacts.other.readonly,https://www.googleapis.com/auth/datastudio,https://www.googleapis.com/auth/directory.readonly,https://www.googleapis.com/auth/documents,https://www.googleapis.com/auth/drive,https://www.googleapis.com/auth/drive.activity,https://www.googleapis.com/auth/gmail.modify,https://www.googleapis.com/auth/gmail.settings.basic,https://www.googleapis.com/auth/gmail.settings.sharing,https://www.googleapis.com/auth/keep,https://www.googleapis.com/auth/spreadsheets,https://www.googleapis.com/auth/tasks,https://www.googleapis.com/auth/userinfo.profile,https://www.googleapis.com/auth/userinfo.email&clientIdToAdd=SVCACCTID&overwriteClientId=true&dn=domain.com&authuser=admin@domain.com

You will be directed to the Google Workspace admin console Security/API Controls/Domain-wide Delegation page
The "Add a new Client ID" box will open
Make sure that "Overwrite existing client ID" is checked
Click AUTHORIZE
When the box closes you're done
After authorizing it may take some time for this test to pass so wait a few moments and then try this command again.

admin@server:/Users/admin/bin/gamadv-xtd3$
```
The link shown in the error message should take you directly to the authorization screen.
If not, make sure that you are logged in as a domain admin, then re-enter the link.

### Verify GAMADV-XTD3 service account access.

Wait a moment and then perform the following command; it it still fails, wait a bit longer, it can sometimes take serveral minutes
for the authorization to complete.
```
admin@server:/Users/admin/bin/gamadv-xtd3$ ./gam user admin@domain.com check serviceaccount
System time status:
  Your system time differs from www.googleapis.com by less than 1 second    PASS
Service Account Private Key Authentication:
  Authentication                                                            PASS
Domain-Wide Delegation authentication:, User: admin@domain.com, Scopes: 28
  https://mail.google.com/                                                  PASS (1/28)
  https://sites.google.com/feeds                                            PASS (2/28)
  https://www.googleapis.com/auth/apps.alerts                               PASS (3/28)
  https://www.googleapis.com/auth/calendar                                  PASS (4/28)
  https://www.googleapis.com/auth/classroom.announcements                   PASS (5/28)
  https://www.googleapis.com/auth/classroom.coursework.students             PASS (6/28)
  https://www.googleapis.com/auth/classroom.courseworkmaterials             PASS (7/28)
  https://www.googleapis.com/auth/classroom.profile.emails                  PASS (8/28)
  https://www.googleapis.com/auth/classroom.rosters                         PASS (9/28)
  https://www.googleapis.com/auth/classroom.topics                          PASS (10/28)
  https://www.googleapis.com/auth/cloud-identity                            PASS (11/28)
  https://www.googleapis.com/auth/cloud-platform                            PASS (12/28)
  https://www.googleapis.com/auth/contacts                                  PASS (13/28)
  https://www.googleapis.com/auth/contacts.other.readonly                   PASS (14/28)
  https://www.googleapis.com/auth/datastudio                                PASS (15/28)
  https://www.googleapis.com/auth/directory.readonly                        PASS (16/28)
  https://www.googleapis.com/auth/documents                                 PASS (17/28)
  https://www.googleapis.com/auth/drive                                     PASS (18/28)
  https://www.googleapis.com/auth/drive.activity                            PASS (19/28)
  https://www.googleapis.com/auth/drive.admin.labels                        PASS (20/28)
  https://www.googleapis.com/auth/drive.labels                              PASS (21/28)
  https://www.googleapis.com/auth/gmail.modify                              PASS (22/28)
  https://www.googleapis.com/auth/gmail.settings.basic                      PASS (23/28)
  https://www.googleapis.com/auth/gmail.settings.sharing                    PASS (24/28)
  https://www.googleapis.com/auth/keep                                      PASS (25/28)
  https://www.googleapis.com/auth/spreadsheets                              PASS (26/28)
  https://www.googleapis.com/auth/tasks                                     PASS (27/28)
  https://www.googleapis.com/auth/userinfo.profile                          PASS (28/28)
All scopes PASSED!

Service Account Client name: SVCACCTID is fully authorized.

admin@server:/Users/admin/bin/gamadv-xtd3$ 
```

## Windows

### Download the latest version

This example assumes that GAMADV-XTD3 has been installed in C:\GAMADV-XTD3.
If you've installed GAMADV-XTD3 in another directory, substitute that value in the directions when downloading.

See: [Downloads](Downloads)

In these examples, your Google Super admin is shown as admin@domain.com; replace with the
actual email adddress.

This example assumes that GAMADV-XTD3 has been installed in C:\GAMADV-XTD3; if you've installed
GAMADV-XTD3 in another directory, substitute that value in the directions.

These steps assume Command Prompt, adjust if you're using PowerShell.

### Update your project with local browser to include the additional APIs that GAMADV-XTD3 uses.
This step may be omitted if you are updating from a recent version.
```
C:\GAMADV-XTD3>gam update project

Enter your Google Workspace admin or GCP project manager email address authorized to manage project(s) gam-project-abc-123-xyz? admin@domain.com

Your browser has been opened to visit:

    https://accounts.google.com/o/oauth2/v2/auth?redirect_uri=http%3A%2F%2Flocalhost%3A8080%2F&response_type=code&client_id=...

Authentication successful.
API: admin.googleapis.com, already enabled...
API: appsactivity.googleapis.com, already enabled...
API: calendar-json.googleapis.com, already enabled...
API: classroom.googleapis.com, already enabled...
API: contacts.googleapis.com, already enabled...
API: drive.googleapis.com, already enabled...
API: gmail.googleapis.com, already enabled...
API: groupssettings.googleapis.com, already enabled...
API: licensing.googleapis.com, already enabled...
API: plus.googleapis.com, already enabled...
API: reseller.googleapis.com, already enabled...
API: siteverification.googleapis.com, already enabled...
API: vault.googleapis.com, already enabled...
Enable 3 APIs
  API: audit.googleapis.com, Enabled (1/3)
  API: groupsmigration.googleapis.com, Enabled (2/3)
  API: sheets.googleapis.com, Enabled (3/3)

C:\GAMADV-XTD3>
```
### Update your project without local browser (headless server for instance) to include the additional APIs that GAMADV-XTD3 uses
This step may be omitted if you are updating from a recent version.
```
C:\GAMADV-XTD3>gam config no_browser true save
C:\GAMADV-XTD3>gam update project

Enter your Google Workspace admin or GCP project manager email address authorized to manage project(s) gam-project-abc-123-xyz? admin@domain.com

Go to the following link in a browser on other computer:

    https://accounts.google.com/o/oauth2/v2/auth?redirect_uri=http%3A%2F%2Flocalhost%3A8080%2F&response_type=code&client_id=...

Enter verification code: abc...xyz

Authentication successful.
API: admin.googleapis.com, already enabled...
API: appsactivity.googleapis.com, already enabled...
API: calendar-json.googleapis.com, already enabled...
API: classroom.googleapis.com, already enabled...
API: contacts.googleapis.com, already enabled...
API: drive.googleapis.com, already enabled...
API: gmail.googleapis.com, already enabled...
API: groupssettings.googleapis.com, already enabled...
API: licensing.googleapis.com, already enabled...
API: plus.googleapis.com, already enabled...
API: reseller.googleapis.com, already enabled...
API: siteverification.googleapis.com, already enabled...
API: vault.googleapis.com, already enabled...
Enable 3 APIs
  API: audit.googleapis.com, Enabled (1/3)
  API: groupsmigration.googleapis.com, Enabled (2/3)
  API: sheets.googleapis.com, Enabled (3/3)

C:\GAMADV-XTD3>
```
### Update GAMADV-XTD3 client access

You select a list of scopes, GAM uses a browser to get final authorization from Google for these scopes and
writes the credentials into the file oauth2.txt.

```
C:\GAMADV-XTD3>gam oauth create

Select the authorized scopes by entering a number.
Append an 'r' to grant read-only access or an 'a' to grant action-only access.

[*]  0)  Calendar API (supports readonly)
[*]  1)  Chrome Browser Cloud Management API (supports readonly)
[*]  2)  Chrome Management API - Telemetry read only
[*]  3)  Chrome Management API - read only
[*]  4)  Chrome Policy API (supports readonly)
[*]  5)  Chrome Printer Management API (supports readonly)
[*]  6)  Chrome Version History API
[*]  7)  Classroom API - Course Announcements (supports readonly)
[*]  8)  Classroom API - Course Topics (supports readonly)
[*]  9)  Classroom API - Course Work/Materials (supports readonly)
[*] 10)  Classroom API - Course Work/Submissions (supports readonly)
[*] 11)  Classroom API - Courses (supports readonly)
[*] 12)  Classroom API - Profile Emails
[*] 13)  Classroom API - Profile Photos
[*] 14)  Classroom API - Rosters (supports readonly)
[*] 15)  Classroom API - Student Guardians (supports readonly)
[*] 16)  Cloud Identity Groups API (supports readonly)
[*] 17)  Cloud Storage (Vault Export - read only)
[*] 18)  Contact Delegation API (supports readonly)
[*] 19)  Contacts API - Domain Shared and Users and GAL
[*] 20)  Data Transfer API (supports readonly)
[*] 21)  Directory API - Chrome OS Devices (supports readonly)
[*] 22)  Directory API - Customers (supports readonly)
[*] 23)  Directory API - Domains (supports readonly)
[*] 24)  Directory API - Groups (supports readonly)
[*] 25)  Directory API - Mobile Devices Directory (supports readonly and action)
[*] 26)  Directory API - Organizational Units (supports readonly)
[*] 27)  Directory API - Resource Calendars (supports readonly)
[*] 28)  Directory API - Roles (supports readonly)
[*] 29)  Directory API - User Schemas (supports readonly)
[*] 30)  Directory API - User Security
[*] 31)  Directory API - Users (supports readonly)
[*] 32)  Email Audit API
[*] 33)  Groups Migration API
[*] 34)  Groups Settings API
[*] 35)  License Manager API
[*] 36)  People API (supports readonly)
[*] 37)  People Directory API - read only
[ ] 38)  Pub / Sub API
[*] 39)  Reports API - Audit Reports
[*] 40)  Reports API - Usage Reports
[ ] 41)  Reseller API
[*] 42)  Site Verification API
[*] 43)  Sites API
[*] 44)  Vault API (supports readonly)

     s)  Select all scopes
     u)  Unselect all scopes
     e)  Exit without changes
     c)  Continue to authorization
Please enter 0-44[a|r] or s|u|e|c: c

Enter your Google Workspace admin email address? admin@domain.com

Go to the following link in a browser on this computer or on another computer:

    https://accounts.google.com/o/oauth2/v2/auth?response_type=code&client_id=423565144751-10lsdt2lgnsch9jmdhl35uq4617u1ifp&redirect_uri=http%3A%2F%2F127.0.0.1%3A8080%2F&scope=...

If you use a browser on another computer, you will get a browser error that the site can't be reached AFTER you
click the Allow button, paste "Unable to connect" URL from other computer (only URL data up to &scope required):

Enter verification code or paste "Unable to connect" URL from other computer (only URL data up to &scope required):

The authentication flow has completed.
Client OAuth2 File: C:\GAMConfig\oauth2.txt, Created

C:\GAMADV-XTD3>
```
### Update GAMADV-XTD3 service account access.
```
C:\GAMADV-XTD3>gam user admin@domain.com check serviceaccount
System time status
  Your system time differs from www.googleapis.com by less than 1 second    PASS
Service Account Private Key Authentication
  Authentication                                                            PASS
Service Account Private Key age; Google recommends rotating keys on a routine basis
  Service Account Private Key age: 0 days                                   PASS
Domain-Wide Delegation authentication:, User: admin@domain.com, Scopes: 28
  https://mail.google.com/                                                  PASS (1/28)
  https://sites.google.com/feeds                                            PASS (2/28)
  https://www.googleapis.com/auth/apps.alerts                               PASS (3/28)
  https://www.googleapis.com/auth/calendar                                  PASS (4/28)
  https://www.googleapis.com/auth/classroom.announcements                   PASS (5/28)
  https://www.googleapis.com/auth/classroom.coursework.students             PASS (6/28)
  https://www.googleapis.com/auth/classroom.courseworkmaterials             PASS (7/28)
  https://www.googleapis.com/auth/classroom.profile.emails                  PASS (8/28)
  https://www.googleapis.com/auth/classroom.rosters                         PASS (9/28)
  https://www.googleapis.com/auth/classroom.topics                          PASS (10/28)
  https://www.googleapis.com/auth/cloud-identity                            PASS (11/28)
  https://www.googleapis.com/auth/cloud-platform                            PASS (12/28)
  https://www.googleapis.com/auth/contacts                                  PASS (13/28)
  https://www.googleapis.com/auth/contacts.other.readonly                   PASS (14/28)
  https://www.googleapis.com/auth/datastudio                                PASS (15/28)
  https://www.googleapis.com/auth/directory.readonly                        PASS (16/28)
  https://www.googleapis.com/auth/documents                                 PASS (17/28)
  https://www.googleapis.com/auth/drive                                     PASS (18/28)
  https://www.googleapis.com/auth/drive.activity                            PASS (19/28)
  https://www.googleapis.com/auth/drive.admin.labels                        FAIL (20/28)
  https://www.googleapis.com/auth/drive.labels                              FAIL (21/28)
  https://www.googleapis.com/auth/gmail.modify                              PASS (22/28)
  https://www.googleapis.com/auth/gmail.settings.basic                      PASS (23/28)
  https://www.googleapis.com/auth/gmail.settings.sharing                    PASS (24/28)
  https://www.googleapis.com/auth/keep                                      PASS (25/28)
  https://www.googleapis.com/auth/spreadsheets                              PASS (26/28)
  https://www.googleapis.com/auth/tasks                                     PASS (27/28)
  https://www.googleapis.com/auth/userinfo.profile                          PASS (28/28)
Some scopes FAILED!
To authorize them, please go to:

    https://admin.google.com/ac/owl/domainwidedelegation?clientScopeToAdd=https://mail.google.com/,https://sites.google.com/feeds,https://www.googleapis.com/auth/apps.alerts,https://www.googleapis.com/auth/calendar,https://www.googleapis.com/auth/classroom.announcements,https://www.googleapis.com/auth/classroom.coursework.students,https://www.googleapis.com/auth/classroom.courseworkmaterials,https://www.googleapis.com/auth/classroom.profile.emails,https://www.googleapis.com/auth/classroom.rosters,https://www.googleapis.com/auth/classroom.topics,https://www.googleapis.com/auth/cloud-identity,https://www.googleapis.com/auth/cloud-platform,https://www.googleapis.com/auth/contacts,https://www.googleapis.com/auth/contacts.other.readonly,https://www.googleapis.com/auth/datastudio,https://www.googleapis.com/auth/directory.readonly,https://www.googleapis.com/auth/documents,https://www.googleapis.com/auth/drive,https://www.googleapis.com/auth/drive.activity,https://www.googleapis.com/auth/gmail.modify,https://www.googleapis.com/auth/gmail.settings.basic,https://www.googleapis.com/auth/gmail.settings.sharing,https://www.googleapis.com/auth/keep,https://www.googleapis.com/auth/spreadsheets,https://www.googleapis.com/auth/tasks,https://www.googleapis.com/auth/userinfo.profile,https://www.googleapis.com/auth/userinfo.email&clientIdToAdd=SVCACCTID&overwriteClientId=true&dn=domain.com&authuser=admin@domain.com

You will be directed to the Google Workspace admin console Security/API Controls/Domain-wide Delegation page
The "Add a new Client ID" box will open
Make sure that "Overwrite existing client ID" is checked
Click AUTHORIZE
When the box closes you're done
After authorizing it may take some time for this test to pass so wait a few moments and then try this command again.

C:\GAMADV-XTD3>
```
The link shown in the error message should take you directly to the authorization screen.
If not, make sure that you are logged in as a domain admin, then re-enter the link.

### Verify GAMADV-XTD3 service account access.

Wait a moment and then perform the following command; it it still fails, wait a bit longer, it can sometimes take serveral minutes
for the authorization to complete.
```
C:\GAMADV-XTD3>gam user admin@domain.com check serviceaccount
System time status:
  Your system time differs from www.googleapis.com by less than 1 second    PASS
Service Account Private Key Authentication:
  Authentication                                                            PASS
Domain-Wide Delegation authentication:, User: admin@domain.com, Scopes: 28
  https://mail.google.com/                                                  PASS (1/28)
  https://sites.google.com/feeds                                            PASS (2/28)
  https://www.googleapis.com/auth/apps.alerts                               PASS (3/28)
  https://www.googleapis.com/auth/calendar                                  PASS (4/28)
  https://www.googleapis.com/auth/classroom.announcements                   PASS (5/28)
  https://www.googleapis.com/auth/classroom.coursework.students             PASS (6/28)
  https://www.googleapis.com/auth/classroom.courseworkmaterials             PASS (7/28)
  https://www.googleapis.com/auth/classroom.profile.emails                  PASS (8/28)
  https://www.googleapis.com/auth/classroom.rosters                         PASS (9/28)
  https://www.googleapis.com/auth/classroom.topics                          PASS (10/28)
  https://www.googleapis.com/auth/cloud-identity                            PASS (11/28)
  https://www.googleapis.com/auth/cloud-platform                            PASS (12/28)
  https://www.googleapis.com/auth/contacts                                  PASS (13/28)
  https://www.googleapis.com/auth/contacts.other.readonly                   PASS (14/28)
  https://www.googleapis.com/auth/datastudio                                PASS (15/28)
  https://www.googleapis.com/auth/directory.readonly                        PASS (16/28)
  https://www.googleapis.com/auth/documents                                 PASS (17/28)
  https://www.googleapis.com/auth/drive                                     PASS (18/28)
  https://www.googleapis.com/auth/drive.activity                            PASS (19/28)
  https://www.googleapis.com/auth/drive.admin.labels                        PASS (20/28)
  https://www.googleapis.com/auth/drive.labels                              PASS (21/28)
  https://www.googleapis.com/auth/gmail.modify                              PASS (22/28)
  https://www.googleapis.com/auth/gmail.settings.basic                      PASS (23/28)
  https://www.googleapis.com/auth/gmail.settings.sharing                    PASS (24/28)
  https://www.googleapis.com/auth/keep                                      PASS (25/28)
  https://www.googleapis.com/auth/spreadsheets                              PASS (26/28)
  https://www.googleapis.com/auth/tasks                                     PASS (27/28)
  https://www.googleapis.com/auth/userinfo.profile                          PASS (28/28)
All scopes PASSED!

Service Account Client name: SVCACCTID is fully authorized.

C:\GAMADV-XTD3>
```
