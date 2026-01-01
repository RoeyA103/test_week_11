# create Dockerfile inside your app directory 
echo "" > Dockerfile

# Enter the following content

"FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8080

CMD [ "streamlit", "run" ,"main.py" ,"--server.port", "8080" ,"--server.address=0.0.0.0" ]"

# add dockerignore file

echo "" > .dockerignore

# Enter the following content
.git/
__pychach__/

# connect to your docker hub
docker login 

# inside the app folder
docker build -t your_yusername/myapp:latest .

# add to docker hub
docker push your_yusername/myapp:latest

# after it finished check it it working localy
docker run -p 8080:8080 your_yusername/myapp:latest

# check container status
docker ps

# copy the contianer hash and chack logs
docker logs {hash}

# for more information 
docker inspect {hash}

# chack localy from your brows
open http://localhost:8080
