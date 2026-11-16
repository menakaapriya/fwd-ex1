# EX01 Developing a Simple Webserver
## Date:16/11/2026
## Reg no:26018669

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
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
 ~~~
 from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Suite</title>
</head>
<body>

    <h1>TCP/IP Protocol Suite</h1>

    <h2>List of Protocols</h2>

    <ol>
        <li>Application Layer
            <ul>
                <li>HTTP</li>
                <li>HTTPS</li>
                <li>FTP</li>
                <li>SMTP</li>
                <li>DNS</li>
                <li>Telnet</li>
            </ul>
        </li>

        <li>Transport Layer
            <ul>
                <li>TCP</li>
                <li>UDP</li>
            </ul>
        </li>

        <li>Internet Layer
            <ul>
                <li>IP</li>
                <li>ICMP</li>
                <li>ARP</li>
            </ul>
        </li>

        <li>Network Access Layer
            <ul>
                <li>Ethernet</li>
                <li>Wi-Fi</li>
                <li>PPP</li>
            </ul>
        </li>
    </ol>

</body>
</html>


"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
 ~~~

## OUTPUT:
![alt text](<Screenshot 2026-11-15 212320.png>)
![alt text](<Screenshot 2026-11-15 212347.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

