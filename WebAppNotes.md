# Basic working of a web app
Users use a mobile app or a website to access their services. The
browser/app obtains the IP address from the DNS (Domain Name Severs). Then a 
HTTP response are sent to the web srever. The webserver responds with a HTML page
or a with a JSON file. JSON is commonly used for the sake of a simple interface. 
A database is added as the webapp scales. The data bases can be relational or 
non-relational. Non relational databases are used in a wide variety of applications (like low latency).
You can choose it based on your the requirements of the application.

# Types of scaling
Vertical Scaling:Adding more CPUs, RAMS, better hardware. There is a limit on how much you can vertically scale up.

Horizontal Scaling: Adding more webservers. Used more in real life and more robust than verticle scaling as there are more servers in case one of them fail.
Load balancing is a common technique used to achieve horizontal scaling. 

Database replication: While we can use load balancing to scale servers, what about the databases? In database replication, you have
one master database and multiple slave databases. Master typically supports only write operations and slave supports read
operations. The data from the master is replicated to the slaves. In case you lose data from one database, it is still preserved in the others.
Data that is frequently requestd and not modified is stored in a cache on first retreival. CDNs are used for retreving static content (eg. images/logos that don't change).

Scaling web tier horizontally: You add more servers and you achieve horizontal scaling on the web tier. It can be done with either a stateful or a
stateless architecture. A stateful architecture remembers the client requests from one call to the next. A stateless archiecture is one where the webservers
don't remember client states.


