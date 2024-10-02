import android
import os
from http.server import BaseHTTPRequestHandler, HTTPServer

droid = android.Android()

# Function to shut down the phone
def shutdown_phone():
    os.system("reboot -p")

# Create a request handler for HTTP server
class ShutdownHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        # When someone opens the URL, it triggers the shutdown
        self.send_response(200)
        self.send_header('Content-type', 'text/html')
        self.end_headers()
        self.wfile.write(b"<html><body><h1>Phone is shutting down...</h1></body></html>")
        shutdown_phone()

# Start a simple web server
def run_server():
    server_address = ('', 8080)  # Listen on port 8080
    httpd = HTTPServer(server_address, ShutdownHandler)
    httpd.serve_forever()

# Start the server
run_server()
