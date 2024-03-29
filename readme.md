# Why LowlandTech?

## ***What problem is LowlandTech trying to solve?*** 

When dealing with service based products in general a potential buyer needs to contact the seller. Ascertain if the service in question can fulfill the customers expectation. If not how can the service be customized to deliver a satisfactory result? Then a contract should be drawn up, involving different agents only when all the i's are dotted and the t's are crossed the work in question can begin. Only upon delivery of the work in question invoices can be send and paid. Sometimes this process takes weeks, months or even years to conclude, bringing with it lots of uncertainty and doubt which is always translated into high costs. **LowlandTech is seeking to transform the way we work.**

## ***How to move from job security to income security?*** 
Digital transformation of work and the workplace is something that has been going on for awhile but the recent covid pandemic has seen it speed up. The increasing use of automation and robotization has started to disrupt jobs in all industries at all levels. Heavy regulation and taxation on labor will only seek to further accelerate the move to phase out human labor from the production process. Other technologies like blockchain will try to disintermediate transactional agents reducing the available jobs even further. Integrating and streamlining services into automated process will be the key involving skilled people in the new business model. In order to do that new technologies need to be developed that cannot be censored or regulated to favorite the current status quo. **LowlandTech wants to disrupt the job market.**

**Why peer to peer is the future of work** When Bram Cohen released bittorrent in the early 2000s it was in the middle of a war that the motion and music industry had unleased on downloaders. Instead of embracing the new technology they fought to maintain the status quo. And they eventually lost. Apple swooped in and disrupted the distribution model of film and music with it's iTunes.
Fast forward to 2010. Based on the same principle as bittorrent a revolutionary technology called Bitcoin was released. It broke the strangle hold governments had on the issuance of fiat money and indirectly on bank credit. Governments and bank tried to jail the early players by passing weak and ineffective rules and regulations. They tried to slow the influx of capital into Bitcoin with bureaucracy but it didn't work. The technology proved to be slow and imperfect to fully replace money or even bank credit but it did become a great store of value. Other blockchains like tether eventually ran off with the crown for payments and Ethereum with the crown of digital contracts.
When I saw Bitcoin for the first time, my exact thought was we now can get paid with digital money and totally bypass the slow and way to regulated job market and create online jobs which are mobile and go wherever you go. You wouldn't have to destroy the most valuable possession that a person has by sitting in traffic or commute between your job and your home. But fast forward another ten years, that hasn't happened. The switch to online jobs has not happened. **LowlandTech will create a jobs market online that totally disregards the rules of the jobs market.** This job market will ignore traditional diplomas and degrees and replace them with certified skills. LowlandTech will ignore work history and replace that with ratings for tasks completed. LowlandTech with do away with interviews completely by letting people pick an available task and let them try to complete it. If they manage it they can deliver to the task customer who will release the escrowed funds for that task to the task provider.

**How to create a company in 60 seconds?** LowlandTech an opensource multi-node blockchain with its own stable coin expressed in multiple supported currencies. The blockchain functionality can be accessed via its cli. The cli is equipped with a rest api which can be accessed by anything that has the ability to call a rest endpoint like: web, mobile and desktop applications.
The entire blockchain is centered to creating autonomous organizations, services and service providers and service customers. Each organization develops and maintains their services in a central or decentral way.

## How to create a organization

The following example creates a Dutch organization with the euro as its base currency.

````bash
$ repositories> llt organization create mis --description "My Incredible Startup" --locale nl-EN --currency EUR
$ repositories> cd mis
````
Any description entered for this organization will be assumed to be entered in nl-EN. An organization supports multiple locales as follows:

````bash
$ repositories> llt locale add nl-NL
````

This will create tasks to add a localized value for every description in the organization.

### Subscribing to service plans

The blockchain will look for a service that is tagged with accounting in the tax scheme nl in the language EN. It will look for something that cost 200 euro or less per month. If it finds more than one it will select and subscribe to the highest rated accounting service.

````bash
$ mis> llt plan add accounting --budget 200 --monthly
````

Lets add a few more services we need to run our business

````bash
$ mis> llt plan add tax-help-plan --budget 200 --monthly
$ mis> llt plan add office-space --budget 600 --monthly --workspaces 4
$ mis> llt plan add ms-office --monthly --licenses 4
$ mis> llt plan add desk-lease chair-lease --budget 75 --monthly --qty 4
$ mis> llt plan add wordpress-website --budget 20 --monthly --type freelance --domain my-startup.io
````

If we want to show our current projected costs per month we run:

````bash
$ mis> llt budget show --monthly                                                 
````

| code       | description                                              | budget    | period  |    
| ---------- | -------------------------------------------------------- | --------: | ------- |
| nl-ams-123 | I will consult on accounting and monitor your financials |       149 | monthly |
| nl-rot-165 | I will prepare your monthly and yearly taxes             |        99 | monthly |
| nl-ams-014 | I will provide with office space                         |       225 | monthly |
| us-rmd-500 | I will provide you with desktop tools for the office     |        60 | monthly |
| be-ant-245 | I will provide you with desks and chairs                 |       100 | monthly |
| uk-lon-222 | I will setup and maintain your wordpress websote         |        20 | monthly |
|            | subscribed to 6 monthly services                         |       653 | monthly |  
                                            
