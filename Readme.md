product-service-docker
========================
This is the sample REST Spring boot microservice application to be deployed in Kubernetes minikube cluster.


To build the docker image run following command in the directory where Dockerfile is located:
`$ docker build -t productservice .`

To run the container locally run the following command:
`$ docker run -p 8080:8080 productservice`

Tag the image using following command:
`$ docker tag productservice:latest mirfanmcs/productservice`

Push the image to docker hub:
`$ docker push mirfanmcs/productservice`

Run following command to create Deployment
`$ kubectl create -f productservice-deployment.yml`

Run following command to create Service
`$ kubectl create -f productservice-service.yml`

Run the following command to run the service
`$ minikube service productservicesrv`

OR get the VM IP using following command:
`$ minikube ip`

Enter the IP with the exposed port in the browser URL.

Enter the full URL followed by the port:
http://192.168.99.100:32568//api/product


To scale the application (pods) to 4, run the followig command:
`$ kubectl scale deployment productserviceapp --replicas=4`