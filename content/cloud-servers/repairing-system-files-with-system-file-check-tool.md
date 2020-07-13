---
permalink: repairing-system-files-with-system-file-check-tool/
audit_date:
title: ''Repairing_System_Files_System_Filecheck_Tool'
type: article
created_date: '2020-06-23'
created_by: Dave Myers
last_modified_date:
last_modified_by:
product: Cloud Servers
product_url: cloud-servers
---

# System Filecheck Tool 
System File Check (SFC) Tool is similar to chkdisk. Both are Windows built-in command-line utilities that are used to check and fix disk related errors. Where **chkdsk** is different from **SFC** is the layer at which it operates. **chkdsk** works on repairing Filesystem integrity while **SFC** works on repairing system files that are written to the underlying filesystem. These are often used together starting with **chkdsk** when resolving corrupt or misallocated tables. Neither fixes hardware, they only fix software integrety. When your Windows OS cannot read a file on your computer the OS will begin to display various errors or possibly preventing Windows from starting. **chkdsk** should be run first to fix any filesystem errors. Then proceed to using System File Check (SFC) if the issue isn't resolved using **chkdsk** For more on **chkdsk** please review the "How to run chkdsk in Windows" article: https://support.rackspace.com/how-to/how-to-run-chkdsk-in-windows/

# Invoking System File Check Scan
Once you have made sure that the filesystem is intact and there are no physical damage to the drive you can proceed with checking Windows System Files by running **sfc /scannow** This will take a while to complete. 
[Successful SFC.png]

If the SFC does not find any errors or unable to repair the errors you can proceed with trying to resolve with Deployment Image Servicing and Management (DISM) utility. For more on the Deployment Image Servicing and Management (DISM) utility please review the "DISM" article:

# sfc /help
Microsoft (R) Windows (R) Resource Checker Version 6.0
Copyright (C) Microsoft Corporation. All rights reserved.

Scans the integrity of all protected system files and replaces incorrect versions with
correct Microsoft versions.

SFC [/SCANNOW] [/VERIFYONLY] [/SCANFILE=<file>] [/VERIFYFILE=<file>]
    [/OFFWINDIR=<offline windows directory> /OFFBOOTDIR=<offline boot directory>]

/SCANNOW        Scans integrity of all protected system files and repairs files with
                problems when possible.
/VERIFYONLY     Scans integrity of all protected system files. No repair operation is
                performed.
/SCANFILE       Scans integrity of the referenced file, repairs file if problems are
                identified. Specify full path <file>
/VERIFYFILE     Verifies the integrity of the file with full path <file>.  No repair
                operation is performed.
/OFFBOOTDIR     For offline repair specify the location of the offline boot directory
/OFFWINDIR      For offline repair specify the location of the offline windows directory

e.g.

        sfc /SCANNOW
        sfc /VERIFYFILE=c:\windows\system32\kernel32.dll
        sfc /SCANFILE=d:\windows\system32\kernel32.dll /OFFBOOTDIR=d:\ /OFFWINDIR=d:\windows
        sfc /VERIFYONLY
