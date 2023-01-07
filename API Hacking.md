# API
An application programming interface (API) is a set of rules and protocols that specifies how two software programs should communicate with each other. APIs allow different software systems to communicate with each other, enabling them to exchange information and data. APIs are used in various industries and for various purposes. For example, a weather website may use an API to retrieve and display current weather data from a weather service provider. A social media platform may use an API to enable third-party developers to build applications that integrate with the platform.

APIs can be classified into different types based on their usage and implementation. Some common types of APIs include:
* Open APIs (also known as external or external APIs): These APIs are publicly available and can be accessed by external developers.
* Internal APIs (also known as private APIs): These APIs are used within an organization and are not publicly available.
* Partner APIs: These APIs are provided to a select group of developers or partners and are not publicly available.

APIs are typically accessed over the internet, using a specific protocol such as HTTP. An API request consists of a specific URL, along with a request method (such as GET or POST) and optional request parameters. The API server then processes the request and returns a response in the form of data or an error message. APIs use various authentication methods to ensure that only authorized users can access the API and its resources. Some common authentication methods include API keys, OAuth, and JSON Web Tokens (JWTs).

API design is a crucial aspect of API development, as a well-designed API can make it easier for developers to use and integrate with the API. Some best practices for API design include:

* Use clear, concise, and consistent naming conventions.
* Use standard HTTP response codes to indicate the status of an API request.
* Use versioning to allow for changes to the API without breaking existing integrations.
* Use documentation to provide clear and thorough instructions on how to use the API.

In conclusion, APIs are an essential tool for enabling communication between different software systems. By following best practices for API design and implementation, organizations can create APIs that are easy to use and integrate with, enabling them to expand their capabilities and reach.


# Types of API -
There are several types of APIs based on their usage and implementation:

1. Open APIs (also known as external or public APIs): These APIs are publicly available and can be accessed by external developers. Open APIs allow organizations to expose their functionality to the public, enabling external developers to build applications that integrate with their systems.

2. Internal APIs (also known as private APIs): These APIs are used within an organization and are not publicly available. Internal APIs are used to facilitate communication between different systems and teams within an organization, enabling them to share data and functionality.

3. Partner APIs: These APIs are provided to a select group of developers or partners and are not publicly available. Partner APIs are used to enable communication between different organizations, often in the context of a business partnership.

4. Composite APIs: These APIs allow developers to access multiple APIs through a single API call. Composite APIs are useful for reducing the number of API calls needed to retrieve data from multiple sources, improving the efficiency and performance of applications.

5. Library APIs: These APIs provide access to a specific library or functionality. Library APIs are often used to enable developers to use a specific set of tools or functionality within their own applications.

6. Webhooks: These APIs allow an application to receive real-time data or notifications from another application. Webhooks enable an application to react to events or changes in another system in real-time, without the need for the application to constantly poll for updates.


# Here are a few examples of APIs and how they are used:

* Twitter API: This API allows developers to access and integrate the functionality of Twitter with other applications. Using the Twitter API, developers can build applications that retrieve and display tweets, search for tweets, and programmatically post tweets.

* Google Maps API: This API allows developers to access and integrate the functionality of Google Maps with other applications. Using the Google Maps API, developers can build applications that display maps, retrieve driving directions, and search for places and points of interest.

* PayPal API: This API allows developers to access and integrate the functionality of PayPal with other applications. Using the PayPal API, developers can build applications that enable users to make payments, process transactions, and manage their PayPal accounts.

* Spotify API: This API allows developers to access and integrate the functionality of Spotify with other applications. Using the Spotify API, developers can build applications that retrieve and play music from the Spotify library, search for songs and artists, and create and manage playlists.

* Slack API: This API allows developers to access and integrate the functionality of Slack with other applications. Using the Slack API, developers can build applications that send and receive messages, create and manage channels, and interact with other Slack users.

