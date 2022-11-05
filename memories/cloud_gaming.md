```
id: 1f59e02d-7144-40d2-ac71-0d267289df4a
title: cloud gaming
links:
  - 9033e630-47fb-11ea-a7e6-976edeb0544d
  - 51d06c7e-3b71-11ea-aaea-37494cb0bb04
```

# cloud gaming

> How to Deploy a Windows Server EC2 Instance in AWS using Terraform
>
> In this story, we will learn how to deploy a Windows Server EC2 Instance (VM) in AWS using Terraform.
> [Blog entry][1]

> Deploying a Windows Server EC2 Instance in AWS using Terraform
> [Terraform/Github][2]

## Azure

> Setting Up A Cloud Gaming VM

> Like for many others, my first contact to computers was related to playing computer games. I still like to play computer games from time to time - but the purchase of a real gaming computer seems to be overkill for playing 10 to 20 hours a year.

> Using cloud technologies in day-to-day business, the obvious solution is to create a virtual machine (VM) hosted in the cloud. This VM can then be used as a remote desktop, which runs the games you would like to play. I had no worries related to RAM or CPU, but I was a bit sceptic with regard to latency. After some research I was convinced, that there is good chance that it will work and tried it out.

> This blog post is intended as documentation of the setup. Feel free to adopt it for your gaming needs. I will use Microsoft Azure as the public cloud provider. Basic knowledge about Microsoft Azure is necessary, because the explanation is mainly focussed on the pitfalls I came across.
> [Blog entry][4]

## Nice DCV

- owned by amazon

> NICE DCV

> Deliver high-performance remote desktop and application streaming

> NICE DCV is a high-performance remote display protocol that provides customers with a secure way to deliver remote desktops and application streaming from any cloud or data center to any device, over varying network conditions. With NICE DCV and Amazon EC2, customers can run graphics-intensive applications remotely on EC2 instances, and stream their user interface to simpler client machines, eliminating the need for expensive dedicated workstations. Customers across a broad range of HPC workloads use NICE DCV for their remote visualization requirements. The NICE DCV streaming protocol is also utilized by popular services, like Amazon Appstream 2.0, AWS Nimble Studio, and AWS RoboMaker.
> [AWS documentation][5]

## AWS Compute Blog

> Use Amazon EC2 for cost-efficient cloud gaming with pay-as-you-go pricing

> Since AWS launched in 2006, cloud computing disrupted traditional IT operations by providing a more cost-efficient, scalable, and secure alternative to owning hardware and data centers. Similarly, cloud gaming today enables gamers to play video games with pay-as-you go pricing. This removes the need of high upfront investments in gaming hardware. Cloud gaming platforms like Amazon Luna are an entryway, but customers are limited to the games available on the service. Furthermore, many customers also prefer to own their games, or they already have a sizable collection. For those use cases, vendor-neutral software like NICE DCV or Parsec are powerful solutions for streaming your games from anywhere.
> [Blog entry][6]

## Terraform

> Provision an AWS EC2 instance with a gpu to play games in the cloud. Uses terraform to create the required infrastructure and a user data script to install the applications on the instance. Once configured, games can be streamed from the instance with low-latency using Parsec.
>
> The scripts in this repository automate most of the manual operations needed to setup such an instance. The only exception is management of AMIs, which must be done through the AWS management console.
>
> Currently only compatible with g3 and g4 instance family. The script will still run on other instance types, but gpu driver will have to be installed manually.
> [Github][10] |
> [Github - gusse (fork)][11] |
> [Github - lachlanclulow (fork)][12] |
> [Github - MostlyVet (fork)][13] |
> [Github (fork)][14] |
> [Github (fork)][15]

## 

> PERFORMANCE COMPARISON OF NVIDIA DRIVERS AND GPU-BASED AWS INSTANCES
> Working with graphics and 3D applications it is always important to get the best performance for the end user. We have conducted a performance comparison of GPU-Based Instances and nVidia Drivers on AWS to understand optimal configurations leveraging the popular Unigine Heaven performance benchmark. 
> [Blog entry][17]

## Videos

- [NICE DCV on AWS Tutorial | Cloud Gaming (Youtube)][7]
- [Parsec vs Moonlight vs NICE DCV on AWS | Cloud Gaming (Youtube)][8]
- [Roll Your Own Cloud Gaming Server | Cloud Gaming (Youtube)][9]
- [Gaming in the Cloud: Using AWS to Stream PC games at 1440p 60fps!][16]

## snipets

Getting the price for spot instances.

```
aws --region=eu-central-1 ec2 describe-spot-price-history --instance-types g5.xlarge --start-time=$(date +%s) --product-descriptions="Windows" --query 'SpotPriceHistory[*].{az:AvailabilityZone, price:SpotPrice}'
```

[1]: https://gmusumeci.medium.com/how-to-deploy-a-windows-server-ec2-instance-in-aws-using-terraform-dd86a5dbf731
[2]: https://github.com/KopiCloud/terraform-aws-windows-ec2-instance
[3]: https://lg.io/2015/07/05/revised-and-much-faster-run-your-own-highend-cloud-gaming-service-on-ec2.html
[4]: https://www.baitando.com/it/2021/01/01/setting-up-a-cloud-gaming-vm
[5]: https://aws.amazon.com/hpc/dcv/
[6]: https://aws.amazon.com/blogs/compute/use-amazon-ec2-for-cost-efficient-cloud-gaming-with-pay-as-you-go-pricing/
[7]: https://www.youtube.com/watch?v=h938uZ55Rtk
[8]: https://www.youtube.com/watch?v=xUwyBiMZbws
[9]: https://www.youtube.com/watch?v=gE20QLY6gAI
[10]: https://github.com/badjware/aws-cloud-gaming
<!-- slightly different forks -->
[11]: https://github.com/gusse/aws-cloud-gaming
[12]: https://github.com/lachlanclulow/aws-cloud-gaming
[13]: https://github.com/MostlyVet/aws-cloud-gaming
[14]: https://github.com/pyranja/aws-cloud-gaming
[15]: https://github.com/brainstorm/aws-windows
[16]: https://www.youtube.com/watch?v=aJ8MO6Sfvpo
[17]: https://www.ni-sp.com/performance-comparison-of-gpu-based-instances-and-nvidia-drivers-on-aws/
