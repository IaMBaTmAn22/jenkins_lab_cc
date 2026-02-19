FROM python:3.9-slim

WORKDIR /app

RUN echo 'from http.server import BaseHTTPRequestHandler, HTTPServer
import socket

class Handler(BaseHTTPRequestHandler):
    def do_GET(self):
        hostname = socket.gethostname()
        self.send_response(200)
        self.end_headers()
        self.wfile.write(f"Served by backend: {hostname}".encode())

HTTPServer(("0.0.0.0", 8080), Handler).serve_forever()' > app.py

CMD ["python", "app.py"]
