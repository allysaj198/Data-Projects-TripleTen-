# SHOPIFY APP ANALYSIS

## Description & Methods
The project was to be conducted in the role of a newly hired analyst to review the landscape of apps on the Shopify platform, using data scraped from publicly available Shopify websites to figure out what key factors play into the success of a Shopify app.  With this, the project was divided into three main tasks:
### 1. App Landscape
 - To find key statistics on the types of apps there are, a new sheet 'App Landscape' was created and it used data from the Apps table
    - added a KPI Card counting the unique number of apps
    - added a Line Chart with the sum of the 'reviews_count' on the Y-Axis and the 'lastmod_date' on the X-Axis.
    - Made a Scatterplot with the 'reviews_count' on the X-Axis and the 'rating' on the Y-Axis
### 2. Reviews
- Added a second sheet to the file named Reviews
- added a column, 'helpful_reviews', to the Reviews table using the DAX expression, rating * (1+helpful_count).
  - Made a Card with the average value of the new 'helpful_reviews' column
- added another column, 'developer_answered' to the Reviews table using a DAX expression:
  - developer_answered = IF(ISBLANK(Reviews[developer_reply]), 0, 1)
  - Made a scatterplot comparing the average rating on the Y-Axis by the value of the 'developer_answered' column on the X-Axis
### 3. App Reviews
- Added the last sheet of the file, App Reviews
- In the data model, a new relationship between the Reviews table and the Apps table was created.
  - Used the 'app_id' column from the Reviews table, and the 'id' column from the Apps table.
  - Made the relationship many-to-one built as many (Reviews table) to one (Apps table).
  - Lastly made a bar chart with the 'developer' on the X-Axis, and the sum of 'rating' on the Y-Axis.
- Made a new bar chart with 'developer' on the X-Axis against the 'helpful_review' average on the Y-Axis to account for a possibly misleading previous visualization.
- Made a bar chart with the 'developer' from the apps table and the new 'developer_answered' column
  - added a filter for this visual which selects only the rows where reviews_count is greater than 500.


## Findings
* Shopify holds 7,341 different apps on the platform
* The average count of reviews fluctuates but stays under 50k after a steep drop from over 250k.
* From the Scatterplot in task 2. it can be interpreted that the majority of reviews give a rating higher than 4.00. The highest average rating 4.60, was given by 24,780 reviewers. There were no 0.00-rating reviews but 9,239 of them were a full 5.00.
* The average rating for helpful reviews (reviews weighed by how helpful they are found) was 5.48.
* The average rating on replies from developers is above 4.5.
* Elfsight is the developer among all the apps with the highest sum of rating.
* Pictorem was the developer of the highest average helpful reviews.
* DSers gave the highest amount of replies.

