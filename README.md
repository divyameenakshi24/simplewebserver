# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
### mywebserver.py
```
from http.server import HTTPServer,BaseHTTPRequestHandler

Content="""
<!doctype html>
<html lang="en">
<head>
<title>my webserver</title>
</head>
<body>
<h1>MULTIPLICATION TABLES OF 4</h1>
4×0=0<br>
4×1=4<br>
4×2=8<br>
4×3=12<br>
4×4=16<br>
4×5=20<br>
4×6=24<br>
4×7=28<br>
4×8=32<br>
4×9=36<br>
4×10=40<br>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recived")

        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')             
        self.end_headers()

     #to send the responce
        self.wfile.write(Content.encode())

 #to create server address     
server_address=('',80)

#to listen at the specified port
httpd = HTTPServer(server_address,myhandler)
print("MY WEBSERVER IS RUNNING...")
httpd.serve_forever()
```


## OUTPUT:
![output](./static/img/d.png)

![output](./static/img/d1.png)

## RESULT:
Thus, a webserver is designed to display multiplication table and is hosted in the URL
http://divya.student.saveetha.in/

