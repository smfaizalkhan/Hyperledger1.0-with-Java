# Hyperledger1.0-with-Java
Hyperledger1.0 with Java

PreRequsites
 
  1) cURL 
          - Shipped along with Ubuntu
  2) Docker and Docker-compose
          a ) First way of instlaling docker
              - sudo apt-get update
              - sudo apt-get install docker-ce
     Installing docker will install the docker compose as well     
     
          b) Second Way of installing docker
          
              -  Issue the command
                  
                  Docker
                  wget -qO- https://get.docker.com/ | sh 
                  sudo service docker stop
                  nohup sudo docker daemon --api-cors-header="*" -H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock&
                  
                  Docker Compose
                  
                   curl -L https://github.com/docker/compose/releases/download/1.8.0/docker-compose-`uname -s`-`uname -m` >            /usr/local/bin/docker-compose
                  chmod +x /usr/local/bin/docker-compose
                  docker-compose --version
 3) Installing GO (Hyperledger 1.0 supports GO 1.7)
  
        -  wget https://storage.googleapis.com/golang/go1.7.4.linux-amd64.tar.gz
        -  sudo tar -xvf go1.7.4.linux-amd64.tar.gz
        
        Setting GO PATH
          
        -  export GOROOT = /home/faizal/go  (Given is my GOROOT,Please change as per your PATH)
        -  export GOPATH = $HOME/go
        -  export PATH = $PATH:$GOPATH/bin
    
     Restart the system for the PATHS toke effect or execute the command source ~/.profile
  
  4) Install JAVA1.8 or Above
       Setting JAVA Path

         - export JAVA_HOME="/usr/lib/jvm/java-8-oracle"
         - export PATH=$JAVA_HOME:/$PATH

  5) Install Maven

         sudo apt-get update
         sudo apt-get install maven

  6) Clone the project 
 
           git clone https://github.com/hyperledger/fabric-sdk-java.git
           
           Navigate to  /src/test/fixture in terminal
          
           Run the docker-compose -f docker-compose.yml file 

  7) Open the terminal from the respective folder structure and run the maven test as mvn test
      
           If any error pops out as 
 
           Caused by: java.io.FileNotFoundException: xxxxx/xxx/xxx/fabric-sdk-java/target/protoc-                 `		dependencies/89c38d9d9690c5948055933a19673654/google/type/timeofday.proto (No such file or directory)

        Create Maven project n eclipse and created a proto file and tried to create Java classes out of it.It generated the file

/eclipse-workspace/xxxxx/target/protoc-dependencies/89c38d9d9690c5948055933a19673654/google/xxx.proto files.
 
         Copy the target/protoc-dependencies/89c38d9d9690c5948055933a19673654/google/xxx.proto files and paste it into fabric-sdk-java


 8) Now run "mvn test" from Project folder in terminal "mvn install -DskipTests" to run integration test

  To Run the test from Eclipse and to understand Flow 



 
           

   1) Install Eclipse Neon 

        Create a new Project from eclipse 
        Import exiting Maven projects into created Project in eclipse
        
        ![screenshot from 2017-07-19 17-39-53](https://user-images.githubusercontent.com/22238550/28369611-33452f18-6ca9-11e7-9ad4-460fb0c4e9d8.png)

        
  As  the containers are running and now we have the project in ecipse ,place a breakpoint and run End2EndITtest.java as Junit 
        

