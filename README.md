---
page_type: sample
description: This sample demonstrates how to use the Microsoft Graph Java SDK to access data in Office 365 from native mobile Android applications.
products:
- ms-graph
- microsoft-graph-calendar-api
- office-exchange-online
languages:
- java
---

# Microsoft Graph sample Android app

This sample demonstrates how to use the Microsoft Graph Java SDK to access data in Office 365 from native mobile Android applications.

## Prerequisites

Before you start this tutorial, you should have [Android Studio](https://developer.android.com/studio/) installed on your development machine.

You should also have either a personal Microsoft account with a mailbox on Outlook.com, or a Microsoft work or school account. If you don't have a Microsoft account, there are a couple of options to get a free account:

- You can [sign up for a new personal Microsoft account](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1).
- You can [sign up for the Microsoft 365 Developer Program](https://developer.microsoft.com/microsoft-365/dev-program) to get a free Microsoft 365 subscription.

## Install dependencies

Before moving on, install some additional dependencies that you will use later.

- `com.google.android.material:material` to make the [navigation view](https://material.io/develop/android/components/navigation-view/) available to the app.
- [Microsoft Authentication Library (MSAL) for Android](https://github.com/AzureAD/microsoft-authentication-library-for-android) to handle Azure AD authentication and token management.
- [Microsoft Graph SDK for Java](https://github.com/microsoftgraph/msgraph-sdk-java) for making calls to the Microsoft Graph.

1. Expand **Gradle Scripts**, then open **build.gradle (Module: Graph_Tutorial.app)**.

1. Add the following lines inside the `dependencies` value.

    :::code language="gradle" source="../demo/GraphTutorial/app/build.gradle" id="DependenciesSnippet":::

1. Add a `packagingOptions` value inside the `android` value in **build.gradle (Module: Graph_Tutorial.app)**.

    ```Gradle
    packagingOptions {
        pickFirst 'META-INF/*'
    }
    ```

1. Add the Azure Maven repository for the MicrosoftDeviceSDK library, a dependency of MSAL. Open **build.gradle (Project: Graph_Tutorial)**. Add the following to the `repositories` value inside the `allprojects` value.

    ```Gradle
    maven {
        url 'https://pkgs.dev.azure.com/MicrosoftDeviceSDK/DuoSDK-Public/_packaging/Duo-SDK-Feed/maven/v1'
    }
    ```

1. Save your changes. On the **File** menu, select **Sync Project with Gradle Files**.

## Code of conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Disclaimer

**THIS CODE IS PROVIDED _AS IS_ WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**