In the previous example we let LowlandTech look for the required services. We now are going to show the same process but then with our own preferred services.

````bash
$ mis> llt plan add copywriter --handle us-nyc-789 --budget 50 --hourly --contract 10
$ mis> llt plan add wordpress-expert --handle nl-utr-875 --budget 20 --hourly --contract 20
$ mis> llt plan add sales-person --handle uk-man-947 --budget 20 --hourly --contract 40
````

If we want to see our total budget with the updated services we can again type:

````bash
$ mis> llt budget show --monthly                                                  
````

| code       | description                                              | budget | period  |
| ---------- | -------------------------------------------------------- | -----: | ------- |
| nl-ams-123 | I will consult on accounting and monitor your financials |    149 | monthly |
| nl-rot-165 | I will prepare your monthly and yearly taxes             |     99 | monthly |
| nl-ams-014 | I will provide with office space                         |    225 | monthly |
| us-rmd-500 | I will provide you with desktop tools for the office     |     60 | monthly |
| be-ant-245 | I will provide you with desks and chairs                 |    100 | monthly |
| uk-lon-222 | I will setup and maintain your WordPress website         |     20 | monthly |
| us-nyc-789 | I will write some copy for your website                  |   2165 | monthly |
| nl-utr-875 | I will develop, configure your WordPress plugins         |   1732 | monthly |
| nl-utr-875 | I will find customers and sell your services             |   3464 | monthly |
|            | Subscribed to 9 monthly services                         |   8014 | monthly |

### Setup services for our organization

We need to create service providers first. Let's create two Wendell and Igor.

````bash
$ mis> llt provider create @wendellmva --budget 50 --hourly --hours 40 --shift 8,8,8,8,8 --start 0900 --pto 200
$ mis> llt provider create @igor_1981 --budget 50 --hourly --hours 40 --shift 8,8,8,8,8 --start 0900 --pto 200
````

All values given above are the default values so typing the short version would yield the same result.

````bash
$ mis> llt provider create @wendellmva --location almere
$ mis> llt provider create @igor_1981 --location eindhoven
````

If you want to know the default config values for a (function) group:

````bash
$ mis> llt config list --group provider
````

| config        | value     | description                       | group    |
| ------------- | --------- | --------------------------------- | -------- |
| budget        | 50        | default budget for a provider     | provider |
| scale         | hourly    | default scale for a provider      | provider |
| hours         | 40        | default available hours per week  | provider |
| shift         | 8,8,8,8,8 | default weekly work day pattern   | provider |
| start         | 0900      | default start time (time-zoned)   | provider |
| pto           | 200       | default hours for paid time off   | provider |

Changing a default configuration value:

````bash
$ mis> llt config update budget 50 --group provider
````

If you don't provide a group all config's named budget will be update. The default value only changes for newly to create providers. Changing the config settings does not affect the providers already created.

Now that we have our service providers lets create some services.

````bash
$ mis> llt service create "I will develop components" --price 75 --hourly --providers wendell,igor --tags "angular,vue,react,c#" --cover "https://cardstrip/images/components.jpg"

$ mis> llt service create "I will manage your project" --price 75 --hourly --providers igor --tags "angular,vue,react,c#,azure-devops" --cover "https://cardstrip/images/projects.jpg"

$ mis> llt service create "I will create your c# microservice" --price 75 --hourly --providers wendell --tags "c#,asp.net,docker,linux" --cover "https://cardstrip/images/microservices.jpg"
````

Now that we got our services lets have a look at the services dashboard

````bash
$ mis> llt budget show --monthly
````

| code       | description                                              | budget | period  |
| ---------- | -------------------------------------------------------- | -----: | ------- |
| nl-ams-123 | I will consult on accounting and monitor your financials |    149 | monthly |
| nl-rot-165 | I will prepare your monthly and yearly taxes             |     99 | monthly |
| nl-ams-014 | I will provide with office space                         |    225 | monthly |
| us-rmd-500 | I will provide you with desktop tools for the office     |     60 | monthly |
| be-ant-245 | I will provide you with desks and chairs                 |    100 | monthly |
| uk-lon-222 | I will setup and maintain your WordPress website         |     20 | monthly |
| us-nyc-789 | I will write some copy for your website                  |   2165 | monthly |
| nl-utr-875 | I will develop, configure your WordPress plugins         |   1732 | monthly |
| nl-utr-875 | I will find customers and sell your services             |   3464 | monthly |
| nl-alm-wen | @wendellmva as provider                                  |   8666 | monthly |
| nl-ehv-igo | @igor_1981 as provider                                   |   8666 | monthly |
|            | Subscribed to 11 monthly services                        |  24693 | monthly |
