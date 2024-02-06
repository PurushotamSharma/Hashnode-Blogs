---
title: "🚀 Unleashing AWS EKS Magic: Day 21 of 30 Days of AWS Series ✨"
seoTitle: "Kubernetes, EKS, AWS, EKS Demo"
datePublished: Tue Feb 06 2024 11:57:44 GMT+0000 (Coordinated Universal Time)
cuid: clsab3rie000409jx4npa39d3
slug: unleashing-aws-eks-magic-day-21-of-30-days-of-aws-series
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707220479327/7d0f3e93-9132-4c84-baf9-bf90930c64a0.png
tags: cloud, kubernetes, devops, eks, trainwithshubham

---

## Introduction:

Greetings, cloud enthusiasts! We've reached the 21st day of our exhilarating 30 Days of AWS Series, and today's adventure takes us deep into the realm of container orchestration with the one and only Amazon Elastic Kubernetes Service (EKS). 🌐

Picture this: a world where deploying, managing, and scaling containerized applications becomes a breeze. That's the promise of AWS EKS, and we're about to unravel its secrets. 🕵️‍♂️ But hey, we're not just talkin' theory here. Get ready for a hands-on experience as we guide you through a live demo, showcasing the sheer awesomeness of deploying a containerized application with AWS EKS. 🛠️💻

It's not just a blog; it's a journey into the future of cloud orchestration, filled with emojis, excitement, and the power of AWS services. Buckle up, because AWS EKS is about to make your container dreams come true. Let the container adventure begin! 🚢🔍 #AWSAdventures #ContainerMagic

## What is EKS🤷‍♂️?

Amazon Elastic Kubernetes Service (EKS) is a managed Kubernetes service provided by Amazon Web Services (AWS). Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. AWS EKS takes the complexity out of running Kubernetes by handling the management tasks and allowing users to focus on building and deploying applications.

## Key features of AWS EKS include:

1. **Managed Control Plane:** EKS provides a fully managed Kubernetes control plane, eliminating the need for users to manage and maintain it themselves. AWS takes care of upgrades, patches, and the overall health of the control plane.
    
2. **Serverless Kubernetes:** With EKS, you only pay for the compute resources you use for your worker nodes, making it a cost-effective solution. The control plane's cost is included in the AWS management fee.
    
3. **High Availability:** EKS is designed for high availability by distributing control plane components across multiple Availability Zones. This ensures that your Kubernetes cluster remains resilient to failures.
    
4. **Security:** EKS integrates with AWS Identity and Access Management (IAM) for authentication and authorization, providing a secure way to control access to your Kubernetes clusters.
    
5. **Compatibility:** EKS is compatible with standard Kubernetes tooling and APIs, allowing users to leverage existing knowledge and tools within the Kubernetes ecosystem.
    
6. **Ecosystem Integrations:** AWS EKS seamlessly integrates with other AWS services, enabling users to incorporate services like Amazon RDS, Amazon S3, and AWS Identity and Access Management into their containerized applications.
    

Using AWS EKS, developers and operators can streamline the deployment and management of containerized applications, benefit from the scalability of Kubernetes, and leverage the reliability and security features provided by AWS.

## Pros:

**Managed Control Plane:** EKS takes care of managing the Kubernetes control plane components, such as the API server, controller manager, etcd. AWS handles upgrades, and patches, and ensures high availability of the control plane.

**Automated Updates:** EKS automatically updates the Kubernetes version, eliminating the need for manual intervention and ensuring that the cluster stays up-to-date with the latest features and security patches.

**Scalability:** EKS can automatically scale the Kubernetes control plane based on demand, ensuring the cluster remains responsive as the workload increases.

**AWS Integration:** EKS seamlessly integrates with various AWS services, such as AWS IAM for authentication and authorization, Amazon VPC for networking, and AWS Load Balancers for service exposure.

**Security and Compliance:** EKS is designed to meet various security standards and compliance requirements, providing a secure and compliant environment for running containerized workloads.

**Monitoring and Logging:** EKS integrates with AWS CloudWatch for monitoring cluster health and performance metrics, making it easier to track and troubleshoot issues.

**Ecosystem and Community:** Being a managed service, EKS benefits from continuous improvement, support, and contributions from the broader Kubernetes community.

## Cons:

**Cost:** EKS is a managed service, and this convenience comes at a cost. Running an EKS cluster may be more expensive compared to self-managed Kubernetes, especially for large-scale deployments.

**Less Control:** While EKS provides a great deal of automation, it also means that you have less control over the underlying infrastructure and some Kubernetes configurations.

## Self-Managed Kubernetes on EC2 Instances Pros:

