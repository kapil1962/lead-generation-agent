🚀 Lead Generation Automation - Google Maps to Email Extractor
An automated n8n workflow that extracts business information from Google Maps and intelligently scrapes websites to collect email addresses for lead generation.
📋 Overview
This workflow automates the entire lead generation process by:

Scraping business listings from Google Maps
Extracting website URLs from businesses
Intelligently scraping each website for email addresses
Filtering and processing the collected data
Exporting results to Google Sheets

✨ Features

Google Maps Scraping: Automated extraction of business listings with website URLs
Smart Website Scraping: Intelligent processing to prevent IP blocking with built-in delays
Email Extraction: Regex-based email address detection from website HTML
Data Filtering: Automatic removal of duplicates and empty results
Export to Sheets: Direct integration with Google Sheets for easy access

🔧 Workflow Steps
STEP 1: Google Maps Data Extraction

Initiates workflow with a test trigger
Scrapes Google Maps for business listings
Extracts business website URLs
Filters and removes irrelevant domains
Removes duplicate entries
Limits results for processing

STEP 2: Website URL Processing

Prepares extracted URLs for scraping
Ensures proper URL formatting

STEP 3: Smart Website Scraping

Processes each website individually to prevent IP blocking
Implements loop-over-items strategy with built-in delays
Fetches complete website HTML content
Handles errors gracefully

STEP 4: Email Extraction & Export

Extract Emails: JavaScript regex finds all email addresses in website HTML
Filter Out Empties: Removes websites with no emails found
Split Out: Processes multiple emails per website
Remove Duplicates: Ensures unique email entries (2 passes)
Add to Sheet: Exports final results to Google Sheets

🛠️ Prerequisites

n8n instance (self-hosted or cloud)
Google Maps API access or scraping tool
Google Sheets API credentials
Basic understanding of n8n workflows

📦 Installation

Clone this repository:

bashgit clone https://github.com/yourusername/lead-generation-n8n.git
cd lead-generation-n8n

Import the workflow into n8n:

Open n8n interface
Go to Workflows → Import from File
Select the workflow.json file


Configure credentials:

Set up Google Sheets API credentials
Configure any required API keys for scraping tools



⚙️ Configuration
Google Maps Scraper

Configure search parameters (location, business type, etc.)
Set the number of results to scrape

Website Scraping

Adjust delay timers between requests (default helps prevent blocking)
Modify the loop-over-items configuration as needed

Email Extraction

Email regex pattern is pre-configured
Customize filtering rules if needed

Google Sheets Export

Specify target spreadsheet
Configure sheet name and column mappings

🎯 Usage

Open the workflow in n8n
Click "Test workflow" to start the process
Monitor the execution:

Green nodes indicate successful completion
Check item counts at each step


Access extracted leads in your Google Sheets

📊 Output Format
The workflow exports the following data to Google Sheets:

Business Name (if available)
Website URL
Extracted Email Address
Additional metadata as configured

🔄 Workflow Details
Total Items Processed: 3 items at various stages

After filtering: 3 items
After scraping: 3 items
After email extraction: Variable based on findings

Key Nodes:

Wait Nodes: Prevent rate limiting and IP blocking
Filter Nodes: Ensure data quality
Remove Duplicates: Two-stage duplicate removal for accuracy

⚠️ Important Notes

Rate Limiting: Built-in delays help prevent IP blocking
Compliance: Ensure your usage complies with website terms of service and GDPR/data protection laws
Ethical Use: Only use for legitimate business purposes with proper consent
Resource Usage: Processing time depends on the number of websites scraped

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the repository
Create your feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
🙏 Acknowledgments

Built with n8n - Fair-code automation platform
Google Maps for business data
Community contributors and testers

📧 Contact
Your Name - @yourtwitter
Project Link: https://github.com/yourusername/lead-generation-n8n
🔍 Troubleshooting
No emails found?

Check if websites have contact pages
Verify the email regex pattern
Some websites may use contact forms instead of visible emails

Getting blocked?

Increase wait times between requests
Consider using proxy services
Reduce the number of concurrent requests

Workflow errors?

Verify all credentials are properly configured
Check API rate limits
Review n8n logs for specific error messages


⭐ If you find this project helpful, please give it a star!
