📌 Overview
This project is a Python-based honeypot system that simulates vulnerable services (HTTP login and Telnet) to capture attacker behavior. It logs credentials, commands, and network activity, detects brute-force attacks, and provides a dashboard for monitoring.

 🚀 Features
- Simulated IoT login system (HTTP) and Telnet service  
- Captures username, password, IP address, and attacker commands  
- Monitors TCP network traffic using packet sniffing  
- Logs authentication attempts, telnet commands, and network connections  
- Detects brute-force attacks based on repeated login attempts  
- Displays data through a Flask-based web dashboard  

 🛠️ Technologies Used
- Python  
- Flask  
- SQLite  
- Socket Programming  
- Scapy  
- HTML (Jinja Templates)  

 ⚙️ System Components

 HTTP Honeypot (Port 8080)
- Simulates IoT device login page  
- Captures credentials and IP address  
- Always returns "Login Failed"

 Telnet Honeypot (Port 2323)
- Simulates command-line interface  
- Captures login credentials  
- Logs attacker commands  
- Responds with fake shell output  

 Network Packet Sniffer
- Uses Scapy to capture TCP packets  
- Extracts IP, port, and TCP flags  
- Stores data in database  

 Attack Detection Module
- Monitors login attempts continuously  
- If attempts from an IP exceed 5:
  - Flags Brute Force Attack  
  - Stores alert in database  
  - Prints alert  

 Web Dashboard (Port 9000)
- Displays login attempts in table format  
- Shows latest activity first  

▶️ Setup & Usage

 Install Dependencies
pip install flask scapy

 Initialize Database
python db_setup.py

Run Components (in separate terminals)

HTTP Honeypot:
python login_server.py

Telnet Honeypot:
python telnet_honeypot.py

Packet Sniffer:
python sniffer.py

Attack Detector:
python detector.py

Dashboard:
python app.py

 📂 Project Structure
project/
│── login_server.py
│── telnet_honeypot.py
│── sniffer.py
│── detector.py
│── app.py
│── db_setup.py
│── honeypot.db
│── templates/
│     └── index.html

 📊 Detection Logic
- Groups login attempts by IP  
- If attempts > 5 → Brute Force Attack  
- Alerts stored in database  

 📈 Results
- Captured multiple login attempts and attacker inputs  
- Detected repeated login attempts from same IP  
- Logged TCP packet data showing connection patterns  

 🎯 Learning Outcomes
- Understanding of honeypot systems and attacker behaviour  
- Experience with Flask, sockets, and packet sniffing  
- Implementation of basic intrusion detection logic  
- Working with SQLite for logging  

 ⚠️ Limitations
- Stores credentials in plain text (for analysis only)  
- Basic detection logic  
- Requires admin privileges for packet sniffing  
- Not production-ready  

 🔮 Future Improvements
- IP blocking/rate limiting  
- Real-time alert system  
- Data visualisation  
- Secure logging (hashing)  
- Advanced detection techniques  

---

## ⚠️ Note
This project demonstrates multi-layer monitoring (application, service, and network level).
