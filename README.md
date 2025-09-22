# EX01 Developing a Simple Webserver

# Date: 19/09/2025
# AIM:
To develop a simple webserver to serve html pages and display  the list of protocols in TCP/IP Protocol Suite.


# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler
content ='''
<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Network Model</title>
    <style>
        body
        {
            background-color: #0077b6;
            color: white;
            font-family: Arial, sans-serif;
            margin: 40px;
        }
        h1
        {
            text-align: center;
            text-transform: uppercase;
        }
        h3
        {
            color: #ffdd00;
            margin-top: 25px;
        }
        table 
        {
            width: 100%;
            border-collapse: collapse;
            margin-top: 25px;
        }
        th, td 
        {
            border: 1px solid white;
            padding: 12px;
            text-align: left;
        }
        th
        {
            background-color: #023e8a;
            color: #ffdd00;
        }
        tr:nth-child(even)
         {
            background-color: rgba(255, 255, 255, 0.1);
        }
    </style>
</head>
<body>

    <h1>TCP/IP Network Model</h1>

    <h3>Overview:</h3>
    <p>The TCP/IP model is a framework that defines how data should be transmitted over networks. It consists of layers, each with specific responsibilities.</p>

    <h3>Layers Description:</h3>
    <table>
        <tr>
            <th>Layer</th>
            <th>Function</th>
            <th>Examples</th>
        </tr>
        <tr>
            <td>Application Layer</td>
            <td>Provides network services to end-users and applications.</td>
            <td>HTTP, FTP, SMTP</td>
        </tr>
        <tr>
            <td>Transport Layer</td>
            <td>Ensures reliable or fast delivery of data between devices (error detection, flow control).</td>
            <td>TCP, UDP</td>
        </tr>
        <tr>
            <td>Network Layer</td>
            <td>Handles logical addressing and routing of data packets from source to destination.</td>
            <td>IP, ICMP</td>
        </tr>
        <tr>
            <td>Data Link Layer</td>
            <td>Combines raw bits into frames, handles error recovery and retransmissions.</td>
            <td>Ethernet, ARP</td>
        </tr>
        <tr>
            <td>Physical Layer</td>
            <td>Provides the physical interface for transmission of raw bits over a medium.</td>
            <td>Cables, Hubs</td>
        </tr>
    </table>

    <h3>Key Points:</h3>
    <ul>
        <li>Each layer interacts with the layer above and below it.</li>
        <li>TCP/IP model is the basis for the modern Internet.</li>
        <li>It is simpler than the OSI model but widely used in practice.</li>
    </ul>

</body>
</html>
'''
          

class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address=('',8000)
httpd=HTTPServer(server_address,Myserver)
httpd.serve_forever()
```

## OUTPUT:
![alt text](<Screenshot 2025-09-22 111321.png>)


![alt text](<Screenshot 2025-09-22 111434.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
