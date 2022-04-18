# ScanOpen
usao de trivy for scan images
sitio de trivy 
https://aquasecurity.github.io/trivy/v0.26.0/getting-started/installation/

https://0x1.gitlab.io/security/Trivy/

ejemplo flask

Docker file agregar y sacar USER verificar con trivy

Archivo DockerFile
FROM python:3.8
COPY ./requirements.txt /webapp/requirements.txt
WORKDIR /webapp
RUN pip install -r requirements.txt
COPY webapp/* /webapp
ENTRYPOINT ["python"]
CMD ["app.py"]

archivo requirements.txt 
flask==1.1.0

archivo app.py en folder webapp
from flask import Flask, abort

app = Flask(__name__)

@app.route('/')
def two_hundred():
    return "200! all is good"

@app.route('/error')
def error():
    abort("500! ohh my god error")

if __name__== "__main__":
    app.run(debug=true, host = "0.0.0.0")
    
    
