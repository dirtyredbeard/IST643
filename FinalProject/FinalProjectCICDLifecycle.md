# Data Center Design Group Project <!-- omit in toc -->

> Estimated Completion Time: 40-60 Hours
> 
> Assignment Value: TBD
> 
> Due Date: 
> - In-class project check-up: Weekly
> - Final Presentation of Work: Last class of the semester

## Learning Objectives <!-- omit in toc -->

The objective of this project is for you to construct a scalabe and monitored development and deployment pipeline leveraging Git source code management (GitLab), OpenFaaS, and a Rancher managed kubernetes environment.

## The Assignment

The developer has written an application and their code has been pushed to GitLab. Along with the application code are a series of tests --to verify the application code meets project specifications and guidelines.

As the operations team your task is to host the application in the most scalable, integrated, and stable means possible. The project requirements are as follows:

- When the developer updates their codebase in GitLab, automatically update the live application.
- Programatically ensure all processes are verified as functional or successfully deployed.
- Log all transactions in the application and hosting environment --platforms of your choosing.
- Create a dashboard, and alerts, for any critical metrics of the application or hosting environment.
- Monitor for metrics indicative of a resource constraint --scale the application to mitigate the constraint.
- Estimate the cost of moving this pipeline into the cloud hosting solutions of your choosing.

## Required Deliverable's

- Executive Summary
  - Outline your environment
  - Estimated cost to run this environment in the cloud
    - Reference your application metrics to determine resource requirements
  - Lessons learned & how would you improve your project
  - References\Citations
