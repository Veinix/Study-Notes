# APIs / REST

Imagine you have a box of toys and you want to play with them. Instead of throwing the toys randomly, you organize them neatly in different compartments. You also put labels on each compartment to know what type of toy is inside. Now, if your friend wants to play with a specific toy, they can ask you by saying the name of the toy they want. You find that toy in the compartment, take it out, and give it to your friend. In this case, you are like the server and your friend is like a client requesting a toy. The organized compartments and labels represent the structure and information of a RESTful API, which allows computers to communicate and exchange data in a similar organized manner.

[Back](../Index/index.md)

## Table of Contents

- [Overview](#overview)
- [Creating a RESTful API]

[Link to Sources](./apiMain.md#sources)

## Overview

REST is a set of architectural constraints, not a protocol or a standard. API developers can implement REST in a variety of ways.

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON (Javascript Object Notation), HTML, XLT, Python, PHP, or plain text. JSON is the most generally popular file format to use because, despite its name, it’s language-agnostic, as well as readable by both humans and machines. 

Something else to keep in mind: Headers and parameters are also important in the HTTP methods of a RESTful API HTTP request, as they contain important identifier information as to the request's metadata, authorization, uniform resource identifier (URI), caching, cookies, and more. There are request headers and response headers, each with their own HTTP connection information and status codes.

In order for an API to be considered RESTful, it has to conform to these criteria:

- A client-server architecture made up of clients, servers, and resources, with requests managed through HTTP.
- Stateless client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
- Cacheable data that streamlines client-server interactions.
- A uniform interface between components so that information is transferred in a standard form. This requires that:
    - resources requested are identifiable and separate from the representations sent to the client.
    - resources can be manipulated by the client via the representation they receive because the representation contains enough information to do so.
    - self-descriptive messages returned to the client have enough information to describe how the client should process it.
    - hypertext/hypermedia is available, meaning that after accessing a resource the client should be able to use hyperlinks to find all other currently available actions they can take.
- A layered system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval of requested information into hierarchies, invisible to the client.
- Code-on-demand (optional): the ability to send executable code from the server to the client when requested, extending client functionality. 

Though the REST API has these criteria to conform to, it is still considered easier to use than a prescribed protocol like SOAP (Simple Object Access Protocol), which has specific requirements like XML messaging, and built-in security and transaction compliance that make it slower and heavier. 

In contrast, REST is a set of guidelines that can be implemented as needed, making REST APIs faster and more lightweight, with increased scalablity—perfect for Internet of Things (IoT) and mobile app development. 

## Creating a RESTful API

### Step 1:

Determine the Purpose of Your API
Decide what your API will do and what kind of data it will handle. This could be retrieving, creating, updating, or deleting data related to a specific domain.

### Step 2:
Design Your API Endpoints
Endpoints are specific URLs that the client can use to interact with your API. Each endpoint represents a specific functionality or resource. For example, "/users" could be an endpoint to retrieve a list of users, while "/users/{id}" could be an endpoint to retrieve a specific user by their ID.

### Step 3:
Choose HTTP Methods
RESTful APIs use HTTP methods (verbs) to define the type of operation being performed on a resource. The most common methods are GET (retrieve data), POST (create data), PUT/PATCH (update data), and DELETE (delete data).

### Step 4:
Design Your Data Model
Determine the structure and format of the data you will send and receive. This typically involves defining JSON or XML representations of your resources.

### Step 5:
Implement the API Endpoints
Using a programming language or framework of your choice, write the code to handle the requests to your API endpoints. This includes processing the requests, interacting with a database or other data source, and generating appropriate responses.

### Step 6:
Handle Errors and Validation
Implement error handling mechanisms to provide meaningful error messages when something goes wrong. Validate the input data to ensure it meets the expected criteria.

### Step 7:
Test Your API
Create test cases to ensure your API functions as expected. Test different scenarios, such as successful requests, error cases, and edge cases.

### Step 8:
Document Your API
Create documentation that explains how to use your API. Include information about each endpoint, the required data format, authentication mechanisms, and any additional instructions for developers.

### Step 9:
Deploy Your API
Choose a hosting platform or server to deploy your API. Make sure it is accessible to clients over the internet.

### Step 10:
Maintain and Update Your API
Regularly monitor and maintain your API. Listen to feedback, address issues, and update the API as needed to meet the changing requirements of your users.

Remember, creating a RESTful API can be complex and involves many technical aspects. It's important to have a good understanding of web development concepts, programming languages, and frameworks to build a robust and secure API.

---

[Back to top](#application-programming-interfaces-apis)
