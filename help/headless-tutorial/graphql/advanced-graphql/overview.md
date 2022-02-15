---
title: Advanced Concepts of AEM Headless - GraphQL
description: An end-to-end tutorial illustrating advanced concepts of Adobe Experience Manager (AEM) GraphQL APIs.
version: Cloud Service
feature: Content Fragments, GraphQL API
topic: Headless, Content Management
role: Developer
level: Intermediate
exl-id: daae6145-5267-4958-9abe-f6b7f469f803
---
# Advanced Concepts of AEM Headless

This end-to-end tutorial continues the [basic tutorial](../multi-step/overview.md) that covered the fundamentals of Adobe Experience Manager (AEM) Headless and GraphQL. The advanced tutorial illustrates in-depth aspects of working with Content Fragment Models, Content Fragments, and the AEM GraphQL API, including using AEM GraphQL in a client application.

## Prerequisites

Complete the [quick setup for AEM as a Cloud Service](../quick-setup/cloud-service.md) to configure your environment.

It is highly recommended that you complete the previous [basic tutorial](../multi-step/overview.md) and [video series](../video-series/modeling-basics.md) tutorials before proceeding with this advanced tutorial. Although you can complete the tutorial using a local AEM environment, this tutorial only covers the workflow for AEM as a Cloud Service.

## Objectives

This tutorial covers the following topics:

* Create Content Fragment Models using validation rules and more advanced data types such as Tab Placeholders, nested fragment references, JSON objects, and Date & Time data types.
* Author Content Fragments while working with nested content and fragment references, and configure folder policies for content fragment authoring governance.
* Explore AEM GraphQL API capabilities using GraphQL queries with variables and directives.
* Persist GraphQL queries with parameters in AEM and learn how to use cache-control parameters with persisted queries.
* Integrate requests for persisted queries into the sample WKND GraphQL React app using the AEM Headless JavaScript SDK.

## Advanced concepts of AEM Headless overview

The following video provides a high-level overview of the concepts that are covered in this tutorial. The tutorial includes defining Content Fragment Models with more advanced data types, nesting Content Fragments, and persisting GraphQL queries in AEM.

>[!VIDEO](https://video.tv.adobe.com/v/340035/?quality=12&learn=on)

## Project setup

The WKND Site project has all necessary configurations, so you can start the tutorial right after you complete the [quick setup](../quick-setup/cloud-service.md). This section only highlights some important steps that you can use when creating your own AEM Headless project.

### Create a configuration

The first step to starting any new project in AEM is creating its configuration, as a workspace and to create GraphQL API endpoints. To view or create a configuration, navigate to **Tools** > **General** > **Configuration Browser**.

![Navigate to Configuration Browser](assets/overview/create-configuration.png)

Observe that the WKND Site configuration has already been created for the tutorial. To create a configuration for your own project, select **Create** in the top-right corner and complete the form in the Create Configuration modal that appears.

### Create GraphQL API endpoints

Next, you must configure API endpoints to send GraphQL queries to. To review existing endpoints or create one, navigate to **Tools** > **Assets** > **GraphQL**.

![Configure endpoints](assets/overview/endpoints.png)

Observe that the global and WKND endpoints have already been created. To create an endpoint for your project, select **Create** in the top-right corner and follow the workflow.

>[!NOTE]
>
> After saving the endpoint, you will see a modal about visiting the Security Console, which allows you to adjust security settings if you wish to configure access to the endpoint. Security permissions themselves are outside of the scope of this tutorial, however. For more information, refer to the [AEM documentation](https://experienceleague.adobe.com/docs/experience-manager-64/administering/security/security.html).

### Create a language root folder for your project

A language root folder is a folder with an ISO language code as its name such as EN or FR. The AEM translation management system uses these folders to define the primary language of your content and languages for content translation.

Go to **Navigation** > **Assets** > **Files**.

![Navigate to Files](assets/overview/files.png)

Navigate into the **WKND Site** folder. Observe the folder with the title "English" and the name "EN". This folder is the language root folder for the WKND Site project.

![English folder](assets/overview/english.png)

For your own project, create a language root folder inside your configuration. See the section on [creating folders](/help/headless-tutorial/graphql/advanced-graphql/author-content-fragments.md#create-folders) for more details.

### Assign a configuration to the nested folder

Finally, you must assign your project's configuration to the language root folder. This assignment enables the creation of Content Fragments based on Content Fragment Models defined in your project's configuration.

To assign the language root folder to the configuration, select the folder, then select **Properties** in the top navigation bar.

![Select Properties](assets/overview/properties.png)

Next, navigate to the **Cloud Services** tab and select the folder icon in the **Cloud Configuration** field.

![Cloud Configuration](assets/overview/cloud-conf.png)

In the modal that appears, select your previously created configuration to assign the language root folder to it.

### Best practices

The following are best practices when creating your own project in AEM:

* The folder hierarchy should be modeled with localization and translation in mind. In other words, language folders should be nested within configuration folders, which allows for easy translation of content within those configuration folders.
* The folder hierarchy should be kept flat and straightforward. Avoid moving or renaming folders and fragments later on, especially after publishing for live usage, as it changes paths which can affect fragment references and GraphQL queries.

## Starter and Solution Packages

Two AEM **packages** are available and can be installed via [Package Manager](/help/headless-tutorial/graphql/advanced-graphql/author-content-fragments.md#sample-content)

* [Advanced-GraphQL-Tutorial-Starter-Package-1.0.zip](/help/headless-tutorial/graphql/advanced-graphql/assets/tutorial-files/Advanced-GraphQL-Tutorial-Starter-Package-1.0.zip) is used later in the tutorial and contains sample images and folders.
* [Advanced-GraphQL-Tutorial-Solution-Package-1.1.zip](/help/headless-tutorial/graphql/advanced-graphql/assets/tutorial-files/Advanced-GraphQL-Tutorial-Solution-Package-1.1.zip) contains the finished solution for Chapters 1-4 including new Content Fragment Models, Content Fragments, and Persisted GraphQL queries. Useful for those who want to skip right into the [Client Application Integration](/help/headless-tutorial/graphql/advanced-graphql/client-application-integration.md) chapter.

Two React JS projects are available to experiment with queries [from a headless client application](/help/headless-tutorial/graphql/advanced-graphql/client-application-integration.md).

* [aem-guides-wknd-headless-start-tutorial.zip](/help/headless-tutorial/graphql/advanced-graphql/assets/tutorial-files/aem-guides-wknd-headless-start-tutorial.zip) - starter client application that is completed in [Chapter 5 - Client Application Integration](/help/headless-tutorial/graphql/advanced-graphql/client-application-integration.md).
* [aem-guides-wknd-headless-solution-tutorial.zip](/help/headless-tutorial/graphql/advanced-graphql/assets/tutorial-files/aem-guides-wknd-headless-solution-tutorial.zip) - finished client application that uses **persisted** queries.


## Getting started

To get started with this advanced tutorial, follow these steps:

1. Set up a development environment using [AEM as a Cloud Service](../quick-setup/cloud-service.md).
1. Start the tutorial chapter on [creating Content Fragment Models](/help/headless-tutorial/graphql/advanced-graphql/create-content-fragment-models.md).