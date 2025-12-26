# EX01 Developing a Simple Webserver
## Date:11-12-2025

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
from http.server import HTTPServer,BaseHTTPRequestHandler
content ="""
<!DOCTYPE html>
<html>
<head>
  <title> SIMPLE SERVER  varuna </title>
  <style>
    *{
            font-family: 'Times New Roman';
        }

body {
  font-family: 'MyFont', sans-serif;
}
  </style>

</head>
<body style="background-color:black ; overflow:hidden;">
    <h1 style="position:absolute; left: 70px; top: 50px; color:white; font-size:48px; "> LAP SPECIFICAATIONS </h1>
    <p  style="position:absolute; left: 70px; top: 400px; color:white; font-size:24px; width:800px;">
      Device name	TMP215-75-G2 <br>Processor	Intel(R) Core(TM) Ultra 5 125H (1.20 GHz)<br> Installed RAM	16.0 GB (15.5 GB usable)<br>Device ID	E3F06795-1915-4187-8C56-F3F3634559FF<br>Product ID	00342-42784-08492-AAOEM<br>System type	64-bit operating system, x64-based processor<br>Pen and touch	No pen or touch input is available for this display
    </p>
</body>
</html>

"""
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
~~~

## OUTPUT:
<img width="1033" height="549" alt="Screenshot 2025-12-11 203323" src="https://github.com/user-attachments/assets/71f421f7-3b3b-4b79-a609-51f6b75760b2" />



## RESULT:
The program for implementing simple webserver is executed successfully.
