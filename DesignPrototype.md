This guide is written to get a small self contained  application/service/microservice from concrete ideas to implementaion.

### Things to keep in mind for designing and prototyping in a fast paced environment in order to determine viability of a tech stack

- Before working on the prototype a common set of functionalities should be established that cannot or will not change drastically in the future,
atleast an overall abstract use should be there even if specific requirements might not be there
e.g my application should be able to process x number of queries on a given size of data with a given amount of complexity for the data and queries, or
my application should be able perform x number of functions with some y additional features in future, basically we should have a definitive list of features the app can provide 
now and in the future with some level of flexiblity, more flexible the app needs to be the harder it will be to prototype and some alternate model of sdlc should be chosen for this app if flexibilty required is too high.
- Understanding whether you are doing application development or framework development(also called meta programming which is a time consuming process and requries a lot of planning and time so its really not possible to prototype it)
- Too much fixation on SOLID/DRY principles: since we are working outside any particular sdlc there might be little to no planning time, just focus on keeping the vital 
components of your architecture maintainable or better yet use an existing framework/collection of libraries which does it for you. As any non vital components/code/classes can be changed
 by even junior developers if it has limited functionality.
- If you have a fairly good amount of features, start with the most basic functionality that your application can providing quickly, then test it with various available technologies to test whether they will
fulfill your purpose, if you implement a lot of code without first ruling out tech stacks that can't fulfill your requirements it will be hard to change it down the line.
- Always give the most priority to non trivial features as trivial things can be easily changed later.
- Always make sure any testing work you do is reproducible with minimum effort when you are still deciding between various tech.

### Common strategies to rule out frameworks/libraries/dbs etc:
Depending on the problem you are solving you can easily rule out some of the tech stacks that you are planning to use, if you follow these steps cleverly you can 
straight out reject some tech without the need to implmenent it.
- Every language has its own merits and demerits being familiar with what various languages offer in terms of their pros and cons is essential.
- When chosing a framework figure out whether your use case is simple enough to not require a full blown framework as certains frameworks will limit you a lot in future based on their own philsophy, for small services chosing more flexible libraries with higher freedom of choices would be better than chosing more limiting frameworks
- make yourself familiar with what your chosen set of technologies can and cannot do in terms of your requirements especially the constraints of the given language/frameowrk/etc, this is the most important step will result in problems in the future.
- For small services it is totally acceptable to not with very feature rich but limiting frameworks or go with stripped down version of otherwise heavy frameworks

### Common good practices

- always try to use standard  functionality provided by your chosen languages of common functions such as logging, file io etc, never wrap them in your own functions as it will lead to developers who are used to 
using the standard tools a bit frustrating, there is almost never a need to create your own wrappers for standard functions in a language, In the initial phase you can even skip logging, commenting etc as things will change too quickly and updating and maintaining logs/comments etc will be additional overhead.
- for configuration of an app all variables which are not mandatory should have acceptable defaults and ideally an application should never even require any mandatory configuration, there should be valid defaults for everthing e.g we are using any external app/system/db to connect we can expect a default host and port for these external systems but still some configuration might not have any sensible defaults, this is especially true in the initial stage where you just expect everything to work without a lot of configuration.
- when writing code initially don't  start in terms of meangingful base classes for protoyping, only do it if you think the functionality will be used more than 2-3 places and defintely, don't try to abstract everything, remember when writing small services/prototypes it will be much easier to change the code later, your current focus should be on, whether your chosen tech stack is viable or not.
-  Always keep in mind any issues that need to be resolved in future or better write them down either in code using TODO comments or use something like github/gitlab issues or confluence or something else, you will always find something like this based on what languages/frameworks you decide to go with e.g for python it might be optimzing certains parts of code in future or for go 
keeping in mind the async nature of code and how it affects e.g your connection limits with db/external systems.

Once you have a basic set of features working you can determine which tech stacks you are willing to go ahead with, in some cases it will be quite clear either due to 
lack of choices or by your findings while prototyping but in some cases this step might take a lot of discussion and trials to decide, if your are not familiar with the chosen technologies it 
might be beneficial to consult somone who has expertise in the said tech, no guess work should go into deciding the tech stack. This will require a deep understaing of both the 
uses cases and tech so this step should probably include everyone that can provide a useful input and not just few people.

### From prototype to a working application

- Once you have decided the tech stack, clean up your code and start adding practical code structure, first only do this for core features, in the course of further development
you may find bugs keep fixing them and if possible write unit tests for any code that you have written(don't write tests for framework/library/language builtins as they are already tested).
- Make the code consistent across the code base.
- Do these for a few small iterations of 1-2 days until your core features become stable.
- Now just keep adding more features in small iterations.
 






