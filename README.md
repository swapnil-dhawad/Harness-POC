
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
 
    a. Project   -  It's is a plyground where all the pipline related work group together. 

    b. Pipelines -  All the pipelines creared in the particular project visible inside this tab.

    c. Services  -  A Harness Service is what you're deploying. It contains Manifest      configuration,artifacts configuuration.etc.

    d. Connector -  You use Connectors to connect Harness to your tools, such as Kubernetes clusters, code and artifact repositories, and cloud platforms.

    e. Delegates -  Harness Delegate is a service you run in your local network or VPC to connect your artifacts, infrastructure, collaboration, verification and other providers, with Harness Manager

    f. Enviorment - A Harness Environment represents where you are deploying your Service. 


     ![image](https://user-images.githubusercontent.com/56785623/235205322-d9185638-d746-486a-9cbf-b42a809e60f7.png)


## Pipeline Overview
![image](https://user-images.githubusercontent.com/56785623/235207288-386eb5b0-2063-4c0e-8afb-27284adfe431.png)

Above pipeline depicts complete overview of e2e deployment of an artifact on Primary & Secondary GKE cluster using Helm charts. It also proceed with Istio deployment on primary and Secondary cluster.

Let's take an example of Deploy to Primary Stage.

    1. Select a Stage as type 'Deployment' from Add stage widget. 
    2. In Overview section select Deployment type as Kubernetes. 
    3. Next we have to configure service. As below; 
       Deployment Type as Kubernetes and manifests has been added from github repo as Values.yml containing "Namespace" details where deployment is planned on the cluster. 
       Pipleine trigger action is release tag as shown in second screenshot.
       
![image](https://user-images.githubusercontent.com/56785623/235631456-34b00615-82e6-436f-8301-85ee4371872e.png)

![image](https://user-images.githubusercontent.com/56785623/235633175-79d9fb99-89d2-436a-9789-50932935eda5.png)
   
    4. Next is setting up the Enviorment, First is to select the Enviorment from avaialable options like Prodcution, PreProduction or Test etc. 
       Second stage is to select the infra like EC2 server,Google cloud function, lambda etc. 
       
![image](https://user-images.githubusercontent.com/56785623/235636320-54b51174-ef1a-47bc-a671-8fdce24b17de.png)

     5.Setting up the Values.yml as a hanress manifests in case Values.yml not provided with Helm charts.
         Select Enviorment type as PreProduction then in Enviorment overrides second select Add new manifest to override and Select an Option from hanress Namespace. 
![image](https://user-images.githubusercontent.com/56785623/235644711-32f0310e-3726-4485-a795-f583a428f21c.png)

     6. Next is Execution stage which provides deiffernt options of deployment like Canary,Blue Green,Rolling Deployment. In below example Canary Deployment has been seelected, it also asks for number of instances for deployment. 

![image](https://user-images.githubusercontent.com/56785623/235646789-3a1b1768-f037-43e1-833b-0e43930233d6.png)

![image](https://user-images.githubusercontent.com/56785623/235646995-1dbc1747-ec35-4f27-af16-0963bd012f0f.png)
     
     7. Advanced Section defines various options in case deployment failure Strategy such as rollback,delegates,conditional execution. 

![image](https://user-images.githubusercontent.com/56785623/235648096-e2f15dd8-9bd4-4683-b7d0-0e27228e3a0a.png)

The pipeline can be triggered using webhook option, manual run or approval based execution. Pipeline execution logs are also avaialable to monitor the execution of pipeline.


                        
