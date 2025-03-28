# EX01 Developing a Simple Webserver
## Date:18.03.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.


## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
from http.server import HTTPServer,BaseHTTPRequestHandler
content="""" 
<!DOCTYPE html>
<html>
<head>
    <title>Simple Table</title>
    <style>
        table {
            width: 50%;
            border-collapse: collapse;
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <h2>TCP/IP Protocols</h2>
    <table>
        <tr>
            <th>S.no</th>
            <th>Layers</th>
            <th>Protocols</th>
        </tr>
        <tr>
            <td>1</td>
            <td>Application Layer</td>
            <td>HTTP,FTP,Telnet,DNS</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Transport Layer</td>
            <td>TCP,UDP</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Internet Layer</td>
            <td>IPv4,IPv6</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Network Access Layer</td>
            <td>Ethernet,MAC</td>
        </tr>
    </table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address=('',8000)
httpd=HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:
![alt text](481616889_1392599598580430_2178610269567281601_n.png)
![Simple web browser](https://github.com/user-attachments/assets/c7cfd9d5-ae5b-4216-8448-d532d3d5a6f4)


 SANTHOSHKUMAR P(212224220055)
## RESULT:
The program for implementing simple webserver is executed successfully.
