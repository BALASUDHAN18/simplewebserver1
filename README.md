# EX01 Developing a Simple Webserver
## Date:5/10/2023

## AIM:
To develop a simple webserver to serve html pages.

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler

# HTML content with a list of the top 5 revenue-generating companies
content = """
<!DOCTYPE html>
<html>
<head>
    <title>Top 5 Revenue-Generating Companies</title>
</head>
<body>
    <h1>Top 5 Revenue-Generating Companies</h1>
    <ol>
        <li>Apple</li>
        <li>Saudi</li>
        <li>Amazon</li>
        <li>Microsoft</li>
        <li>Google</li>
    </ol>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 80)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![Screenshot 2023-10-07 154210](https://github.com/BALASUDHAN18/simplewebserver1/assets/118807740/de41aa75-f20c-4372-b2c2-e2555c047332)
## RESULT:
The program for implementing simple webserver is executed successfully.
