---
title: "Heroku to Private Cloud"
description: "A week ago, I was stuck on Heroku. Despite being a part of DigitalOcean Hatch, and having $100,000 in DO credits, I’d given up running my…"
date: "2020-05-02T22:47:52.265Z"
categories: []
published: false
---

A week ago, I was stuck on Heroku. Despite being a part of DigitalOcean Hatch, and having $100,000 in DO credits, I’d given up running my own cluster as something too difficult. Until I decided I’d had enough. We’re going to be:

1.  Creating a 5 node Kubernetes Cluster
2.  Installing Deis Workflow on the Cluster
3.  Creating an application on our Cluster

#### My Workflow (which will not be replicated)

I have a rigorous flow that I’ve been using for years:

1.  My application is hosted at Github/Gitlab
2.  `master` is always automatically deployed to production
3.    
    

#### Make a Kubernetes Cluster with Deis

You’re going to love me for this: go to stackshare.io and point and click

#### Creating and deploying an App

  

Registering With Deis

1.  Deis register
2.  Deis keys:add
3.  deis create
4.  git push deis master
5.  deis database

  

Exposing
