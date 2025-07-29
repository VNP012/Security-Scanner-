# Security-Scanner-
Python based security scanner and report generator 
AutoRecon is a Python-based security scanning tool that performs common port scanning, SSL/TLS certificate inspection, basic endpoint exposure checks, and generates an HTML report. It is designed for quick recon, red-team analysis, self-assessment, or instructional purposes.

Why This Matters

In cybersecurity, visibility is critical. AutoRecon helps by automating the discovery of open ports, misconfigurations, and certificate data on a target. This is useful for ethical hackers, sysadmins, and learners alike. It offers a starting point for further vulnerability analysis or environment hardening.

Features

Asynchronous port scanning using asyncio for fast enumeration.
SSL certificate inspection (issuer, subject, and validity window).
Basic web endpoint checks for potential leaks (like /admin, .env).
Clean HTML report generation for documentation or analysis.
Modular, extensible Python architecture.
Prerequisites

This project requires Python 3.9 or higher. The following Python packages must be installed:

httpx
jinja2

Install them using the command:

pip install httpx jinja2

Folder Structure

The folder should look like this:

autorecon/
├── autorecon.py
├── templates/
│ └── report_template.html
└── output/
  └── report.html

Setup Instructions

To begin, open your terminal and navigate to the Documents folder. Create the working directory:

cd ~/Documents
mkdir autorecon
cd autorecon

Now create the main Python file:

nano autorecon.py

Paste the contents of autorecon.py from this repository. Save and exit the editor.

Next, create a folder for the HTML report template:

mkdir templates
nano templates/report_template.html

Paste the HTML template provided in the templates folder of this repository. Save and exit.

Then, install the required dependencies if you haven’t already:

pip install httpx jinja2

Running the Scanner

To run the scanner on a domain, use:

python3 autorecon.py example.com

Replace example.com with your target domain. After execution, the output report will be created at:

output/report.html

To open the report on macOS:

open output/report.html

Sample Output

Running the scan on github.com will typically return open ports such as 22, 80, and 443. The SSL certificate data will be extracted and displayed. If the domain hosts any exposed endpoints matching the default list (e.g. /admin, /.env), they will also appear in the report.

Project Importance

AutoRecon demonstrates how Python can be applied in the cybersecurity domain for real-world recon tasks. It combines practical concepts such as socket programming, TLS/SSL analysis, asynchronous execution, HTML reporting, and modular script design. It’s intended as a learning tool and a practical starter framework for more advanced assessments.

Possible Future Enhancements

Secret scanning using regex for API keys, tokens, JWTs
WHOIS and DNS subdomain enumeration
CVE identification from service banners
Live terminal output with libraries such as rich
JSON output option for integration with other tools
Author

This project was developed by [YourNameHere]. Contributions and forks are welcome. Pull requests are encouraged for additional scanning modules or reporting features.

License

This project is licensed under the MIT License.

