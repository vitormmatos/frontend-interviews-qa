# WEB

- [WEB](#web)
  - [What is Git?](#what-is-git)
  - [What is HTTP?](#what-is-http)
  - [What is DNS?](#what-is-dns)
  - [What is JWT?](#what-is-jwt)
  - [What is CORS?](#what-is-cors)
  - [What is SSL?](#what-is-ssl)
  - [What is FTP?](#what-is-ftp)
  - [What is REST?](#what-is-rest)
  - [What are the differences between Local Storage, Session Storage and Cookie?](#what-are-the-differences-between-local-storage-session-storage-and-cookie)
    - [**Local Storage**](#local-storage)
    - [**Session storage**](#session-storage)
    - [**Cookie**](#cookie)

## What is Git?

Git is a free and open source distributed **version control** system designed to handle everything from small to very large projects with speed and efficiency.

**[⬆ Back to Top](#web)**

## What is HTTP?

HTTP is a protocol for **fetching resources** such as HTML documents. It is the foundation of any data exchange on the Web and it is a **client-server protocol**, which means requests are initiated by the recipient, usually the Web browser. A complete document is reconstructed from the different sub-documents fetched, for instance, text, layout description, images, videos, scripts, and more.

**[⬆ Back to Top](#web)**

## What is DNS?

The Domain Name System (DNS) turns **domain names** into **IP addresses**, which browsers use to load internet pages.

Every device connected to the internet has its own IP address, which is used by other devices to locate the device.

DNS servers make it possible for people to input normal words into their browsers, such as github.com, without having to keep track of the IP address for every website.

**[⬆ Back to Top](#web)**

## What is JWT?

JSON Web Tokens are an **open**, **industry standard method** for representing claims **securely** between **two parties**.

**[⬆ Back to Top](#web)**

## What is CORS?

Cross-origin resource sharing (CORS) is a mechanism that allows **restricted** resources on a web page to be requested from another domain **outside** the domain from which the first resource was served.

**[⬆ Back to Top](#web)**

## What is SSL?

SSL, or Secure Sockets Layer, is an **encryption**-based Internet **security protocol** with the purpose of ensuring **privacy**, **authentication**, and **data integrity** in Internet communications. SSL is the predecessor to the modern **TLS** encryption used today.

**[⬆ Back to Top](#web)**

## What is FTP?

The File Transfer Protocol (FTP) is a standard **communication protocol** used for the **transfer** of **computer files** from a **server** to a **client** on a computer network.

FTP is built on a client–server model architecture using separate control and data connections between the client and the server.

**[⬆ Back to Top](#web)**

## What is REST?

Representational state transfer (REST) is a software architectural style that describes a uniform interface between decoupled components in the Internet in a **Client-Server architecture**.

REST defines four interface constraints:

- Identification of resources
- Manipulation of resources
- Self-descriptive messages and
- hypermedia as the engine of application state

Generally it describes a machine to machine interface and more specifically in web development it allows for an addition or replacement of server-side rendering to assist client-side rendering in web applications as client server model where the web browser acts as the client.

**[⬆ Back to Top](#web)**

## What are the differences between Local Storage, Session Storage and Cookie?

### **Local Storage**

localStorage is a way to **store data** on the client’s computer. It allows the saving of **key/value pairs** in a web browser and it stores data with no **expiration date**.

localStorage can only be accessed via JavaScript, and HTML5. However, the user has the ability to clear the browser data/cache to erase all localStorage data.

Pros:

- stores data with no expiration date
- storage limit is about 5MB
- data is never transferred to the server

Cons:

- plaintext, hence not secure by design
- limited to string data, hence need to be serialized
- can only be read on client-side

**[⬆ Back to Top](#web)**

### **Session storage**

Same as localstorage , we can write key-value pair in session storage as well.

- stores data only for a session, meaning that the data is stored until the browser (or tab) is closed
- data is never transferred to the server
- can only be read on client-side
- storage limit is about 5-10MB
- opening multiple tabs/windows with the same URL creates sessionStorage for each tab/window

**[⬆ Back to Top](#web)**

### **Cookie**

Cookies can be updated , set using document.cookie object from browser window object.

- Stores data that has to be sent back to the server with subsequent XHR requests. Its expiration varies based on the type and the expiration duration can be set from either server-side or client-side .
- Cookies are primarily for server-side reading (can also be read on client-side), localStorage and sessionStorage can only be read on client-side.
- Size must be less than 4KB.
- Cookies can be made secure by setting the httpOnly flag as true for that cookie. This prevents client-side access to that cookie.

**[⬆ Back to Top](#web)**
