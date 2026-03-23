# Security Automator Tool

**How to Run the Application**
  
1. Run in GitHub Codespaces (Recommended)  
Open this repository on GitHub.  
Click Code → Codespaces → Create Codespace on main.  
Wait for the environment to load.  
Open the terminal inside Codespaces.  
Run:         &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bash demo.sh  
  
2. Run Manually Inside the Repository (Local Machine)  
If you downloaded or cloned the repository:  
Open a terminal.  
Navigate to the project folder.  
Example:  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cd Security-Automation-Tool  
Run the launcher:  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bash demo.sh  

3. If You Are Using a Random Public Terminal  
Public terminals do not automatically have this project. You must first download or clone the repository.  
A. Option A — Clone with Git  
Type:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;git clone https://github.com/USH3R/Hackathon-Project-Security-Automation-Tool.git  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cd Hackathon-Project-Security-Automation-Tool  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bash demo.sh  
B. Option B — Download ZIP  
Click Code → Download ZIP on GitHub.  
Extract the folder from the ZIP file. Then,  
Open a terminal in that folder.
Run / Type: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bash demo.sh
            
4. Quick Start Command  
This command is only for use inside a Terminal (like the one in Codespaces, terminal, or on your local machine).  
    Verify Your Location: Ensure your terminal is currently pointed at the project directory;  
    You should see Hackathon-Project-Security-Automation-Tool in your command prompt.  
    If you have already performed the setup in steps 1, 2, or 3 and just need to restart the application, type:   
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bash demo.sh 
---

**This tool reduces manual analysis time for SOC analysts.**

Here’s a quick rundown of what this Security Automation Tool / script is doing and what its output will look like:
What it does
IP Validation
Uses a precise regex to validate IPv4 addresses (0.0.0.0 → 255.255.255.255).
Invalid formats (like 999.999.999.999 or not_an_ip) get flagged.
Incident Staging
For valid IPs, it creates a JSON-like log entry with:
Timestamp (UTC ISO format)
Target IP
Severity (HIGH by default)
Action (STAGED_FOR_BLOCK)
Return
Returns a dictionary indicating success (SUCCESS) or error (ERROR).
Test Suite
Runs four sample IPs through stage_incident to verify logic without user input.

Sample Output
🔍 RUNNING AUTOMATED LOGIC TEST...
========================================
[SUCCESS] Testing 8.8.8.8: {'timestamp': '2026-03-18T21:50:12.345678Z', 'target_ip': '8.8.8.8', 'severity': 'HIGH', 'action': 'STAGED_FOR_BLOCK'}
[ERROR] Testing 999.999.999.999: Invalid IP format: 999.999.999.999
[SUCCESS] Testing 10.0.0.1: {'timestamp': '2026-03-18T21:50:12.345789Z', 'target_ip': '10.0.0.1', 'severity': 'HIGH', 'action': 'STAGED_FOR_BLOCK'}
[ERROR] Testing not_an_ip: Invalid IP format: not_an_ip

✅ Highlights
Clean separation of validation, staging, and logging.
Handles errors gracefully without crashing.
Ready for integration into a larger SOC automation workflow.
