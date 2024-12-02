# EX01 Developing a Simple Webserver
# Date:28.10.2024
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
1.views.py
```
from django.shortcuts import render,HttpResponse
from http.server import HTTPServer,BaseHTTPRequestHandler

content = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lenovo ThinkPad E16 Specifications</title>
</head>
<body style="font-family: Arial, sans-serif; line-height: 1.6; margin: 0; padding: 0; background-color: #fefae0;">
    <div style="max-width: 800px; margin: 20px auto; padding: 20px; background: #ffffff; border-radius: 8px; box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); border-left: 6px solid #ff8303;">
        <h1 style="text-align: center; color: #03ff07; margin-bottom: 20px;">Lenovo ThinkPad E16 Specifications</h1>
        <table style="width: 100%; border-collapse: collapse; margin: 20px 0;">
            <tr>
                <th style="border: 1px solid #ddd; padding: 10px; background-color: #ff8303; color: white; text-align: left;">Specification</th>
                <th style="border: 1px solid #ddd; padding: 10px; background-color: #ff8303; color: white; text-align: left;">Details</th>
            </tr>
            <tr style="background-color: #00fff7;">
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">Processor</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">Intel Core i7-1355U (12th Gen)</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">Operating System</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">Windows 11 Pro</td>
            </tr>
            <tr style="background-color :#00fff7;">
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">Display</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">16" FHD+ (1920x1200) IPS, Anti-Glare, 300 nits</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">Memory</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">16GB DDR4</td>
            </tr>
            <tr style="background-color: #00fff7;">
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">Storage</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">512GB SSD</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">Graphics</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">Intel Iris Xe Graphics</td>
            </tr>
            <tr style="background-color: #00fff7;">
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">Battery Life</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">Up to 12 hours</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">Weight</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">1.78 kg (3.92 lbs)</td>
            </tr>
            <tr style="background-color: #00fff7;">
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">Ports</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #000000;">USB-C, USB 3.2, HDMI, Ethernet, Audio Jack</td>
            </tr>
            <tr>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">Price</td>
                <td style="border: 1px solid #ddd; padding: 10px; color: #00ff2a;">$1,099 (starting price)</td>
            </tr>
        </table>
    </div>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,Myserver)
httpd.serve_forever()
```

2.urls.py
```
from django.contrib import admin
from django.urls import path
from lapspec import views

urlpatterns = [
    path('admin/', admin.site.urls),
]
```
# OUTPUT:
![Screenshot 2024-11-30 140941](https://github.com/user-attachments/assets/f2abf1f4-9a85-40df-9fb6-66aa7cec388d)
![Screenshot (17)](https://github.com/user-attachments/assets/a66b47d4-7ae3-4218-b596-8118ebc7d111)


# RESULT:
The program for implementing simple webserver is executed successfully.
