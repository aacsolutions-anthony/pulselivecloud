Cyber Security Overview Document 

Development of this project is to allign with the goals pertained in this document. 

For these descriptions there are 4 moving parts: 

1. Manager
2. Cloud proxy
3. Nginx proxy / venue nginx / venue proxy
4. Pulselive / venue / venues 

The manager connects to the cloud proxy website which has a dashboard of all venues associated with them. 
Once the manager selects a server to connect to, a new tab opens which is the nginx proxy to PulseLive. 
This is extra HTTPS proxy is required, as a public facing DB with unencrypted traffic straight to a login page is known as a *bad idea*. 
This extra proxy also allows us to setup whitelists (blacklist not recommended) so that any conneciton other than the cloud server is blocked. 
This prevents spiders and crawling or testing of the internal PulseLive logon page which would **severely** slow down client networks. 
Cloudflare checks along the way of this chain also ensure that no one else can DoS or DDoS the secure tunnel, only allowing authorized connections, encrypting them, then transporting them around the globe to where they need to be. 

Minimum security requirements: 

1. User authentication against hashed password DB
2. Google Recaptcha on Cloud login 
3. Anti-clickjacking header
4. CSRF Tokenization
5. Managers can only visit their specified venues as outlined in config files
6. TLS HTTPS Conneciton to the venues reverse proxy
7. Cloudflare DDoS check on Cloud proxy server
8. venue nginx server only accepts requests from Cloud server using IP whitelist
9. Plan in place to wrap pulse live under nginx and uWSGI or other. / Encrypt communication between venue proxy and pulselive.

High level description: 
    User Authentication System: You need an application on your cloud server which handles user authentication. This could be a web application using any web development framework like Django, Flask, Rails, Express.js, etc. The application will authenticate users and maintain a session for each authenticated user.

    User-Server Mapping: The application must also keep a record of which server each user should be redirected to after they're authenticated. This could be a database table with each user's ID and the corresponding server's URL or IP address.

    Redirection: Once a user is authenticated, the application will look up the server the user should be redirected to and send a HTTP redirect response to the client. The client's browser will then make a new request to the redirected server.

    Nginx Configuration: Each Nginx server should be configured to reverse proxy requests to the correct internal server based on the received requests.

    User-Specific Access Control: To ensure a user can't access another user's server, you could include the user's ID or some other unique identifier in the redirected URL, and have the Nginx server check this against the user-server mapping. If they don't match, Nginx would return an error response.


Checkmark criteria: 
Passes basic Kali Tool test by red team in QA. 

Author and contact: 
Anthony - AAC Solutions 
