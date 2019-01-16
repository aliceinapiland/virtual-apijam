# API Consumption : Developers and Apps 

*Duration : 15 mins*

*Persona : Developer*

# Use case

As an App Developer you would like to learn about APIs exposed by the API Team using API Documentation. Register into an API Program to get access to the APIs exposed by the API Team.

# How can Apigee Edge help?

Apigee Edge has out of the box lightweight Developer Portal which allows API Team to publish API Documentation & as an App Developer you can self register onto API Platform. Once logged in, you can create Apps to get API Keys using which you can access APIs securely.

In this lab, we will see how to register as an App Developer, navigate through API documentation, create app in the Developer Portal to access API keys, test the APIs using the keys we got from Developer Portal.

# Pre-requisites

*API Security* and *API Publishing* lab exercises. 

# Instructions

* Go to [https://apigee.com/edge](https://apigee.com/edge) and log in. This is the Edge management UI. 

* Select **Publish → Portals** in the side navigation menu.

![image alt text](./media/image_0.png)

* Click on **{your_initials}_{api_proxy_name}_portal** that you have created in earlier lab exercise.	

![image alt text](./media/image_1.png)

* Click on **Live Portal** link to access Developer Portal to start interacting as Developer persona.

![image alt text](./media/image_2.png)

* In this lab, we will play the role of an App Developer who would like to access the APIs and API Documentation.

* Let’s register as an App Developer by clicking on the **Sign In** link on the home page.

![image alt text](./media/image_3.png)

* In the **Sign In** page, click on **Create account**

![image alt text](./media/image_4.png)

* Fill in the details and then click on **Create Account**

![image alt text](./media/image_5.png)

* As the message indicates, check your inbox to view the confirmation email.

![image alt text](./media/image_6.png)

* Click on the verification link in your confirmation email to verify your account. You will be redirected back to the developer portal.

![image alt text](./media/image_7.png)

* Once again, click on the **Sign In** button, then fill in your Developer Portal credentials to log into the portal.

![image alt text](./media/image_8.png)

* Note that the **Sign In** button has been replaced with your email, indicating a successful login.

![image alt text](./media/image_9.png)

* Click on the **APIs** link in the top menu to view the list of API Products associated to this portal.

![image alt text](./media/image_10.png)

* Click on **{your_initials}_{api_name}_product** to view the API Product documentation

![image alt text](./media/image_11.png)

* Go through API Documentation to view the list of APIs and visualize the API Request and Response.

![image alt text](./media/image_12.png)

* Let’s **create** a Developer App.

Typically, developers who want to consume APIs go to developer portal and register to use them. When registering, the developer gets to select which of API products he or she wishes to use. For example, some products may be offered for free, while others require payment depending on a service plan. Upon completion, this registration step produces an Edge entity called a **developer app**. A developer app includes the products the developer selected and a set of API keys that the developer will be required to use to access the APIs that are associated with those products. 

* To Create an App, Click on your **Email Address** & then **My Apps** in the top menu bar.

![image alt text](./media/image_13.png)

* Click on **+ New App** to create an App.

![image alt text](./media/image_14.png)

* Fill in the App's Name, Description, and click on the toggle to enable access to the Employee product.  Click on the **Create** button to create a new App.

![image alt text](./media/image_15.png)

* After the App has been created, the App page will now have a new section containing the API Key. Copy the key, which can be used to make secured API calls.

![image alt text](./media/image_16.png)

* From the main Apigee UI (not the Developer Portal), go back to the Employee API you've already created and click the **Trace** tab in the upper right.

* Click **Start Trace Session** to begin a trace session.

* Click **Send** to send a request (Do not add the API Key to they query string yet).

   You should see a 401 (unauthorized) response for your API Call because the API Proxy was expecting an API Key as a query      parameter.  See the trace session below

* Now add the query parameter ```?apikey={your_api_key}``` to the URL in the trace tool and try again.  (Replace ```{your_api_key}``` with the API Key you just created in this Lab and resend the request.

   You should see a 2xx response code and the Trace for that request should show that the Verify API Key policy is now            passing.

![image alt text](./media/image_19.png)

# Lab Video

If you like to learn by watching, here is a short video on consuming APIs using Apigee Developer Portal [https://youtu.be/nCJwlVF6waw](https://youtu.be/nCJwlVF6waw)

# Earn Extra-points

Now that you have Registered in Developer Portal, Created App, Read API Documentation, Explore more by making an API call using keys generated above.

# Quiz

1. When you create an App, What are the different keys associated with it ?

2. Is it possible to create different Apps with same App Name ?

3. Is it possible to associate multiple API Products with same App ?

# Summary

That completes this hands-on lesson. In this simple lab you learned how to self register as a Developer to access APIs, Create Apps, Access API Keys, and Navigate through API Documentation.

# References

* Useful Apigee documentation links on Apigee Developer Portal.

    * Apigee Developer Portal , [https://docs-new.apigee.com/portal](https://docs-new.apigee.com/portal)

# Rate this lab

How did you like this lab? Rate [here](https://goo.gl/forms/H4qE5nLy36yWjj642).

Now to go [Lab-5](../Lab%205%20Traffic%20Management%20-%20Rate%20Limit%20APIs/README.md)


