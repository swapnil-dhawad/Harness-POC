# Harness

Harness is the industry’s first Software Delivery Platform to use AI to simplify your DevOps processes - CI, CD & GitOps, Feature Flags, Cloud Costs, and much more.

## Continuous Delivery & GitOps

Harness CD & GitOps enables deployment of application and infrastructure changes in a safe and sustainable way. Your CD pipeline or GitOps workflow should automate all of the steps necessary to get your changes into production.

## Prerequisite

Harness Login [link](https://www.harness.io/)

GitHub Repo [link](https://github.com)


### Let's get started

1. The repo structure used for the pipeline looks like below.

![image](https://user-images.githubusercontent.com/56785623/235187222-9bf4f17b-2329-43cf-ba65-b5c3743a91fe.png)

2. helm-charts folder has standard structure defined. 

![image](https://user-images.githubusercontent.com/56785623/235188153-74a597a2-928a-45d3-9ef6-60d3772090ca.png)

3.  Values.yml is further referred in Harness pipeline to deploy the artifact in the given name-space.

![image](https://user-images.githubusercontent.com/56785623/235188636-90647adf-c9cf-4696-a67b-331cce2398a8.png)

4. Once login to Harness, below is the basic overview of Dashboard.

![image](https://user-images.githubusercontent.com/56785623/235199554-ef0e8eb9-5dfb-4fb2-b509-6fcf624278ae.png)

5. Few important terms in Harness while buidling the pipeline. 
 
    a. Project   -  It's is a plyground where all the pipline related worked grouped together. 

    b. Pipelines -  All the pipelines creared in the particular project visible inside this tab.

    c. Services  -  A Harness Service is what you're deploying. It contains Manifest      configuration,artifacts configuuration.etc.

    d. Connector -  You use Connectors to connect Harness to your tools, such as Kubernetes clusters, code and artifact repositories, and cloud platforms.

    e. Delegates -  Harness Delegate is a service you run in your local network or VPC to connect your artifacts, infrastructure, collaboration, verification and other providers, with Harness Manager

    f. Enviorment - A Harness Environment represents where you are deploying your Service. 


![image](https://user-images.githubusercontent.com/56785623/235205322-d9185638-d746-486a-9cbf-b42a809e60f7.png)




