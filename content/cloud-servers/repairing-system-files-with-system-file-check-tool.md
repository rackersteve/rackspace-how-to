---
permalink: repairing-system-files-with-system-file-check-tool/
audit_date: '2020-07-30'
title: Repairing system files with the System Filecheck Tool
type: article
created_date: '2020-07-30'
created_by: Dave Myers
last_modified_date:'2020-07-30'
last_modified_by: William Loy
product: Cloud Servers
product_url: cloud-servers
---

## System Filecheck Tool 

System File Check (SFC) Tool is similar to `chkdisk`. Both are Windows&reg; built-in command-line utilities that are used to check and fix disk related errors. Where `chkdsk` is different from SFC is the layer at which it operates. `chkdsk` works on repairing filesystem integrity while **SFC** works on repairing system files that are written to the underlying filesystem. These are often used together starting with `chkdsk` to resolve corrupt or misallocated tables. Both tools can only fix software integrity. 

When your Windows operating system (OS) cannot read a file on your computer, the OS begins to display various errors or possibly prevents Windows from starting. `chkdsk` should be run first to fix any filesystem errors. Then proceed to using System SFC if the issue isn't resolved using **chkdsk**. For more information on **chkdsk** please review the [How to run chkdsk in Windows](https://support.rackspace.com/how-to/how-to-run-chkdsk-in-windows/) article.

### Invoking System File Check Scan

When you have made sure that the filesystem is intact and there  isn't physical damage to the drive, you can proceed with checking Windows system files by running `sfc /scannow`. This command can take a while to complete. 

[Successful SFC.png]

If the SFC does not find any errors or is unable to repair the errors you can proceed with trying to resolve the issue with the Deployment Image Servicing and Management (DISM) utility. For more on the Deployment Image Servicing and Management (DISM) utility please review the "DISM" article:

### SFC help page

For a list of additional command options, try using the `sfc\help` command to produce a list like the following:

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
