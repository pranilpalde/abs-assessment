# abs-assessment
#Below are step by step guide 

tar -xvf abs-guide.tar

#Above command untar file 

#By using Dockerfile, we can create docker image

docker build -t abs-guide .

#create docker tag 

docker tag abs-guide abs-guide:latest

replace image name and image tag by using sed

sed -i s,'\${IMAGE_NAME},${IMAGE_NAME},g;s\${IMAGE_TAG},${IMAGE_TAG},g' infrastructure.yaml

To create or deploy above application we need kubernetes cluster.

Assuming we have kubernetes cluster we need to deploy abs-guide by using below command

login using credentails for kubernetes , then assign context which cluster and use below command to deploy 

kubectl apply -f infrastructure.yaml --context = k8sCluster-cc-dat1 (use particular context)

Since it is frontend file we need ingress yaml file 

for ingress yaml file we need domain name , ssl certificate then we can able to create ingress yaml. once we configure it we can able to access above application below is sample ingress yaml file 

https://gist.githubusercontent.com/matthewpalmer/d1147ed1066e9219e8c346f4e0dd0488/raw/05b8917f31bd76d9d28fc249d0dfc71523787462/apple.yaml





