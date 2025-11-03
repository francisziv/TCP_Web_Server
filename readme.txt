TCP Web Server - README

Overview
This project contains the server implementation in C++ (all .cpp and .h files are in the TCP_WEB_SERVER folder). The server is a simple TCP-based web server intended to serve static content for several languages.

Requirements
- C++17 or newer (mandatory)
- Windows (tested on Windows 10/11)

Content setup (static files to serve)
Extract the provided compressed content into the following root directory:
C:\temp
After extraction, the directory structure should look like this:
- C:\temp\en
- C:\temp\he
- C:\temp\fr
Each language directory must contain:
- index.html
- index.files (directory with the page assets)

Build (from the project folder)
Using MSVC (Developer Command Prompt):
cl /std:c++17 /EHsc /W4 /Fe:TcpWebServer.exe *.cpp

Using MinGW/LLVM g++ (PowerShell/CMD):
g++ -std=c++17 -O2 -Wall -Wextra -o TcpWebServer.exe *.cpp

Run
PowerShell/CMD:
TcpWebServer.exe [port] [root_dir]
Defaults (if not provided):
- port: 8080
- root_dir: C:\temp

Examples
- TcpWebServer.exe
- TcpWebServer.exe 9090
- TcpWebServer.exe 8080 C:\temp

Test
After the server is running, open a browser and try:
- http://localhost:8080/en/
- http://localhost:8080/he/
- http://localhost:8080/fr/

Notes
- Ensure the C:\temp structure exists exactly as described so that GET requests can resolve the correct files.
- If you change the root_dir, mirror the same en/he/fr structure under that directory.