![](https://assets.website-files.com/5ff66329429d880392f6cba2/61555448696635114d8260f5_API%20work.svg)

## Here is an example of a simple API written in Go that returns a list of users in JSON format:
```
package main

import (
	"encoding/json"
	"net/http"
)

type User struct {
	ID       int    `json:"id"`
	Username string `json:"username"`
	Email    string `json:"email"`
}

var users []User

func main() {
	http.HandleFunc("/users", func(w http.ResponseWriter, r *http.Request) {
		w.Header().Set("Content-Type", "application/json")
		json.NewEncoder(w).Encode(users)
	})

	http.ListenAndServe(":8080", nil)
}
```
This API has a single endpoint, /users, which returns a list of users in JSON format when a GET request is made to it. The users variable is a slice of User structs, which represent the user records in the API.

To run the API, you can build and run the Go program. The API will listen for incoming requests on port 8080. For example, you can test the /users endpoint by making a GET request to http://localhost:8080/users using a tool such as cURL or a web browser. This is just a simple example, and in a real-world API, you would likely have additional endpoints and functionality, such as the ability to create, update, and delete user records. You may also want to add authentication and authorization to secure the API and ensure that only authorized users can access its resources.


## Here is an example of a simple API written in Python using the Flask web framework - 
```
from flask import Flask, jsonify

app = Flask(__name__)

users = [
    {
        "id": 1,
        "username": "user1",
        "email": "user1@example.com"
    },
    {
        "id": 2,
        "username": "user2",
        "email": "user2@example.com"
    }
]

@app.route("/users", methods=["GET"])
def get_users():
    return jsonify(users)

if __name__ == "__main__":
    app.run()
```
This API has a single endpoint, /users, which returns a list of users in JSON format when a GET request is made to it. The users variable is a list of dictionaries, which represent the user records in the API.

To run the API, you can execute the Python script. The API will listen for incoming requests on the default port (5000). For example, you can test the /users endpoint by making a GET request to http://localhost:5000/users using a tool such as cURL or a web browser. This is just a simple example, and in a real-world API, you would likely have additional endpoints and functionality, such as the ability to create, update, and delete user records. You may also want to add authentication and authorization to secure the API and ensure that only authorized users can access its resources.

# API Hacking

API hacking refers to the practice of exploiting vulnerabilities in APIs in order to gain unauthorized access to systems or data. API hacking can be used to attack both the server-side and client-side of an API.

On the server-side, API hacking can involve tactics such as injection attacks (e.g., SQL injection), in which an attacker injects malicious code into an API request in an attempt to execute unintended actions on the server. Server-side API hacking can also involve attacks such as denial of service (DoS), in which an attacker floods an API with requests in an attempt to overwhelm and disable it.

On the client-side, API hacking can involve tactics such as man-in-the-middle attacks, in which an attacker intercepts and modifies API traffic in order to gain unauthorized access to data or systems. Client-side API hacking can also involve attacks such as replay attacks, in which an attacker captures and replays valid API requests in an attempt to gain unauthorized access.

To prevent API hacking, organizations should implement security measures such as input validation, authentication, and authorization. It is also important to regularly test and monitor APIs for vulnerabilities, and to promptly apply any necessary security patches or updates.

#### Here are a few examples of API hacking - 

* SQL injection: This is a type of injection attack in which an attacker injects malicious code into an API request in an attempt to execute unintended actions on the server, such as accessing or modifying sensitive data. For example, an attacker might send an API request with a maliciously crafted parameter that contains SQL code, in an attempt to retrieve sensitive information from a database.

* Man-in-the-middle attack: In this type of attack, an attacker intercepts and modifies API traffic in order to gain unauthorized access to data or systems. For example, an attacker might intercept an API request and modify the parameters to gain access to a user's account.

* Replay attack: This is a type of attack in which an attacker captures and replays valid API requests in an attempt to gain unauthorized access. For example, an attacker might capture a valid API request to transfer funds from one account to another, and then replay the request multiple times in an attempt to drain the account.

* Denial of service (DoS) attack: In a DoS attack, an attacker floods an API with requests in an attempt to overwhelm and disable it. This can prevent legitimate users from accessing the API and cause disruptions to the system.

It is important for organizations to implement security measures to prevent API hacking and protect their systems and data from these types of attacks.


#### Here are the top 10 OWASP (Open Web Application Security Project) API vulnerabilities and a brief explanation of each - 

* Broken object level authorization: This vulnerability occurs when an API does not properly enforce object-level permissions, allowing unauthorized users to access or modify sensitive data.

* Broken authentication and session management: This vulnerability occurs when an API has weak or flawed authentication and session management controls, allowing attackers to gain unauthorized access to the system.

* Injection: This vulnerability occurs when an API is susceptible to injection attacks, such as SQL injection, allowing attackers to execute unintended actions on the server or access sensitive data.

* Security misconfiguration: This vulnerability occurs when an API has insecure default configurations, incomplete or weak configuration settings, or exposed sensitive information.

* Sensitive data exposure: This vulnerability occurs when an API exposes sensitive data, such as passwords, to unauthorized users.

* XML external entity (XXE) injection: This vulnerability occurs when an API is susceptible to XXE injection attacks, allowing attackers to access sensitive data or execute unintended actions on the server.

* Broken function level authorization: This vulnerability occurs when an API does not properly enforce function-level permissions, allowing unauthorized users to access or modify sensitive data.

* Cross-site scripting (XSS): This vulnerability occurs when an API is susceptible to XSS attacks, allowing attackers to inject malicious code into the API and execute it on the client-side.

* Insecure direct object references: This vulnerability occurs when an API exposes direct object references, allowing unauthorized users to access sensitive data.

* Failure to restrict URL access: This vulnerability occurs when an API does not properly restrict access to URL resources, allowing unauthorized users to access sensitive data.

It is important for organizations to identify and address these types of vulnerabilities in order to protect their APIs and systems from attack.



# Links to learn API hacking - 

1. OWASP API Security Project: This project is a comprehensive resource for information on API security, including a list of the top 10 API vulnerabilities and guidance on how to prevent and mitigate them.
2. API Security Top 10 by API Fortress: This resource provides an overview of the top 10 API security risks, along with practical advice on how to address them.
3. API Security Checklist by GitHub: This checklist provides a list of best practices for securing APIs, including recommendations for authentication, authorization, and data protection.
4. API Security Best Practices by Amazon Web Services: This resource provides a list of best practices for securing APIs, including guidance on how to design and implement secure APIs.
5. API Security 101: The Biggest API Security Threats by Nordic APIs: This article provides an overview of the most common API security threats, along with tips for preventing and mitigating them.

In addition to these resources, there are also many online courses, training programs, and certification programs that cover API security and hacking. It is important for organizations to invest in ongoing training and education to ensure that their API security practices are up to date and effective.

# Links - 
1. OWASP API Security Project: https://www.owasp.org/index.php/OWASP_API_Security_Project
2. API Security Top 10 by API Fortress: https://apifortress.com/top-10-api-security-risks/
3. API Security Checklist by GitHub: https://github.com/shieldfy/API-Security-Checklist
4. API Security Best Practices by Amazon Web Services: https://aws.amazon.com/api-gateway/security-best-practices/
5. API Security 101: The Biggest API Security Threats by Nordic APIs: https://www.nordicapis.com/api-security-101-the-biggest-api-security-threats/



# Resources - 

APIs || Hacking
* Alex Wang’s post - What is an API, and how does it work? - https://lnkd.in/eSih-jU9
* Cyber-Guy1 - https://github.com/Cyber-Guy1/API-SecurityEmpire/tree/main/assets
* API Hacking beginners guide by Dana Epp - https://lnkd.in/eCcQSdxW
* Corey Ball API workshop here - https://lnkd.in/eZn3aZ66
* APIsec University by Corey J. Ball and Dan Barahona - https://lnkd.in/ez3jh2Gj
* MalAPI by mrd0x - https://malapi.io/
* MindAPI by David Sopas - https://lnkd.in/g3FAtwiA
* Hackxpert | OWASP top 10 api training - https://lnkd.in/eh8skkDZ
* VAmPI by erev0s - https://lnkd.in/gKtw63hy , https://lnkd.in/eab9Y6Br
* APISecure Conference all their 2022 videos are available on their website - https://lnkd.in/e7ge2qRv
* Hacking mHealth Apps and APIs on KnightTV with Alissa Valentina Knight - https://lnkd.in/gF5kqysD
* Credit | **Gabrielle B** - https://www.linkedin.com/in/gabriellebotbol/

### If you are interested in becoming a pro in API hacking, here are a few steps you can follow:-

* Start by learning the fundamentals of API security and hacking. This can include learning about common API vulnerabilities and attack vectors, as well as best practices for securing APIs. Resources such as the OWASP API Security Project and the API Security Top 10 by API Fortress can be helpful for learning about these topics.

* Gain practical experience by testing and hacking APIs. This can be done through hands-on projects or exercises, such as setting up your own API and attempting to find and exploit vulnerabilities, or participating in online capture-the-flag (CTF) competitions that focus on API hacking.

* Enhance your skills through training and education. There are many online courses and training programs that cover API security and hacking, as well as certification programs such as the Certified API Security Expert (CASE) offered by the Open Web Application Security Project (OWASP).

* Stay up to date with the latest developments in API security. This can include reading industry blogs and publications, following security experts on social media, and attending conferences and workshops on API security. By following these steps, you can gain a strong foundation in API security and hacking and continue to build and improve your skills over time.

 #  Hacking API Resources(YouTube) - 
 * APIs for Beginners - How to use an API (Full Course / Tutorial) - https://www.youtube.com/watch?v=GZvSYJDk-us
 * Postman Beginner's Course - API Testing - https://www.youtube.com/watch?v=VywxIQ2ZXw4
 * APi Pentesting full course - https://www.youtube.com/watch?v=vCJVFnepECc&list=PLUDwpEzHYYLuW9XEvFEJk2kqsk6HqscI4
 * Finding Your First Bug: Finding Bugs Using APIs - https://www.youtube.com/watch?v=yCUQBc2rY9Y&list=PLbyncTkpno5HqX1h2MnV6Qt4wvTb8Mpol
 * How To Hack An API In 15 Minutes - Igor Matlin - https://www.youtube.com/watch?v=JH2bH8duj2c
 * API hacking with postman Part 1 - getting the basics down - https://www.youtube.com/watch?v=rdxVgV8dOnQ&list=PLd92v1QxPOprsg5fTjGBApq4rpb0G-N8L
 * Hacking APIs and Cars: You need to learn this in 2023! - https://www.youtube.com/watch?v=4VaHN4CG34w
 * API Hacking 101, w/ Dr. Katie Paxton-Fear | by Traceable AI - https://www.youtube.com/watch?v=qC8NQFwVOR0
 * What AI can do for API Security - https://www.youtube.com/watch?v=sZq3LrRIkEo
 * Traceable AI: The Industry’s 1st Free API Security Solution - https://www.youtube.com/watch?v=cERz3HciSOo&list=PL8IDSDRZxCCANEpMNtod31YOI1JpB30Qt
