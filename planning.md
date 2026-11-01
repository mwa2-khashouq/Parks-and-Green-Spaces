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
TODO: Scope of the System of Interest. Include a bullet list of things from your context diagram that are in scope.

![Insert your Context Diagram Here](images/context.png)
