---
layout: post
title: A love letter to infrastructure-as-code
date: '2020-07-13 17:16:27 -0500'
categories: jekyll update
published: false
---

While tweaking AWS' CDK, a fellow intern asked me, "Why can't we just provision our resources in the AWS console?"

(For those who are unfamiliar, [CDK](https://aws.amazon.com/cdk/), or Cloud Development Kit, is a tool/library that allows developers to write code that compiles into CloudFormation templates using their language of choice. Supported languages include Javascript/Typescript, Python, Java, and C#.)

Personally, the thought has never crossed my mind. IaC is versioned, declarative, and constant: A successful deployment _now_ should (hypothetically) be a successful deployment in X amound of time. Every single modification made to the stack can be tracked and stored, while the deployment itself is both automated and consistent. Having begun my CS experience setting things up on DigitalOcean droplets, I can appreciate simplicity and elegance of being able to accurately and definitely state the shape of the infrastructure using a DSL, code, whatever. 

While my coworker might complain about the extra time needed for us to become accustomed to using the IaC tool (CDK in our case), I think the upsides far outweigh the initial learning curve. For example: