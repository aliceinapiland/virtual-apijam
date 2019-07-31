# API Design : Create a Reverse Proxy from OpenAPI Spec

*Duration : 10 mins* 

*Persona : API Team*

# Use case

You have a requirement to create a reverse proxy for taking HTTP requests from the Internet and forwarding them to an existing backend service. You have decided to follow a design first approach & build a reusable component, a specification which can be used to build API proxies, generate API documentation, and generate API test cases using OpenAPI Specification format. You would like to generate an Apigee API Proxy by using the OpenAPI Specification (Swagger) instead of building the API Proxy from scratch.

# How can Apigee Edge help?

Apigee Edge enables you to quickly expose backend services as APIs. You do this by creating an API proxy that provides a facade for the backend service that you want to expose. Apigee Edge out of the box supports the OpenAPI specification, allowing you to auto-generate API proxies. Apigee Edge also has an OpenAPI specification editor & store which you can use to maintain your OpenAPI specifications. 

The API proxy decouples your backend service implementation from the API that developers consume. This shields developers from future changes to your backend services. As you update backend services, developers, insulated from those changes, can continue to call the API uninterrupted.

In this lab, we will see how to create a reverse proxy that routes inbound requests to existing HTTP backend services using a readily available OpenAPI specification.

# Pre-requisites

Basic understanding of [OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification) (Swagger)

# Instructions

* Go to [https://apigee.com/edge](https://apigee.com/edge) and log in. This is the Edge management UI. 

* Select **Develop → API Proxies** in the side navigation menu

![image alt text](./media/image_0.png)

* Click **+Proxy** The Build a Proxy wizard is invoked. 
![image alt text](./media/image_6.png)

* Select **Reverse proxy**, Click on **Use OpenAPI** below reverse proxy option.

![image alt text](./media/image_7.png)

* You should see a popup with access to either use a previously imported Open API Spec, upload a new Spec or Import from a URL. Select the **Import from a URL** tab. Here, provide the following values:
  * Spec Name: Employee Backend

  * URL: [https://raw.githubusercontent.com/aliceinapiland/virtual-apijam/master/Resources/employee-openapi-spec.yaml](https://raw.githubusercontent.com/aliceinapiland/virtual-apijam/master/Resources/employee-openapi-spec.yaml)

* Click **Select.** 

![image alt text](./media/image_8.png)

* You can see the imported OpenAPI Spec URL below the Reverse Proxy option, Click **Next** to continue.

![image alt text](./media/image_9.png)

* Enter the proxy name, base path, and description. This is the first version of our Employees API, so we'll make it version 1. When you enter the proxy name, the proxy base path will automatically be populated, but you'll need to change the hyphen before the version to a forward slash. 

  * Proxy Name: employees-v1

  * Proxy Base Path: /employees/v1

  * Existing API: Observe the field value which is auto filled from OpenAPI Spec.

  * Description: Employees API v1

![image alt text](./media/image_10.png)

* Verify the values and click **Next**.

* You can select, de-select list of API Proxy Resources that are pre-filled from the OpenAPI Spec. Make sure all resources are selected and click on **Next**.

![image alt text](./media/image_11.png)

* Select **Pass through (none)** for the authorization in order to choose not to apply any security policy for the proxy. Click **Next**. 
![image alt text](./media/image_12.png)

* The next pane allows us to decide whether the proxy will be available over http (default), https (secure), or both. In this case, our API deals with employee data. This is generally sensitive information, so we will only allow access via https. If we allowed access via http, all traffic to and from the API would be in plaintext across the internet. Unless there is a specific requirement to expose a specific API via http, you should always only allow access via https. **Uncheck the default virtual host and click Next**.
![image alt text](./media/image_13.png)

* The proxy is certainly not ready to deploy to production yet! Ensure that only the **test** environment is selected and click **Build and Deploy**.
![image alt text](./media/image_14.png)

* You should see that the proxy has been generated, uploaded, and deployed to test. Once the API proxy is built and deployed, click the **employees-v1** link to view your proxy in the proxy editor.

![image alt text](./media/image_15.png)

* You should see the proxy **Overview** screen.
![image alt text](./media/image_16.png)

* *Congratulations!* ...You have now built a reverse proxy for an existing backend service.

* You can also import and edit Open API Specs within Apigee. Click on **Develop > Specs** from side navigation menu.

![image alt text](./media/image_5.png)

* Click **+Spec.** Click on **Import URL** to add a new spec from existing source.

![image alt text](./media/image_1.png)

* Enter the spec details.

  * File Name: Employee Backend

  * URL: [https://raw.githubusercontent.com/aliceinapiland/virtual-apijam/master/Resources/employee-openapi-spec.yaml](https://raw.githubusercontent.com/aliceinapiland/virtual-apijam/master/Resources/employee-openapi-spec.yaml)

![image alt text](./media/image_2.png)

* Verify the values and click **Import**.

* Spec has been imported into Apigee Edge & Ready to use. You should see your spec in the list.

![image alt text](./media/image_3.png)

* Click on the spec from the list to access the OpenAPI spec editor and interactive documentation that lists the backend API details and resources.

![image alt text](./media/image_4.png)

# Test the API Proxy

* Let us test the newly built API proxy using the [Apigee REST Client](https://apigee-restclient.appspot.com/). Open the REST Client in a new browser window.  

* Copy the URL for your API proxy. 

![image alt text](./media/image_17.png)

* Paste the link into the REST Client and make a GET call

![image alt text](./media/image_18.png)

* You should see a success response similar to this:
![image alt text](./media/image_19.jpg)

# Download the API Proxy

* Let’s download the API Proxy locally as an API Bundle so that we can reuse it in other labs.

* Download the API Proxy by downloading the current revision of the proxy. Return to the Overview tab, and see screenshot below for instructions.

![image alt text](./media/image_20.png)

# Lab Video

If you like to learn by watching, here is a short video on creating a reverse proxy using an Open API Specification - [https://youtu.be/3XBG9QOUPzg](https://youtu.be/3XBG9QOUPzg) 

# Earn Extra-points

* Now that you have created a reverse proxy using an OpenAPI spec, click on the "Develop" tab and explore the flow conditions populated from the OpenAPI spec. Also, explore the OpenAPI Spec editor where you can edit the OpenAPI specification and test the API requests. Finally, explore the "Trace" tab in the proxy overview page.

# Quiz

1. How do you import the proxy bundle you just downloaded? 
2. How does Apigee Edge handle API versioning? 
3. Are there administrative APIs to create, update and delete API proxies in Apigee?

# Summary

That completes this hands-on lesson. In this simple lab you learned how to create a proxy for an existing backend using an OpenAPI Specification and the Apigee proxy wizard.

# References

* Useful Apigee documentation links on API proxies:

    * Build a simple API Proxy - [https://docs.apigee.com/api-platform/fundamentals/build-simple-api-proxy](https://docs.apigee.com/api-platform/fundamentals/build-simple-api-proxy) 

    * Best practices for API proxy design and development - [https://docs.apigee.com/api-platform/fundamentals/best-practices-api-proxy-design-and-development](https://docs.apigee.com/api-platform/fundamentals/best-practices-api-proxy-design-and-development) 

* Watch this 4minute video on the "Anatomy of an API proxy" - [https://youtu.be/O5DJuCXXIRg](https://youtu.be/O5DJuCXXIRg) 

# Rate this lab

How did you like this lab? Rate [here](https://goo.gl/forms/G8LAPkDWVNncR9iw2).

Now go to [Lab-2](../Lab%202%20API%20Security%20-%20Securing%20APIs%20with%20API%20Keys)

