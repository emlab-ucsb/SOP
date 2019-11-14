# emLab Standard Operating Procedures

Standard operating procedures for emLab projects:

<https://emlab-ucsb.github.io/SOP/>


## Table of Contents

1. Project Management  
    - Google Calendar
    - Slack
    - Airtable
    - Google Shared Drive
    - Git and GitHub
2. File Structure
    - File Naming
    - Shared Drive Files
    - GitHub Structure
3. Data
    - Metadata
    - Data Directory
    - Tidy Data
4. Code
    - Scripts and Version Control
    - Style Guide
5. High Performance Computing
    - Google Cloud Platform
    - UCSB Server Clusters


## Contributing

The website is built using the `bookdown` package for R. After pulling the latest updates and adding or revising content, use the following command to render the website:

`bookdown::render_book(input = "index.Rmd")`

To produce a clean build of the website, simply delete the 'docs' folder before rendering, which is where generated files are stored. Once rendered, then commit the changes and push to the repo. The GitHub website will automatically update with the new changes.
