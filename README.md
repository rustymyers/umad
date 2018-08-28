# UMAD
[U]ser-facing
[M]DM
[A]pproval
[D]ialog

## Screenshots

### DEP
![Screenshot DEP](/images/ss_dep.png?raw=true)

### Manual
![Screenshot Manual](/images/ss_manual.png?raw=true)

### UAMDM
![Screenshot UAMDM](/images/ss_uamdm.png?raw=true)

## Building this package
You will need to use [munki-pkg](https://github.com/munki/munki-pkg) to build this package

### Notes
Because of the way git works, umad will not contain the `Logs` folder required for the postinstall to complete.

In order to create a properly working package, you will need to run the following command:
`munkipkg --sync /path/to/cloned_repo/mdm/umad`

## Options
Essentially every component of the UI is customizable, all through the LaunchAgent.

### Cutoff date
Cut off date in UTC.
```xml
<string>--cutoffdate</string>
<string>2018-12-31-17:00</string>
```

### Cut off date warning
This is the number, in days, of when to start the initial UI warning. When this set of days passes, the user will be required to hit an "I Understand" button, followed by the "Close" button to exit out of the UI.
```xml
<string>--cutoffdatewarning</string>
<string>14</string>
```

### Due date text
This is the bolded portion of the UI towards the top.
```xml
<string>--duedatetext</string>
<string>MDM Enrollment is required by 12/31/2018 (No Restart Required)</string>
```

### DEP failure text
If a user has a DEP capable device, but they are passed the enrollment window, they will have an option to manually enroll.

This is the first set of text above the enrollment button.
```xml
<string>--depfailuretext</string>
<string>Not getting this notification?</string>
```

### DEP failure subtext
If a user has a DEP capable device, but they are passed the enrollment window, they will have an option to manually enroll.

This is the second set of text above the enrollment button.
```xml
<string>--depfailuresubtext</string>
<string>You can also enroll manually below:</string>
```

### Enable enrollment button
Always show the manual enrollment button, DEP or not.

```xml
<string>--enableenrollmentbutton</string>
```

### Logo path
A custom logo path. Alternatively, just replace the included company_logo.png
```xml
<string>--logopath</string>
<string>/Some/Custom/Path/company_logo.png</string>
```

### Manual enrollment text
If a user does not have a DEP capable device, they will have the option to manually enroll.

This is the bolded text that takes place of the DEP or UAMDM screenshot.

```xml
<string>--manualenrollmenttext</string>
<string>Manual Enrollment Required</string>
```

### Manual enrollment h1 text
If a user does not have a DEP capable device, they will have the option to manually enroll.

This is the first set of text above the enrollment button.

```xml
<string>--manualenrollh1text</string>
<string>Want this box to go away?</string>
```

### Manual enrollment h2 text
If a user does not have a DEP capable device, they will have the option to manually enroll.

This is the second set of text above the enrollment button.

```xml
<string>--manualenrollh2text</string>
<string>Click on the Manual Enrollment button below.</string>
```

### Manual enrollment URL
This is the URL to open for the Manual Enrollment button.
```xml
<string>--manualenrollmenturl</string>
<string>https://apple.com</string>
```

### More info URL
This is the URL to open for the Manual Enrollment button.
```xml
<string>--moreinfourl</string>
<string>https://google.com</string>
```

### Nag screenshot path
A custom nag screenshot path. Alternatively, just replace the included nag_ss.png
```xml
<string>--nagsspath</string>
<string>/Some/Custom/Path/nag_ss.png</string>
```

### No timer
Do not attempt to restore the umad GUI to the front of a user's window.

```xml
<string>--notimer</string>
```

### Paragraph 1 text
This is the text for the first paragraph.
```xml
<string>--paragraph1</string>
<string>If you do not enroll into MDM you will lose the ability to connect to Wi-Fi, VPN and Managed Software Center.</string>
```

### Paragraph 2 text
This is the text for the second paragraph.
```xml
<string>--paragraph2</string>
<string>To enroll, just look for the below notification, and click Details. Once prompted, log in with your username and password.</string>
```

### Paragraph 2 text
This is the text for the third paragraph.
```xml
<string>--paragraph3</string>
<string>To enroll, just look for the below notification, and click Details. Once prompted, log in with your OneLogin username and password.</string>
```

### Sub-title text
This is the text right under the main title.
```xml
<string>--subtitletext</string>
<string>A friendly reminder from your local IT team</string>
```

### System Preferences H1 text
Should the user have a 10.13.4+ device that is not User Approved MDM, they will be notified that they need to approve the MDM.

This is the first set of text above the system preferences button.
```xml
<string>--sysprefsh1text</string>
<string>Want this box to go away?</string>
```

### System Preferences H2 text
Should the user have a 10.13.4+ device that is not User Approved MDM, they will be notified that they need to approve the MDM.

This is the second set of text above the system preferences button.
```xml
<string>--sysprefsh2text</string>
<string>Open System Preferences and approve Device Management.</string>
```

### Title text
This is the main, bolded text at the very top.
```xml
<string>--titletext</string>
<string>MDM Enrollment</string>
```

### Timer Day 1
The time, in seconds, to restore the umad GUI to the front of a user's window. This will occur indefinitely until the UI is closed or MDM is enrolled.

This is when the MDM cutoff is one day or less.
```xml
<string>--timerday1</string>
<string>600</string>
```

### Timer Day 3
The time, in seconds, to restore the umad GUI to the front of a user's window. This will occur indefinitely until the UI is closed or MDM is enrolled.

This is when the MDM cutoff is three days or less.
```xml
<string>--timerday3</string>
<string>7200</string>
```

### Timer Elapsed
The time, in seconds, to restore the umad GUI to the front of a user's window. This will occur indefinitely until the UI is closed or MDM is enrolled.

This is when the MDM cutoff has elapsed.
```xml
<string>--timerelapsed</string>
<string>10</string>
```

### Timer Final
The time, in seconds, to restore the umad GUI to the front of a user's window. This will occur indefinitely until the UI is closed or MDM is enrolled.

This is when the MDM cutoff is one hour or less
```xml
<string>--timerfinal</string>
<string>60</string>
```

### Timer Initial
The time, in seconds, to restore the umad GUI to the front of a user's window. This will occur indefinitely until the UI is closed or MDM is enrolled.

This is when the MDM cutoff is over three days.
```xml
<string>--timerinital</string>
<string>14400</string>
```

### Timer MDM
The time, in seconds, to check if the device is enrolled into MDM.

```xml
<string>--timermdm</string>
<string>5</string>
```

### User Approved MDM paragraph 1 text
This is the text for the first paragraph on the user Approved MDM UI.
```xml
<string>--uamdmparagraph1</string>
<string>Thank you for enrolling your device into MDM. We sincerely appreciate you doing this in a timely manner.</string>
```

### User Approved MDM paragraph 2 text
This is the text for the second paragraph on the user Approved MDM UI.
```xml
<string>--uamdmparagraph2</string>
<string>Unfortunately, your device has been detected as only partially enrolled into our system.</string>
```

### User Approved MDM paragraph 3 text
This is the text for the third paragraph on the user Approved MDM UI.
```xml
<string>--uamdmparagraph3</string>
<string>Please go to System Preferences -> Profiles, click on the Device Enrollment profile and click on the approve button.</string>
```

### User Approved MDM screenshot path
A custom uamdm screenshot path. Alternatively, just replace the included uamdm_ss.png.png
```xml
<string>--uasspath</string>
<string>/Some/Custom/Path/uamdm_ss.png</string>
```