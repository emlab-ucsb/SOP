# emLab Standard Operating Procedures

Standard operating procedures for emLab projects:

<https://emlab-ucsb.github.io/SOP/>


## Table of Contents

1. Project Management  
    - Google Calendar
    - Zoom
    - Slack
    - Airtable
    - Google Shared Drive
    - Git and GitHub
    - Zotero
2. File Structure
    - Folder Naming
    - Shared Drive Files
    - GitHub Structure
3. Data
    - Data File Naming
    - Metadata
    - Data Directory
    - Tidy Data
    - Data Formats
4. Code
    - Scripts and Version Control
    - Style Guide
    - Reproducibility
5. High Performance Computing
    - Google Cloud Platform
    - UCSB Server Clusters
6. Reports and Publications
    - emLab Affiliation
    - Reports
    - Author Contribution
    - Making Your Data Publicly Available
    - Preparing a Public GitHub Repository


## Contributing

The website is built using the `bookdown` package for R. After pulling the latest updates and adding or revising content, use the following command to render the website:

`bookdown::render_book(input = "index.Rmd")`

To produce a clean build of the website, simply delete the 'docs' folder before rendering, which is where generated files are stored. Once rendered, then commit the changes and push to the repo. The GitHub website will automatically update with the new changes.
