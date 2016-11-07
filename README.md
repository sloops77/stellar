# stellar
Nowadays web systems are never merely client and server. This way of looking at them is year 2000 thinking. Instead they are interconnected clusters of servers,  some servers offer endpoints to clients, others process jobs, some do both and the question you ask is: how do we split these things apart? Usually the api's offered for these tasks are distinct and different.

Stellar is a nodejs web systems framework, it is a microservices framework. And microservices are the accepted way to build scalable systems. It offers a consistent api for all the different and distinct tasks microservices need to accomplish.

Stellar is easy to get started on offering a familiar way to expose endpoints to express or meteor.

But is based on standard message exchange patterns that are tried and tested to work and are needed any but the most trivial demo applications.

It is even easier to migrate and scale once you need to.

Stellar wraps this up in an easy to use API

**Whats different about Stellar?**

1. Stellar is fucking fast! Fast to develop on, Fast in production.

2. Stellar is designed for scale FOR REAL. It is unlike Meteor or Express - these are monolithic servers that once they get to certain number of endpoints are slow to reload, slow in production, difficult to maintain, leads to merge hells and more. Once you start growing you look at ways of splitting your servers using whichever technologies you are comfortable with but they may not be the best in class (eg. using mongo as a job framework, or using a PAAS offering). Instead use Stellar from the start in single server mode and it'll grow with you as your codebase grows and you need to move to a microservices architecture. When you grow, just refactor your stellar code move your code to a new deployment module and (optionally) changing your endpoint. Job done!

3. Stellar doesnt tie you in to a chosen stack. The only dependencies are industry standard libraries like bluebird promises. Currently it is tied to redis, but is designed to be easily extendable. Want 0MQ or rabbitmq? Great, just write a different transport and we'll link to it. Prefer sock.js to engine-io? Great its just another transport for stellar.

4. Unlike meteor: stelar doesnt try to take over the build process, doesn't force you to use one database, works with multiprocess by default, doesnt try and force you to use graphql. All it is a series of pipes that connect your rich client, to your server code AND your server code to your other server code.

## Getting Started

### REST interface
Currently stellar offers a CRUD-like or REST-like api to clients
* create
* update
* remove
* get
 
Currently will try once to deliver the request. Like a REST endpoint you can also ignore the response if you like.

**TODO** allow adjustment of retry settings
 
### Get & Subscribe
Similar to retreve request/response but also subscribes to a channel for data changes. This is similar to Meteor's Publish/Subscribe mechanism.

### Publish/Subscribe
This provides the ability for one microservice to subscribe to a publication from another microservice. Unlike a tool like redis which say can offer between node processes pub sub, this is at the microservice to microservice level.

