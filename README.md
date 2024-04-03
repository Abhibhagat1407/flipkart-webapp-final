Enter here

jdk and java installation

https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-22-04

jenkins installation
https://www.jenkins.io/doc/book/installing/linux/#debianubuntu

#Follow these steps only after completing the whole configuration of the Jenkins, eks, etc.
- ssh into the ec2 instance with the pem key file.
- Update your system with <sudo apt update>
- Then create EKS cluster using the following command:
  ``` eksctl create cluster --name sample1 --region us-east-1 --node-type t2.medium --nodes-min 2 --nodes-max 3 ```
  > The above command will start creating the EKS cluster which will take up to 10-15 minutes to create.
- Open your browser and copy your public IP ADDRESS eg. 100.26.215.169 and map it with the jenkins default port 8080.
  > EXAMPLE: http://100.26.215.169:8080 (this ip is dynamic you need to copy your current ip address and map it with the 8080 port.
- After following the above process you will take you to the Jenkins dashboard page. To log in enter the credentials.

![Screenshot from 2024-04-03 19-38-45](https://github.com/Abhibhagat1407/flipkart-EKS-CICD/assets/109520000/8abf7fd8-1369-4696-9a3c-a82b1ca32aac)

- Here you can see flipkart-clone-pipeline job click on that and click on the play button to run the Pipeline script. Which will deploy your Flipkart-clone application on our previously created EKS cluster.
- Pipline will get start executing and after completing the execution of the pipeline move to your terminal and type following commands.
```
      kubectl get pods 
      kubectl get get nodes 
      kubectl describe pod
      kubectl get svc
```
- The above command are important to see the pods running, nodes we are using, services etc.
- To access our application on the web browser use ``` kubectl get svc ``` this command will provide you the URL where you can find your application running.
![Screenshot from 2024-04-03 19-55-20](https://github.com/Abhibhagat1407/flipkart-EKS-CICD/assets/109520000/bf2a9f74-7d2b-431d-8d06-ce7210622d47)

> This is the example of URL: a0b25faf8cd2640369aeedf78b5ed78f-2046069420.us-east-1.elb.amazonaws.com (copy it and paste it on the browser.)
- You will see your application running on the browser.









  
