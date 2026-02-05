## SOP: Developing a web application for incident reporting

### Purpose 
This SOP provides a standard process for internal GIS teams to develop a web application using ArcGIS Experience Builder in ArcGIS Enterprise. The web app will allow crisis management teams users to visualize locations with one click and submit various types of incident reports via a hosted form in real-time.

### Scope
This SOP covers the end-to-end process of developing, testing, and deploying the web application. It applies to the crisis management team, GIS Developers and Analysts, Quality Assurance team, and the Project Manager.

### Responsibilities
* **Crisis management team:**	Provide application requirements at the start of the project and give feedback during User Acceptance Testing (UAT).
* **GIS teams (Developers and Analysts):** Build and deploy the web application in ArcGIS Enterprise.
* **Quality Assurance (QA) team:** Test the application and report issues for correction.
* **Project Manager:** Track progress and ensure requirements are met.

### Prerequisites
The web application and the hosted form will be hosted in the organization enterprise environment and will be developed using ArcGIS Experience Builder framework and Python (ArcPy). 

### Objectives
* Develop a single-click feature that displays administrative areas using the organization’s standard styles and symbols.
* Provide a hosted form that allows crisis teams to add new incidents in real-time, capturing attributes such as location, type of crisis, priority, and date/time.
* Implement a search functionality to query all incident attributes for future reference and analysis.

### Development process
* **Administrative layers:** 
Datasets sourced from open source platforms such as ESRI and OpenStreetsMap.

* **Hosted form - Key attributes:**
| Attribute/Field | Type              | Description                                                   |
| ----------------| ----------------- | ------------------------------------------------------------- |
| GUID            | Unique Identifier | Automatically generated -  serial number                      |
| Name            | Text              | Brief title of the incident                                   |
| Type            | Text              | Main classification (e.g., Accident, Protest, etc)            |
| Status          | Text              | Current status (Ongoing, Resolved)                            |
| Country         | Text (calculated) | Auto-populated - Country                                      |
| Admin_region    | Text (calculated) | Auto-populated - Administrative state or district             |
| Location        | Text (calculated) | Auto-populated - Town, village or locality name               |
| Coordinates     | Text (calculated) | Latitude and longitude                                        |
| Media           | Image             | Image related to the incident                                 |
| Editor Tracking | System-generated  | created_date, created_user, last_edited_date, last_edited_user|
