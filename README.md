# Docker_Projects
this repo is for all the docker labs/projects 


This projects walk us through on how to write a Dockerfile from code,build the docker image from Dockerfile and create a container using docker image 

STEP1 -> Create a Folder and create 3 files app.py , requirements.txt, Dockerfile 

  <img width="437" height="152" alt="Screenshot 2026-07-07 195255" src="https://github.com/user-attachments/assets/06b83d44-8f40-4ecb-a5d8-fbeccc7c4d3f" />

STEP2 -> Open app.py and write a simple flask application 

		command => vi app.py 

	 <img width="573" height="275" alt="Screenshot 2026-07-07 195509" src="https://github.com/user-attachments/assets/3e154c45-fe3c-4aa7-a2ab-9c1b5b9714bd" />

STEP 3 : Open requirements.txt and write dependencies  for app.py  to run  

		command => vi requirements.txt	 




<img width="332" height="216" alt="Screenshot 2026-07-07 195543" src="https://github.com/user-attachments/assets/77ed5b76-1f48-4246-b9cb-a81ff7443105" />

 

 

STEP 4 : write a dockerfile to build an image 

Command => vi Dockerfile  
<img width="542" height="222" alt="Screenshot 2026-07-07 195558" src="https://github.com/user-attachments/assets/c2bb1383-6455-4a89-9ece-d9c56147e052" />

 

Analysing dockerfile -> 

Our code is in python so python3.8-slim, a lightweight version of python, is taken as base image 

WORKDIR will create an “/app” folder inside your container (first it will create a folder inside the image which is going to be built). 

RUN pip install will install dependencies (Flask 2.0.1 version and Werkzeug 2.0.1 version), written inside requirements.txt, inside the image. 

COPY will copy the code inside the docker image 

EXPOSE will open the port “5000” , so when the application will run it will listen on port 5000 

CMD is used so when container will run we want to run the app.py inside the container. If we don’t specify this then we must manually login inside the container and run this command to run the application which defeats the whole purpose of scripting 


Step 5: Run the docker build command to build docker image from docker file 

 <img width="735" height="112" alt="Screenshot 2026-07-07 195745" src="https://github.com/user-attachments/assets/e47a37f1-bd52-408b-8cf8-4950902feb3a" />


Step 6: check the image is build or not  

 <img width="735" height="112" alt="Screenshot 2026-07-07 195745" src="https://github.com/user-attachments/assets/1b623402-70f0-4e5b-bac2-dca926af3d4d" />


Step 7: run the docker image to create the container 

 <img width="1067" height="22" alt="Screenshot 2026-07-07 200039" src="https://github.com/user-attachments/assets/e74ed15d-3aab-4508-ab21-dd08018615b0" />


STEP 8: check if container is running or not 

 <img width="1496" height="67" alt="Screenshot 2026-07-07 200011" src="https://github.com/user-attachments/assets/e97e9c9f-13c2-444a-b7e9-fbbf9300fcaf" />


STEP 9: visit http://localhost:5000 to see the output  

 <img width="655" height="166" alt="Screenshot 2026-07-07 200052" src="https://github.com/user-attachments/assets/d73379c9-6979-4924-b235-07f7d3ca3a7b" />


 

RESULT -> your container is running fine  
