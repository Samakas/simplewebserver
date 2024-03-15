# EX01 Developing a Simple Webserver
## Date:26/02/2024

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
    <table align="center" border="2" cellspacing="5" cellpadding="5" width="1200" height="50">
        <caption>TOP IT COMPANIES</caption>
		<tr>
			<th>S.NO</th>
			<th>COMPANIES NAME</th>
			<th>COMPANIES FOUNDER</th>
		</tr>
        <tr>
			<th>1</th>
			<th>GOOGLE</th>
			<th> LARRY PAGE & SERGEY BRIN</th>
		</tr>
        <tr>
			<th>2</th>
			<th>MICROSOFT</th>
			<th>BILL GATES</th>
		</tr>
        <tr>
			<th>3</th>
			<th>TCS</th>
			<th>RATAN TATA</th>
		</tr>
        <tr>
			<th>4</th>
			<th>WIPRO</th>
			<th>M.H. HASHAM PREMJI</th>
		</tr>
        <tr>
			<th>5</th>
			<th>INFOSES</th>
			<th>NARAYANA MURTHY</th>
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


## OUTPUT:
![alt text](<Screenshot 2024-03-15 095002.png>)
![alt text](<Screenshot 2024-03-15 095042.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
