---
layout: post
title: A love letter to infrastructure-as-code
date: '2020-07-13 17:16:27 -0500'
categories: jekyll update
published: true
---

While tweaking AWS' CDK, a fellow intern asked me, "Why can't we just provision our resources in the AWS console?"

(For those who are unfamiliar, [CDK](https://aws.amazon.com/cdk/), or Cloud Development Kit, is a tool/library that allows developers to write code that compiles into CloudFormation templates using their language of choice. Supported languages include Javascript/Typescript, Python, Java, and C#.)

Personally, the thought has never crossed my mind. Besides being a cornerstone of effective DevOps, IaC is versioned, declarative, and constant: A successful deployment _now_ should (hypothetically) be a successful deployment in X amound of time. Every single modification made to the stack can be tracked and stored, while the deployment itself is both automated and consistent. Having begun my CS experience setting things up on DigitalOcean droplets, I can appreciate simplicity and elegance of being able to accurately and definitely state the shape of the infrastructure using a DSL, code, whatever. 

```
# Think of infrastructure-as-code as being a magical grocery list,
# compared to memorizing everything

1 Medium Soda
2 Banana Milkshakes (1 without whipped cream)
17 Pineapple Pizzas (3 with extra pineapple)
4 Bottles of Root Beer (Bring more if needed)
7 Bags of Doritos
2 Packs of Cups
```

While my coworker might complain about the extra time needed for us to become accustomed to using the IaC tool (CDK in our case), I think the upsides far outweigh the initial learning curve.

### Developers can become more involved on the operations side.
After talking with some of the full-time engineers at my internship (as well as other software developers), I've come to understand that there was a dark time where development was hindered by blockers such as:
- Waiting on the Operations team
- Urgently searching through system configurations and settings
- Difference in _development_ and _deployment_ environments

Infrastructure-as-code works to address all of these old issues. Having __versioned__ and __declarative__ infrastructure enables developers to become more involved in operations, and allows Operations to focus on more mission-critical responsibilities, expediting and hardening the development lifecycle (AKA __DevOps__). Configurations are no longer manually modified (requiring a team of expert SysAdmins), but are now versioned and regulated, so that for every change to a development/sandbox/nonproduction environment, a change can be made in the production environment. Furthermore, since resources and configurations are all declarative, versioned, and accessible, there won't be unexpected differences between production and development environments.

The title is true: this post _is_ a love letter to infrastructure-as-code. Infrastructure-as-code empowers great developers to do just-as-great things. But equally so, it is a love letter to DevOps, Continuous Delivery, and organized software development practices, without which we would've never been able to see the beauty and effectiveness of infrastructure-as-code.
