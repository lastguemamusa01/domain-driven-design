# domain-driven-design
domain driven design 101 linked in courses


DDD(Domain Driven Design) - is an essential architecture process in both the microservice and the agile worlds.
for architect for highly modular systems that can grow incrementally.

DDD authored by Eric Evans. Developed before agile and microservices existed.
 
applied before in monolithic architecture and now in microservices architecture.

another good bock is Domain Driven Design distilled written by Vauhgn Vernon. concise and easier to follow and more up-to-date information.

DDD

* collborative - buisness people and developers must work together daily throughout the project <- also agile manifesto
* Modeling - DDD is built on the notion of modeling. structure of the code models one-to-one to the strucutre of the domain.
    * example : domain-> accounting, storefront, etc.(make sense to business user to look at the overall large struture of your system)
* all collaborators can make sense of the struture
* changes are made to the domain, which maps to where code changes should occur.
    * example: when change happens in one place, it is easy to make changes in the other. (main advantage of DDD)
    * changes happen in the domain not in the code. domain is one to one to the code.
* Incremental - come up with only enough architecture to slve the immediate problem
    * the code evolves as you learn more about the problem and more architecture is added.


A domain-driven design architecture is designed to grow incrementally over time.

Domain is going to influence the system. also system influcens domain. -> for releasing incrementally. Cyclic process.

you release the small portion of the code. the users will use your app or system. the users will ask some issues or improvement to get the next release code. 


DDD works well with agile. 

agile - inspect and adapt loop - small change, released, assesed with talk with user, get feedback and you improve.

stories in agile - short narrative, a couple of sentences, describes end user performing a domain-driven, result-oriented task. describes your user's work. provide value to user when the story is implemented.


microservice - microservices address the issue of complexity within a monolithic application. a lot of dependencies in monolith. 

problems with the monolith 

* tends to access data only - tends to focus on data. data model changed, the monolith and the code has to change also, and that's very difficult.
* hard to update 
* hard to deploy - it is large
* hard to maintain
* accretes cruft - junk accumulate
* agility is impossible

all us this cost money.


microservice - breaks the monolith in to series of small services. they talk to each other through network. but break into pieces the monolith cannot be microservices.

DDD is almost an ideal way to design a set of microservices.

Advantages of microservices 

* small - OOP class
* indepently deployable
* hide implementation details
* modeled around business concepts
* decentralized
* highly observable - when something going wrong
* autonomous - isolation. you can make change in one service and not changes in another services.

DDD is organizing code along certain weel-defined boundaries.

* Bounded Contexts - natural division within a business

example: a bookstore

store itself is a context

purpose of the context is to sell books to people.

warehouse is the another context - shipping 

so there are 2 context

* wharehouse - shipping
* store - sales


to seperate the context you need to ask this questions : 

what are the responsibilities of the people working within that context ?

what happens inside the contexts stays inside the contexts.

An entity is an individual within a given context.

An aggregate is a collection of entities you talk to through a single portal.


* entity
    * much like an object/class in object oriented world
    * has one job and does one thing
    * does that in a specific context


Entity vs Aggregate

* line between entity and aggregate can be fuzzy
* portal into aggregate looks like an entity
* portal entities use other entities in aggregate to get work done
* determining entity or aggregate may not be visible from the outside of the context


A portal entity uses other entities within an aggregate to accomplish tasks

![image](https://user-images.githubusercontent.com/73188710/168500598-5f9a6a0c-a17a-4add-a8cf-c499f3f98179.png)


Ubiquitous language

* people working within a context use a language all their own
* language of one context is different than other contexts

for sales in store - authors, views, readability and length

actions for sales in store - sell, shelf, organize

for shpping of warehouse - weight, size, shelf.

actions for warehouse - picke off shelves, box books.

the language itself will be reflected within the code.

Ubiquitous language - you will use this when talking about the problems that you are solving, reflected in the code itself, used at domain level to describe work. 

language is ubiquitous within a specific context.

to know if the language is belong to specific context.

* look at the way you decribe something
* which language is most appropiate ?

names

* distinguish between actors(people) and roles(tasks)
* Actors may accomplish tasks in different roles
* Entities named after roles, not actor.

entity is roles(tasks)

example : 

TimeSheet System


Manage 

* Authorizes timesheets

Employee

* Fill out the timesheets


Ubiquitous language tries to identify roles for entities. 



Data model for traditional ways , is thinking about normalization and relational database

![image](https://user-images.githubusercontent.com/73188710/168501227-53bc9f30-4e43-425a-8c95-ca205287cfe7.png)

there is entities outside of the context, in DDD that is bad thing.

because Every entity is DDD should be associated with only one context.

 
For microservice the modern implementation with DDD: 

![image](https://user-images.githubusercontent.com/73188710/168501450-e324359a-c70a-46b9-a2f5-68748391e26d.png)

* every entity should be associated with one context
* move away from relation database thinking
* bad to have single product-object in multiple contexts

microservices, warehouse and store, will be 2 completely different services with databases. 
Everything stays context specific.




























