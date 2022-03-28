# abs-assessment
Below are step by step guide 

1. tar -xvf abs-guide.tar

#Above command untar file 

By using Dockerfile, we can create docker image

2. docker build -t abs-guide .

Create docker tag 

3. docker tag abs-guide abs-guide:latest

Replace image name and image tag by using sed which we can use it as tag name changes 

4. sed -i s,'\${IMAGE_NAME},abs-guide,g;s\${IMAGE_TAG},latest,g' infrastructure.yaml

To create or deploy above application we need kubernetes cluster. Assuming we have kubernetes cluster we need to deploy abs-guide by using below command. Login using credentails for kubernetes , then assign context which cluster and use below command to deploy 

5. kubectl apply -f infrastructure.yaml --context = k8sCluster-cc-dat1 -n=sample
6. kubectl get pods -n sample

Since it is frontend file we need ingress yaml file. For ingress yaml file we need domain name , ssl certificate then we can able to create ingress yaml. once we configure it we can able to access above application below is sample ingress yaml file 

7.  https://gist.githubusercontent.com/matthewpalmer/d1147ed1066e9219e8c346f4e0dd0488/raw/05b8917f31bd76d9d28fc249d0dfc71523787462/apple.yaml





