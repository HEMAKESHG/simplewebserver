# EX01 Developing a Simple Webserver
## Date:6/10/2023

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
content = """

<html>
     <title>Top five Revenue Generating Software Companies</title>
<body>
     <table border="2" cellspacing="10" cellpadding="6">
     <caption>Top five Revenue Generating Software Companies</caption>
     <tr>
         <th>S.No</th>
         <th>Companies</th>
         <th>Revenue</th>
     </tr>
      <tr>
         <th>1</th>
         <td>Microsoft</td>
         <td>65 Billion</td>
      </tr>
       <tr>
         <th>2</th>
         <td>Oracle</td>
         <td>29.6 Billion</td>
      </tr>
       <tr>
         <th>3</th>
         <td>IBM</td>
         <td>29.1 Billion</td>
      </tr>
       <tr>
         <th>4</th>
         <td>SAP</td>
         <td>6.4 Billion</td>
      </tr>
       <tr>
         <th>5</th>
         <td>Symantec</td>
         <td>5.6 Billion</td>
      </tr>
</table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![image](https://github.com/HEMAKESHG/simplewebserver/assets/144870552/cc568c6b-2057-43d7-a55f-23590bd1e0d3)
![image](https://github.com/HEMAKESHG/simplewebserver/assets/144870552/eb8d73d7-741a-4fb0-a6cd-9f1975af9b7a)


## RESULT:
The program for implementing simple webserver is executed successfully.
