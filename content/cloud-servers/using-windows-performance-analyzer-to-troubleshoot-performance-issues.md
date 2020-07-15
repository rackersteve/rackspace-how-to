---
permalink: using-windows-performance-analyzer-to-troubleshoot-performance-issues/
audit_date:
title: ‘Using Windows Performance Analyzer to troubleshoot performance issues’
type: article
created_date: '2020-07-09’
created_by: Karoline Mills
last_modified_date:
last_modified_by:
product: Cloud Servers
product_url: cloud-servers
---

### Using Windows Performance Analyzer to troubleshoot performance issues

This article explains how to use Windows Performance Analyzer to troubleshoot performance issues in Windows. Windows Performance Analyzer (WPA) is included in the Windows Assessment and Deployment Kit (ADK). It is used to create tables and graphs of performance data and events that are captured with Windows Performance Recorder (WPR), which is also part of the ADK. This kit is free and can be downloaded directly from Microsoft.

#### Creating an event trace log file using Windows Performance Recorder (WPR)

Once you have downloaded the Windows Assessment and Deployment Kit, open then Windows Performer Recorder application. The tool will gather information about the interaction of programs and hardware running on the server. You can simply select **Start** to start recording using the default settings. If you would like to customize the recording, expand the options menu by clicking on **More options**. Here you can select additional profiles for performance recording, such as GPU activity, power usage and pool usage. Once you are satisfied with the length of the recording, click **Save** to stop recording and select a path for the event trace log to be stored. You can now directly import the file into WPA by clicking **Open in WPA**.

#### Importing and analyzing event trace log file to Windows Performance Analyzer (WPA)

To start the WPA application, click on the Windows button on your desktop and type **WPA**.  Follow these steps if you want to open an existing trace log file in WPA:

1.	In the **File** menu, click **Open**

2.	Navigate to the location where your file is stored (by default, event trace log files are stored in your Documents\WPR Files folder)

3.	Select the file and click **Open**

#### Analyzing the event trace log file

You will see all available performance recordings in the **Graph Explorer** on the left-hand side. To view different graphs in more detail, expand them by clicking the small triangle. To further analyze the data, you can double-click or drag-and-drop the graph to the right-hand side into the **Analysis** panel. You can open multiple graphs in the **Analysis** tab using this method. In addition, you can open multiple **Analysis** tabs by clicking on the **+** icon. In the top bar, you can change the graph view and layout. 
To select a specific time interval to analyze, left-click on the graph, hold and drag the cursor to highlight the desired section. To view the selected time frame in more detail, right-click and select **Zoom**. You can also customize the data table view. Drag-and-drop the columns to change their order and right-click to choose which columns you want to be displayed. You can also search the data by right-clicking on the data column and selecting **Find**. If you want to save a layout for later use, you can export it by clicking **Profiles** and **Export…**. You can also select **Save Startup Profile** to make this the default layout upon start of WPA.
