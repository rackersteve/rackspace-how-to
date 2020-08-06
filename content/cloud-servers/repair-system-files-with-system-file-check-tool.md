---
permalink: repair-system-files-with-system-file-check-tool/
audit_date: '2020-07-30'
title: Repair system files with the System Filecheck tool
type: article
created_date: '2020-07-30'
created_by: Dave Myers
last_modified_date:'2020-07-30'
last_modified_by: William Loy
product: Cloud Servers
product_url: cloud-servers
--- 

The System File Check (SFC) tool is similar to `chkdisk`. Both are Windows&reg; built-in command-line utilities that
you can use to check and fix disk-related errors. Where `chkdsk` is different from SFC is the layer at which it
operates. `chkdsk` works on repairing filesystem integrity while **SFC** works on repairing system files that are
written to the underlying filesystem. Often, you use these together starting with `chkdsk` to resolve corrupt or
misallocated tables. Both tools can fix only software integrity. 

When your Windows operating system (OS) cannot read a file on your computer, it begins to display various errors
or possibly prevents Windows from starting. You should run `chkdsk` first to fix any filesystem errors. Then use SFC
if `chkdsk` doesn't resolve the issue. For more information on `chkdsk`, review the 
[How to run chkdsk in Windows](https://support.rackspace.com/how-to/how-to-run-chkdsk-in-windows/) article.

### Invoke a SFC scan

When you have made sure that the filesystem is intact and there isn't physical damage to the drive, you can check
Windows system files by running `sfc /scannow`. This command can take a while to complete. 

If the SFC does not find any errors or can't repair the errors, you can try to resolve the issue with the Deployment
Image Servicing and Management (DISM) utility.

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
