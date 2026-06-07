ROCHESTER NEIGHBORHOOD INTELLIGENCE SUITE

Welcome to the Rochester Neighborhood Intelligence Suite. This repository contains a powerful collection of five independent Python programs designed to gather, filter, and output critical localized data for Rochester, NY. 

By combining real estate metrics, public safety data, economic growth indicators, and local event schedules, this suite acts as a comprehensive neighborhood intelligence tool.

--- PREREQUISITES ---
Before running these scripts, ensure you have Python installed and the required third-party libraries:

pip install requests beautifulsoup4 cloudscraper

API Requirements:
* RapidAPI Key: Required *only* for the Real Estate Scraper. You must subscribe to the 'real-estate-zillow-com' API on RapidAPI's Free Tier.
* All other scripts tap into free, public government Open Data portals or use local static intelligence and do not require API keys.

--- THE PROGRAMS ---

1. ZillowRecentlySold (ZillowRecentlySold.py)
Tracks property values and housing market movement.
* Data Source: RapidAPI (real-estate-zillow-com)
* Functionality: Targets the /v1/search/sold and /v1/search endpoints to bypass folders and strictly pull a cleanly formatted list of recently sold homes or active listings, including their Zillow links and exact prices.

2. RecentCrime (RecentCrime.py)
Monitors neighborhood safety and recent Part I Crimes.
* Data Source: Rochester Police Department Open Data (ArcGIS)
* Functionality: Connects to the RPD server, strips out massive map polygon coordinates to prevent crashes, and filters the city's 30-day crime log to only display incidents from the past 7 days in a readable format.

3. NewBusinesses (NewBusinesses.py)
Tracks new corporate and LLC registrations to see where business is booming.
* Data Source: New York State Open Data Portal (Socrata)
* Functionality: Queries the Active Corporations database. Uses advanced SoQL to perfectly filter case-sensitive data and extract the 25 newest businesses registered in the Rochester area.

4. ActiveConstruction (ActiveConstruction.py)
Monitors massive, multi-million dollar capital construction projects that anchor neighborhoods.
* Data Source: DASNY (Dormitory Authority of the State of New York) Open Data
* Functionality: Filters for Monroe County to display major institutional builds (like universities and hospitals), complete with multi-million dollar budget formatting and projected timelines.

5. FestivalFinder (FestivalFinder.py)
A static intelligence module detailing high-value public events for vendor opportunities.
* Data Source: Hardcoded Local Intelligence
* Functionality: Uses a rock-solid, hardcoded dictionary of Rochester's most profitable, vendor-friendly festivals (e.g., Lilac Festival, Corn Hill Arts Festival) to ensure 100% uptime for your master dashboard.

--- HOW TO RUN ---
Each script is designed to run independently in your terminal. For example:
python RecentCrime.py

Note: For ZillowRecentlySold.py, ensure you have pasted your valid X-RapidAPI-Key into the master execution block before running.
