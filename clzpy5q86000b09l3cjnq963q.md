---
title: "What Happens When You Type "google.com" and Start Searching?"
seoTitle: "What Happens When You Type "google.com" and Start Searching?"
datePublished: Sun Aug 11 2024 19:17:36 GMT+0000 (Coordinated Universal Time)
cuid: clzpy5q86000b09l3cjnq963q
slug: what-happens-when-you-type-googlecom-and-start-searching
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1723399090167/31257db6-e5c9-4427-86a4-c20486ad4aa6.jpeg
tags: software-development, programming-blogs, javascript, browsers, python, web-development, chrome, webdev, beginner, reactjs, google, beginners, software-engineering, internet, web3

---

When you type "[google.com](http://google.com)" into your browser’s address bar and hit enter, a series of complex processes are triggered behind the scenes, resulting in the webpage loading and you being able to start searching. While the entire process is highly optimized and happens in milliseconds, it involves several key steps. Let’s break down what happens in a bit of technical detail.

## 1\. **Domain Name System (DNS) Lookup**

The first step begins with resolving the human-readable domain name "[google.com](http://google.com)" into an IP address, which is necessary for communication over the internet. Here’s how it happens:

* **Cache Check**: Your browser first checks its DNS cache to see if it has recently visited "[google.com](http://google.com)." If it has, the cached IP address is used, skipping the DNS lookup.
    
* **OS Cache**: If the browser doesn’t have the IP address, it asks the operating system to check its cache.
    
* **Router and ISP Cache**: If neither the browser nor the OS has the information, the request is sent to your router, and then to your Internet Service Provider (ISP). Both may have DNS caches.
    
* **Recursive DNS Query**: If the IP address is not found in any cache, the ISP’s DNS resolver queries other DNS servers. The query goes through a hierarchical system, starting from the root DNS servers, down to the Top-Level Domain (TLD) servers (e.g., ".com" servers), and finally to Google’s authoritative DNS servers, which return the IP address associated with "[google.com](http://google.com)."
    
    ![How does the Domain Name System (DNS) lookup work?](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F5dd6a922-eea7-49b3-aa1a-b1e21793a36a_1999x908.png align="left")
    

## 2\. **TCP/IP Connection**

Once the IP address is obtained, your browser establishes a connection to the Google servers using the Transmission Control Protocol (TCP) over Internet Protocol (IP). This involves:

* [**Three-Way Handshake**](https://www.sciencedirect.com/topics/computer-science/three-way-handshake): A TCP connection is established through a process known as the three-way handshake:
    
    * **SYN**: Your browser sends a synchronization packet (SYN) to Google’s server.
        
    * **SYN-ACK**: The server responds with a synchronization-acknowledgment (SYN-ACK) packet.
        
    * **ACK**: Finally, your browser sends an acknowledgment (ACK) packet back to the server, establishing the connection.
        

At this point, your browser and the Google server are ready to exchange data.

![Three-Way Handshake - an overview | ScienceDirect Topics](https://ars.els-cdn.com/content/image/3-s2.0-B0122272404001878-gr10.gif align="left")

## 3\. [**SSL/TLS Handshake**](https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/)

Given that Google uses HTTPS for secure communication, an SSL/TLS handshake occurs next:

* **ClientHello**: Your browser sends a ClientHello message to the server, including details like supported SSL/TLS versions and cipher suites.
    
* **ServerHello**: The server responds with a ServerHello message, selecting the SSL/TLS version and cipher suite.
    
* **Certificate Exchange**: Google’s server sends its SSL/TLS certificate, which your browser validates to ensure the authenticity of the server.
    
* **Session Keys**: Both the browser and the server generate session keys for encrypting the data that will be transmitted.
    
    ![A SSL/TLS handshake. | Download Scientific Diagram](https://www.researchgate.net/publication/300402166/figure/fig2/AS:349301646610438@1460291410455/A-SSL-TLS-handshake.png align="left")
    

## 4\. **Sending the HTTP Request**

Now that a secure connection is established, your browser sends an [HTTP request](https://www.uptimia.com/learn/what-is-http-request) to the Google server. The request typically looks like this:

```plaintext
GET / HTTP/1.1
Host: www.google.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
```

This request tells the server that your browser wants to retrieve the main page of "[google.com](http://google.com)."

![4 steps are involved in a typical HTTP request - DEV Community](https://media.dev.to/cdn-cgi/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Frppelgps0pzavwq977vf.gif align="left")

## 5\. **Server Response and Rendering the Page**

* **HTTP Response**: Google’s server processes the request and responds with an HTTP response, which includes the HTML, CSS, JavaScript, and other resources needed to render the page. For example:
    

```plaintext
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8
Content-Length: 12345
```

* **Rendering**: Your browser receives the response and starts parsing the HTML. It then fetches the CSS files, which determine the layout and styling, and executes JavaScript files that add interactivity. The browser’s rendering engine constructs the Document Object Model (DOM) tree and the CSS Object Model (CSSOM) tree, which together represent the page’s content and style.
    
* **Painting and Compositing**: Finally, the browser paints the content on the screen and composites layers (e.g., for overlapping elements) to render the complete webpage.
    
    ![What is Server-Side Rendering? Definition and FAQs | HEAVY.AI](https://cdn.prod.website-files.com/620d42e86cb8ec4d0839e59d/6230e9ad9a22b134ae9eceb8_61cb64ed587c1111fb1dc917_SSR-server-side-rendering-infographic.png align="left")
    

## 6\. **Search Query Execution**

Now that the Google homepage is loaded, you enter a search query and press enter. Here’s what happens:

* **AJAX Request**: When you submit the query, your browser sends an asynchronous JavaScript and XML (AJAX) request to Google’s search API endpoint. This request usually looks like:
    

```plaintext
POST /search?q=your+query HTTP/1.1
Host: www.google.com
```

* **Search Algorithm Execution**: Google’s server processes the query using its complex search algorithms, which involve indexing, ranking, and filtering billions of web pages to find the most relevant results.
    
* **Search Results Delivery**: The server then sends back a JSON response with the search results. Your browser dynamically updates the page with these results using JavaScript without requiring a full page reload.
    
    ![FIRST CLASS SQL for FULL-TEXT SEARCH - The Couchbase Blog](https://www.couchbase.com/blog/wp-content/uploads/2020/07/Screen-Shot-2020-07-01-at-7.02.40-PM.png align="left")
    

## 7\. **Content Delivery and Interaction**

As you interact with the search results, additional HTTP requests may be made (e.g., when loading images, videos, or more results). The entire process is optimized for speed and efficiency, ensuring that your experience is as seamless as possible.

![What is CDN (Content Delivery Network) Streaming & How it Works](https://d1zsdp7qbliduy.cloudfront.net/blog/wp-content/uploads/2023/08/how-does-a-content-delivery-network.webp align="left")

## Conclusion

The process of visiting "[google.com](http://google.com)" and performing a search involves a fascinating interplay of various technologies, from DNS resolution to secure TCP connections and HTTP requests. Despite the complexity, these operations are so well-optimized that they take place in just a few hundred milliseconds, providing you with instant access to the information you seek.