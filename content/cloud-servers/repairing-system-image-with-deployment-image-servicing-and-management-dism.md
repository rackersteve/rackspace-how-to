---
permalink: repair-system-image-with-dism/
audit_date:
title: 'Repair System Image with DISM'
type: article
created_date: '2020-07-07'
created_by: Dave Myers
last_modified_date: '2020-07-21'
last_modified_by: Rose Morales
product: Cloud Servers
product_url: cloud-servers
---

Deployment Image Servicing and Management (DISM) is a Windows&reg built-in
command-line tool used to prepare, modify, and repair Windows system images.
Images can be saved and used later in deploying and restoring Windows operating
system. DISM is used to repair your system when it is not booting properly or
getting a blue screen error, when System File Check (SFC) is unable to resolve
it first. 

**Note** This task requires a user with administrative privileges on the server.

- Open the **Command Prompt** or **PowerShell** and type the command lines below. Press **Enter** after typing each command line to check and repair a Windows&reg 10 system image.

  `DISM /Online /Cleanup-Image /CheckHealth`

  Checks for corruptions inside the local image, no repairs happen.

  `DISM /Online /Cleanup-Image /ScanHealth`

  Performs a deep scan to check if Windows&reg 10 image has system corruptions.

  `DISM /Online /Cleanup-Image /RestoreHealth`

  Runs an advanced scan and automatically repairs image problems.

<br>

####Windows&reg edition servicing commands

  | `/Set-ProductKey`     | Sets the product key of the offline image|
  | `/Get-TargetEditions` | Displays a list of Windows editions that an image can be upgraded to.|
  | `/Get-CurrentEdition` | Displays the edition of the current image.|
  | `/Set-Edition`        | Upgrades an image to a higher edition.|

####General commands

  | `/Optimize-Image`    | Performs specified configurations to an offline image.|

####Default association commands

  | `/Remove-DefaultAppAssociations`   | Removes the default application associations from a Windows image. |
  | `/Import-DefaultAppAssociations`   | Imports a set of default application associations to a Windows image. |
  | `/Get-DefaultAppAssociations`      | Displays the list of default application associations from a Windows image. |
  | `/Export-DefaultAppAssociations`   | Exports the default application associations from a running operating system. |

####AppX servicing commands

  | `/Set-ProvisionedAppxDataFile`   | Places custom data into the specified app package (.appx or .appxbundle). The specified application package must already be in the image.|
  | `/Remove-ProvisionedAppxPackage` | Removes app packages (.appx or .appxbundle) from the image. App packages will not be installed when new user accounts are created.| 
  | `/Add-ProvisionedAppxPackage`    | Adds app packages (.appx or .appxbundle) to the image and sets them to install for each new user.|
  | `/Get-ProvisionedAppxPackages`   | Displays information about app packages (.appx or .appxbundle) in an image that are set to install for each new user.|

####Unattended servicing commands

  | `/Apply-Unattend`        | Applies an unattended file to an image.|

####Driver servicing commands

  | `/Remove-Driver`         | Removes driver packages from an offline image.|
  | `/Add-Driver`            | Adds driver packages to an offline image.|
  | `/Get-DriverInfo`        | Displays information about a specific driver in an offline image or a running operating system. |
  | `/Get-Drivers`           | Displays information about all drivers in an offline image or a running operating system. |
  | `/Export-Driver`         | Export all third-party driver packages from an offline image or a running operating system.|

####International servicing commands

  | `/Set-LayeredDriver`     | Sets keyboard layered driver. |
  | `/Set-UILang`            | Sets the default system UI language that is used in the mounted offline image. |
  | `/Set-UILangFallback`    | Sets the fallback default language for the system UI in the mounted offline image. |
  | `/Set-UserLocale`        | Sets the user locale in the mounted offline image. |
  | `/Set-SysLocale`         | Sets the language for non-Unicode programs (also called system locale) and font settings in the mounted offline image. |
  | `/Set-InputLocale`       | Sets the input locales and keyboard layouts to use in the mounted offline image.|
  | `/Set-TimeZone`          | Sets the default time zone in the mounted offline image. |
  | `/Set-AllIntl`           | Sets all international settings in the mounted offline image. |
  | `/Set-SKUIntlDefaults`   | Sets all international settings to the default values for the specified SKU language in the mounted offline image. |
  | `/Gen-LangIni`           | Generates a new lang.ini file.|
  | `/Set-SetupUILang`       | Defines the default language that will be used by setup. |
  | `/Get-Intl`              | Displays information about the international settings and languages.|

####Application servicing commands

  | `/Check-AppPatch`         | Displays information if the MSP patches are applicable to the mounted image.|
  | `/Get-AppPatchInfo`       | Displays information about installed MSP patches.|
  | `/Get-AppPatches`         | Displays information about all applied MSP patches for all installed applications. |
  | `/Get-AppInfo`            | Displays information about a specific installed MSI application. |
  | `/Get-Apps`               | Displays information about all installed MSI applications.|

####Package servicing commands

  | `/Add-Package`            | Adds packages to the image. |
  | `/Remove-Package`         | Removes packages from the image. |
  | `/Enable-Feature`         | Enables a  specific feature in the image. |
  | `/Disable-Feature`        | Disables a specific  feature in the image. |
  | `/Get-Packages`           | Displays information about all  packages in the image. |
  | `/Get-PackageInfo`        | Displays information about a  specific package. |
  | `/Get-Features`           | Displays information about all  features in a package. |
  | `/Get-FeatureInfo`        | Displays information about a  specific feature. |
  | `/Cleanup-Image`          | Performs cleanup and recovery  operations on the image.|

For more information about these servicing commands and their arguments, specify
a command before /?.

     Examples:
         DISM.exe /Image:C:\test\offline /Apply-Unattend /?
         DISM.exe /Image:C:\test\offline /Get-Features /?
         DISM.exe /Online /Get-Drivers /?
