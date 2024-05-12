# EX01 Developing a Simple Webserver
## Date:7/3/2024

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
content="""
<html>
<title>Top Software Industries</title>
<body>
<table border="2" cellspacing="10" cellpadding="6">
<caption>Top 5 Revenue Generating Software Companies </caption>
<tr>
<th>s.no</th>
<th>companies</th>
<th>revenue</th>
</tr>
<tr>
<th>1</th>
<th>Microsoft</th>
<th>65 billion</th>
</tr>
<tr>
<th>2</th>
<th>oracle</th>
<th>29.6 billion</th>
</tr>
<tr>
<th>3</th>
<th>IBM</th>
<th>29.1 billion</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>6.4 billion</th>
</tr>
<tr>
<th>5</th>
<th>SYMENTEC</th>
<th>6 billion</th>
</tr>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header("content-type", "text/html; charset-utf-8")
        self.end_headers()
        self.wfile.write(content.encode())
server_address=('',8000)
httpd=HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![Screenshot (16)](https://github.com/Sushiendar/simplewebserver/assets/159266287/7f1fa5fd-4d46-47a4-a94e-99327eb1088b)

![Screenshot 2024-03-11 222232](https://github.com/Sushiendar/simplewebserver/assets/159266287/875582e4-8f5e-476c-ae17-34e07b33a29c)




## RESULT:
The program for implementing simple webserver is executed successfully.