## Media
![36F989D3-C457-4A15-B026-7D02C9111A04](https://github.com/user-attachments/assets/28cda591-9390-4984-b61b-9a5ecd1dab47)

![DD497202-A125-405A-916E-AF7A011FC4AE_1_105_c](https://github.com/user-attachments/assets/38ac5d84-86b6-457f-9e65-0bb2c6893edd)

![4F424CF6-8CF8-4331-BA97-3CC809F02CBE_1_105_c](https://github.com/user-attachments/assets/e194b76b-2c4e-44b5-83fd-898ecd4fc07a)

![A09A9F4C-ADC6-43ED-9FA9-9070C14FDFF1_1_105_c](https://github.com/user-attachments/assets/cbe77482-7bbd-46e5-bf87-fabf526b40bf)


## Link to project page
N/A

## Deployment Instructions & System Requirements
#### Deployment Instructions for Power BI
* Download Power BI Desktop
  * Power BI Desktop is available for free and can be installed on Windows-based systems.
  * Go to the official Microsoft Power BI website: Power BI Desktop Download.
  * Click "Download free" to get the installer.
* Install Power BI Desktop
  * Once the installer (.exe file) has been downloaded, double-click it to start the installation process.
  * Follow the on-screen instructions:
  * Choose your preferred installation options.
  * Click Install when prompted to begin the installation.
* Launch Power BI Desktop
  * After installation, open Power BI Desktop by searching for it in the Start Menu or by clicking the Power BI Desktop icon on your desktop.
  * The first time you launch the application, you may be prompted to sign in to your Microsoft account. If you don't have one, you can create one at Microsoft Account Signup.

#### System Requirements for Power BI
Here are the system requirements for running Power BI Desktop on your local machine:

#### For Windows:
* Operating System:
  * Windows 10 (64-bit) or later
  * Windows Server 2016 or later (for server environments)
  * Power BI Desktop does not run on older versions of Windows (Windows 8.1 or lower, Windows 7).
* Processor:
  * A 64-bit processor (x64 architecture)
  * At least 1 GHz or faster, with at least 2 cores (4 cores or more recommended for large datasets)
* Memory (RAM):
  * Minimum 2 GB of RAM (4 GB or more recommended for better performance)
  * 8 GB or more of RAM is recommended for larger data models or complex reports.
* Disk Space:
  * At least 1 GB of free disk space (more may be required depending on data model size)
* Display:
  * A screen resolution of at least 1440 x 900 or higher is recommended for optimal display of data and visuals.
* Graphics:
  * A DirectX 10 compatible graphics card for accelerated rendering. While not strictly required, it improves performance with large visualizations.
* Internet Connection:
  * Required for downloading and installing Power BI Desktop.
  * An internet connection is also required for publishing reports to Power BI Service and for receiving data refresh updates (if applicable).
#### Power BI Service (for Online Use and Collaboration)
To fully utilize Power BI and collaborate with colleagues or stakeholders:
* Browser Compatibility:
  * Latest versions of Google Chrome, Microsoft Edge, Safari, or Mozilla Firefox are supported.
  * Internet Explorer is not recommended for an optimal experience.
* Power BI Service Subscription (Optional):
  * While Power BI Desktop is free, to share and collaborate with others or access more advanced features, you may need a Power BI Pro or Power BI Premium license.
  * The Power BI Pro license offers collaboration, sharing, and additional features, while Power BI Premium offers dedicated cloud resources and increased data model size for enterprise needs.

#### Options for Running Power BI on a Mac
* Using Power BI Service (Web Version):
  * You can use Power BI Service through any modern web browser, including those on macOS (Google Chrome, Safari, or Mozilla Firefox). This allows you to create, view, and interact with reports, dashboards, and data models without needing to install Power BI Desktop.
  * Access Power BI Service: Power BI Service
* Running Power BI Desktop via a Virtual Machine or Windows Environment:
  *Virtualization: You can use virtualization software (such as Parallels Desktop or VMware Fusion) to run a Windows environment on your Mac. With this, you can install and run Power BI Desktop as you would on a Windows machine.
  * Boot Camp: Alternatively, you can set up Boot Camp to dual-boot Windows on your Mac, allowing you to install Power BI Desktop in the Windows partition.
* Using Wine or Crossover (Non-native Solution):
  * Some users have successfully run Power BI Desktop on macOS using Wine or Crossover to simulate a Windows environment. However, this is not officially supported by Microsoft, and there could be performance or stability issues.
#### System Requirements for Power BI Service on macOS (Web Version)
If you're planning to use Power BI Service via a web browser, here are the browser requirements:
#### For Web Browsers on macOS:
* Operating System:
  * macOS 10.13 (High Sierra) or later is recommended to ensure compatibility with the latest versions of web browsers.
* Web Browsers:
  * Google Chrome (recommended)
  * Safari (latest version)
  * Mozilla Firefox (latest version)
  * Microsoft Edge (latest version)
* Internet Connection:
  * A stable internet connection is required to access Power BI Service.
* Display:
  * Minimum resolution of 1280 x 800 pixels for optimal user experience.
* Graphics:
  * A graphics card capable of rendering modern web apps, which is typically built into most recent Mac devices.
#### System Requirements for Running Power BI Desktop on Mac via Virtual Machine or Boot Camp
If you choose to run Power BI Desktop in a Windows environment on your Mac (using Parallels, VMware Fusion, or Boot Camp), here are the basic system requirements for Power BI Desktop running in Windows:

#### For Windows on Mac (via Virtual Machine or Boot Camp):
* Operating System:
  * Windows 10 (64-bit) or later.
  * Windows 7 or 8.1 (64-bit) are supported, but Power BI recommends using Windows 10 for the best performance and compatibility.
* Processor:
  * 1.8 GHz or faster x64-based processor (Intel or AMD).
* Memory:
  * Minimum 4 GB of RAM (8 GB recommended for larger datasets or complex reports).
* Disk Space:
  * At least 1 GB of available disk space for installation (more may be required depending on data models).
* Graphics:
  * A DirectX 10-compatible graphics card or better.
* Display:
  * A screen resolution of 1366 x 768 or higher is recommended.
* Internet Connection:
  * Required for downloading and installing Power BI Desktop and for publishing reports to Power BI Service.
#### Summary:
* Power BI Desktop is not directly supported on macOS, but you can still access Power BI Service (the web version) using any modern browser on macOS.
* If you need Power BI Desktop specifically, you can run it on macOS using a virtual machine, Boot Camp, or emulation software like Wine or Crossover.
* Power BI Service via the browser requires a stable internet connection and a supported browser.

