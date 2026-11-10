# Project Proposal

## Business Case

### Problem statement
New residents and university students in Bristol often struggle to discover green spaces beyond a few famous locations (like The Downs or Castle Park). Standard map applications prioritise navigation over exploration, offering no way to track local travel progress. This leads to overcrowding in central parks, the underutilization of "hidden gem" community spaces, and newcomers missing out on the mental health benefits of exploring their local natural environment.


### Business benefits
- User wellbeing: encourages outdoor activity, mental health breaks, and physical exercise by gamifying the discovery of nature. 

- Community integration: helps students and newcomers feel more connected to the wider city by pushing them out of their immediate campus or residential bubbles. 

- Resource distribution: disperses foot traffic away from high density tourist parks to lesser known ward parks 

- Personalised utility: quickly solves the problem of finding nearby outdoor spaces based on the user location(postcode/GPS) and specific needs (like closest park, largest park). 


### Options Considered
- Option 1: a lightweight web application that loads the open data csv, calculates distance from the users postcode and uses local Json file or browser local storage to save their visited checklist  

- Option 2: advanced mobile app: a cross platform mobile application that uses live GPS for automatic check ins when a user physically enters a park, storing a progress on a cloud database 

- Option 3: static dashboard: a purely informational dashboard that maps the parks but lacks the interactive user progress saving feature, fails to solve the gamification aspect  


### Expected Risks
- Data Quality Risk: The Open Data Bristol dataset may have missing coordinates, null values for amenities, or outdated boundaries. Mitigation: Clean the dataset programmatically upon load, dropping null-coordinate rows or filling missing text with "Data Unavailable." 

- User Privacy Risk: Calculating distance requires user location data (postcode or coordinates). Mitigation: Process all distance calculations locally on the user's machine; do not send or store user location data to any external server. 

- Data Persistence Risk: The "visited" checklist relies on local storage. If a user clears their browser cache, their progress is wiped. Mitigation: Provide a simple "Export Progress" button that downloads a .Json backup file for the user. 

 
## Project Scope
1. Project Overview & Objectives
The Bristol Green Spaces Explorer is a zero-cost, responsive web application designed to help university students and new residents discover lesser-known parks across Bristol. By gamifying outdoor exploration and using open data, the system encourages physical and mental well-being, fosters community integration, and redistributes foot traffic away from overcrowded central parks (like The Downs or Castle Park) to community green spaces.

- Core Deliverable: A lightweight web application featuring proximity-based searching, facility filtering, interactive map visualization, and local progress tracking.

- Target Audience: University students, newcomers, and local Bristol residents.
  
2. System Context & External Interfaces
Based on the System Context Diagram, the application operates within defined external boundaries:

- User Inputs: Postcode entry, browser GPS authorization, park facility filter selections, and park check-in toggle actions.

- User Outputs: Interactive map view, list of parks sorted by distance, detailed park popups (ward, area, amenities), and downloadable .json progress backups.

- External Data Inputs: Open Data Bristol CSV dataset containing park names, GPS coordinates, ward boundaries, surface areas, and facility types.

- External Services: Map Service (e.g., OpenStreetMap / Nominatim API) providing base map rendering tiles and converting postcode queries into geographic coordinates.

- Data Storage: Browser localStorage for zero-cost, privacy-preserving progress tracking directly on the user's device.
  
3. Scope Boundaries: In-Scope vs. Out-of-Scope
   
In-Scope (Deliverables)
- Data Ingestion & Sanitation: Programmatic processing of the Open Data Bristol dataset on load, filtering out invalid or missing coordinates and setting empty metadata fields to "Data Unavailable."
  
- Proximity & Filtering Engine: Client-side distance calculation sorting parks by proximity to a user's postcode or browser GPS coordinates, combined with filtering by facility type, ward, or size.

- Map & Detail Views: Interactive map markers showcasing park details, surface area, and available facilities.

- Gamified Checklist & Local Backup: A "Visited" checklist stored in browser memory, with an Export/Import Progress feature generating a .json backup file to safeguard against cache wipes.

- Zero-Cost Deployment: Hosting the web application on a free-tier platform (GitHub Pages, Vercel, or Streamlit Cloud).

Out-of-Scope (Future Enhancements)
- Native Mobile Applications: iOS or Android app packages requiring app store distribution.

- Automated Background GPS Tracking: Background location tracking or automatic geofenced check-ins (Option 2).

- Centralized User Accounts: Backend databases, user registration, passwords, or cloud data storage (e.g., Firebase, AWS).

- Live Data Feeds: Real-time crowd density sensors, live weather tracking, or event calendars.
  
4. Technical Constraints, Costs & Time Allocation
   
Cost Matrix
- Dataset: £0 (Public domain data via Open Data Bristol)

- Development Tools & Languages: £0 (Open-source web technologies)

- Hosting & Infrastructure: £0 (GitHub Pages / Vercel / Streamlit Cloud)

- Total Financial Cost: £0

Effort & Time Budget (15–20 Hours Total)
- Data Cleaning & Sanitation (3 hrs): Parsing CSV data, handling null values, standardizing attributes.

- Core Logic & Geocoding (4 hrs): Implementing postcode conversion and client-side distance calculations.

- UI & Interactive Checklist (7 hrs): Designing map views, park filtering controls, checklist UI, and JSON export/import handlers.

- Testing & Zero-Cost Deployment (4 hrs): Verifying browser storage persistence, cross-device testing, and publishing to free web hosting.

5. Risk Assessment & Mitigation
- Data Quality Risk (Severity: Medium): Missing coordinates or incomplete amenity fields in the dataset could break UI components or spatial calculations.
  Mitigation Strategy: Programmatically filter out null coordinates upon data load and set missing text fields to a default value of "Data Unavailable".

- User Privacy Risk (Severity: High): Sensitive user location data (postcode or browser GPS) could be exposed or misused.
  Mitigation Strategy: Perform 100% of spatial distance calculations client-side in browser memory, ensuring user location data is never transmitted to or stored on external servers.

- Data Loss Risk (Severity: Medium): Users clearing their browser storage or cache will delete their saved park checklist progress.
  Mitigation Strategy: Provide a prominent Export/Import Progress feature that allows users to download and upload a .json backup file to save their progress permanently.
<img width="1024" height="765" alt="c2baa37b-34df-445e-b67f-57fbb8860a63" src="https://github.com/user-attachments/assets/968ddc97-e168-4072-be06-6b22e37151b1" />