**Cost-Effective:** Self-managed Kubernetes allows you to take advantage of EC2 spot instances and reserved instances, potentially reducing the overall cost of running Kubernetes clusters.

**Flexibility:** With self-managed Kubernetes, you have full control over the cluster's configuration and infrastructure, enabling customization and optimization for specific use cases.

**EKS-Compatible:** Self-managed Kubernetes on AWS can still leverage various AWS services and features, enabling integration with existing AWS resources.

**Experimental Features:** Self-managed Kubernetes allows you to experiment with the latest Kubernetes features and versions before they are officially supported by EKS.

## Cons:

**Complexity:** Setting up and managing a self-managed Kubernetes cluster can be complex and time-consuming, especially for those new to Kubernetes or AWS.

**Maintenance Overhead:** Self-managed clusters require manual management of Kubernetes control plane updates, patches, and high availability.

**Scaling Challenges:** Scaling the control plane of a self-managed cluster can be challenging, and it requires careful planning to ensure high availability during scaling events.

**Security and Compliance:** Self-managed clusters may require additional effort to implement best practices for security and compliance compared to EKS, which comes with some built-in security features.

**Lack of Automation:** Self-managed Kubernetes requires more manual intervention and scripting for certain operations, which can increase the risk of human error.

## **Setting up Tools for AWS and EKS** ⚙️

* ### **Create IAM Users:**
    

1. Navigate to IAM in the AWS Management Console.
    
2. Click "Users," then "Add user."
    
3. Enter a username, choose access type, and set permissions via groups or policies.
    
4. Optionally, configure permissions boundary, tags, and enable MFA.
    

* ### **Access Keys (for Programmatic Access):**
    

1. If choosing "Programmatic access," secure the Access Key ID and Secret Access Key.
    
2. Configuring the AWS CLI and kubectl ⚙️
    

* ### **Installing the AWS CLI:**
    

1. Download and install AWS CLI on your machine ([OS-specific instructions here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)).
    

* ### **Configuring AWS CLI Credentials:**
    

1. Open terminal/cmd and run `aws configure`.
    
2. Enter the IAM user's access key ID, secret access key, default region, and output format.
    

* ### **Installing kubectl:**
    

1. Install kubectl on your machine [(installation guide here).](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/#install-nonstandard-package-tools)
    

* ### Installing eksctl: [Click here](https://docs.aws.amazon.com/emr/latest/EMR-on-EKS-DevelopmentGuide/setting-up-eksctl.html)
    

Now we start creating or using the EKS service:

1. Now navigate to the EKS service using the AWS Management console.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707137996614/d2015f6a-45d8-417b-be41-3e6be73e2c79.png align="center")
    
    You can see the above image as an interface of your EKS service.
    
3. In this blog, we will be using the root account of AWS.
    
4. We will start with Creating the Cluster on EKS.
    
5. Here we will use the CLI to create the cluster.
    
    ```plaintext
    eksctl create cluster --name demo-cluster --region ap-south-1 --fargate
    ```
    
6. This is a command to create the cluster, Here we were creating one demo cluster in ap-south-1 using the Fargate service.
    
7. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707207829618/c99ed091-694d-4f2e-8e06-e68308203647.png align="center")
    
    Our Cluster is creating it takes a couple of minutes and here keep patience.
    
8. Here you all have a question about why we use Fargate service here because we did not want to create the everything like ec2 instance and their configuration like vpc subnet fargate to all these things automatically. that's why it is tasking time.
    
9. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707209981576/6685bbf4-b851-4e97-8b41-f9ed02e43214.png align="center")
    
    It takes almost 15 min to create.
    
10. Now our cluster is created. Let's see in the console.
    
11. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707210151634/bf8007a4-c4d0-4ceb-aa50-312b4ca2dc32.png align="center")
    
    Our Cluster is created successfully.
    
12. The main Pros of EKS are we find everything in one place, we do not want to run commands to see which pods are running and what resources are here and many more.
    
    1. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707210392068/b837b7b8-c1c8-4848-a48f-aa58062ac5e1.png align="center")
        
13. Now we will upgrade the kubeconfig file.
    
    ```plaintext
    aws eks update-kubeconfig --name demo-cluster --region ap-south-1
    ```
    
14. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707210902364/fecce085-3612-4f23-a53f-fa21ab501b8e.png align="center")
    
    Today we will deploy the [2048 application](https://play2048.co).
    
15. First, we will create the fargate profile. use this command to create a profile.
    
    ```plaintext
    eksctl create fargateprofile --cluster demo-cluster --region ap-south-1 --name alb-sample-app --namespace game-2048
    ```
    
16. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707211966987/48bb0205-ef2a-4fb2-a15a-08d45a9f0213.png align="center")
    
    Our Fargate profile is creating.
    
17. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707212200789/7e856cb8-cd66-49bb-b79a-c839c5ca201e.png align="center")
    
    Our Fargate profile has been successfully created. You can see this in AWS &gt;EKS&gt;Cluster&gt;Compute
    
18. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707212843783/48669233-fdeb-43ca-9ecb-9c969678279a.png align="center")
    
    Now we will deploy our application.
    
    ```plaintext
    kubectl apply -f https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/examples/2048/2048_full.yaml
    ```
    
19. By using this command we can deploy the application.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707213429037/b3fa83a3-15df-4999-b926-df8a3ce84192.png align="center")

1. Our Pods are running. Now we will see the service is running or not?
    
    ```plaintext
    kubectl get svc -n game-2048
    ```
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707213568991/df477c6c-a6b7-4c43-a824-d38e1568fec2.png align="center")
    
    Here we can see that only within the vpc have access to this application , but we want to access this application from outside the vpc so we use the ingress.
    
3. Let's Check the ingress.
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707213742346/45fbd671-0376-4918-b2f9-91da4d391401.png align="center")
    
    Our ingress service is created but the address is not defined, Does anyone know why?
    
5. Because we did not deploy the ingress controller yet, after deploying the ingress controller we can see the address to access the application.
    
6. Now what we will do we will create the ingress controller that ingress controller creates the load balancer using the ingress service after that we can access the application using the load balancer.
    
7. Before creating this we have to create the IAM OIDC Provider so our alb can access to the AWS resources.
    
    ```plaintext
    eksctl utils associate-iam-oidc-provider --cluster demo-cluster --region ap-south-1  --approve 
    ```
    
8. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707214945380/4d890ece-b6f3-4e0d-899f-f9d073b822db.png align="center")
    
    It will create the OIDC provider.
    
9. Now we will install the ALB controller that will create the ALB(Application Load balancer) for us, so now we will create the IAM role and policy to access the AWS resources by ALB controller.
    
10. Use this json file
    
    ```plaintext
    curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json
    ```
    
11. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707215224258/ae875817-e8f4-4929-bc6a-770e3b388f2b.png align="center")
    
    Now we created the IAM policy using the command.
    

```plaintext
aws iam create-policy --policy-name AWSLoadBalancerControllerIAMPolicy  --policy-document file://iam_policy.json
```

1. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707215432365/89c6a0db-8940-4d3b-a7ab-73a60e4c31c1.png align="center")
    
    The policy is created successfully. Now we will create the IAM role for that use this command
    

```plaintext
eksctl create iamserviceaccount --cluster=demo-cluster  --namespace=kube-system --name=aws-load-balancer-controller  --role-name AmazonEKSLoadBalancerControllerRole  --attach-policy-arn=arn:aws:iam::<add account id>:policy/AWSLoadBalancerControllerIAMPolicy --approve
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707216438977/55909f63-6d7c-44c4-b9f8-09432691be3d.png align="center")

1. Our IAM role is created successfully.
    
2. Now we will create the ALB for that we use the helm chart.
    
    ```plaintext
    helm repo add eks https://aws.github.io/eks-charts
    ```
    
3. After this, we will update the <mark>helm repo update eks</mark>
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707217715221/38176eda-af8c-437c-b5a5-08e3024cac5d.png align="center")
    
    After that, we will install the load balancer controller.
    

```plaintext
helm install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system  --set clusterName=demo-cluster  --set serviceAccount.create=false --set serviceAccount.name=aws-load-balancer-controller --set region=ap-south-1 --set vpcId=vpc-0503140d605d9199d 
```

1. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707218953516/3212bbbb-bba0-494a-88f7-224fa71d8da0.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707219048496/52f628e9-64b4-4ceb-a913-2b7660af8f36.png align="center")
    
    Our ALB has 2 replicas ready.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707219620033/0ba575b5-d2e6-41bc-b8c3-b96205829080.png align="center")
    
    Now we have an address for the application
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707219672916/c82c8c7e-02de-422b-9fab-a85f689cc368.png align="center")
    
    Our application is live and successfully deployed.
    

Congrats for deploying your first application on EKS.

If you want to learn this by video then here is the link:

[https://youtu.be/RRCrY12VY\_s?si=F0LBNBoNM8p8GuNZ](https://youtu.be/RRCrY12VY_s?si=F0LBNBoNM8p8GuNZ)

This demo is explained by [**abhishekveeramalla**](https://www.youtube.com/hashtag/abhishekveeramalla)

That's all for today, Stay tuned for day 22.

Happy Learning))

## Github Profile:

[https://github.com/PurushotamSharma](https://github.com/PurushotamSharma)

## Github Repo of 30 days of AWS:

[https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)