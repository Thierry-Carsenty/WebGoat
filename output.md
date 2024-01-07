## OWASP WebGoat Installation Steps:
- Install Docker Desktop
- Install GitHub Desktop
- Fork the WebGoat project then clone it into GitHub desktop
- From GitHub Desktop, open the project with PyCharm IDE (or any other IDE you might use)
- Run the following command:

`docker run -it -p 127.0.0.1:8080:8080 -p 127.0.0.1:9090:9090 webgoat/webgoat`
- This will create a new container of the application on your desktop.
- Then open a web browser and go to: 
http://www.webgoat.local:8080/WebGoat/

# Replacing the WebGoat logo image: 

- Download a new image and place it in the local repository at the following location:  
src/main/resources/webgoat/static/css/img/
- The file should be renamed to: logoBG.jpg so we won't need to modify the CSS code. 
- It might be a good idea to make a backup of the original logoBG.jpg file before replacing it. 
- Install Maven and JDK on your computer and check that both are correctly installed by running: 
  
    `mvn -version`

    `java -version`
- Compile the project with the new screenshot by running the following: 
`./mvnw.cmd clean install`
- build a new docker image by running the following command: 

`docker build -f Dockerfile . -t webgoat/webgoat`

- Once the docker image has successfully been created and the new docker container is running, open the following URL from a web browser: 
http://localhost:8080/WebGoat

