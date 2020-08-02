# CardStrip in 60 seconds

CardStrip a multinode blockchain with its own currency cs coin. You can access the blockchain via its cli. The cli is equipped with a rest api which can talk to any kind of ui: web, mobile, desktop.


The entire blockchain is centered to creating autonomous organizations, services and service providers and service customers. Each organizationsa develops and maintains their services in a central or decentral way.

## How to create a organization

The following example creates a dutch organization with the euro as its base currency.

````bash
$> cardstrip organization create "My Incredible Startup" --handle mis --directory mis --locale nl-EN --currency EUR
$> cd mis
````

### Subscribing to service plans

The blockchain will look for a service that is tagged with accounting in the tax scheme nl in the language en. It will look for something that cost 200 euro or less per month. If it finds more than one it will select and subcribe to the highest rated accounting service.

````bash
$mis> cardstrip plan add accounting --budget 200 --monthly
````

Lets add a few more services we need to run our business

````bash
$mis> cardstrip plan add tax-help-plan --budget 200 --monthly
$mis> cardstrip plan add office-space --budget 600 --monthly --workspaces 4
$mis> cardstrip plan add ms-office --monthly --licenses 4
$mis> cardstrip plan add desk-lease chair-lease --budget 75 --monthly --qty 4
$mis> cardstrip plan add wordpress-website --budget 20 --monthly --type freelance --domain my-startup.io
````

If we want to show our current projected costs per month we run:

````bash
$mis> cardstrip budget show --monthly

handle     description                                              budget    period      
---------- -------------------------------------------------------- --------- -------
nl-ams-123 I will consult on accounting and monitor your financials       149 monthly 
nl-rot-165 I will prepare your monthly and yearly taxes                    99 monthly
nl-ams-014 I will provide with office space                               225 monthly
us-rmd-500 I will provide you with desktop tools for the office            60 monthly
be-ant-245 I will provide you with desks and chairs                       100 monthly
uk-lon-222 I will setup and maintain your wordpress websote                20 monthly
-------------------------------------------------------------------------------------
subscribed to 6 monthly services                                          653 monthly                                                   
````

In the previous example we let cardstrip look for the required services. We now are going to show the same proces but then with our own prefered services.

````bash
$mis> cardstrip plan add copywriter --handle us-nyc-789 --budget 50 --hourly --contract 10
$mis> cardstrip plan add wordpress-expert --handle nl-utr-875 --budget 20 --hourly --contract 20
$mis> cardstrip plan add sales-person --handle uk-man-947 --budget 20 --hourly --contract 40

$mis> cardstrip budget show --monthly

handle     description                                              budget    period      
---------- -------------------------------------------------------- --------- -------
nl-ams-123 I will consult on accounting and monitor your financials       149 monthly 
nl-rot-165 I will prepare your monthly and yearly taxes                    99 monthly
nl-ams-014 I will provide with office space                               225 monthly
us-rmd-500 I will provide you with desktop tools for the office            60 monthly
be-ant-245 I will provide you with desks and chairs                       100 monthly
uk-lon-222 I will setup and maintain your wordpress websitte               20 monthly
us-nyc-789 I will write some copy for your website                       2165 monthly
nl-utr-875 I will develop, configure your wordpress plugins              1732 monthly
nl-utr-875 I will find customers and sell your services                  3464 monthly
-------------------------------------------------------------------------------------
subscribed to 9 monthly services                                         8014 monthly                                                   
````

### Setup services for our organization

We need to create serice providers first. Let's create two Wendell and Igor.

````bash
$mis> cardstrip provider add wendell --handle @wendellmva --budget 50 --hourly --weekly-availability 40 --shift 8,8,8,8,8 --rotation 9pm-5am --pto 2000
$mis> cardstrip provider add igor --handle @igor_1981 --budget 50 --hourly --weekly-availability 40 --shift 8,8,8,8,8 --rotation 9pm-5am --pto 200
````
Now that we have our service providers lets create some services.

````bash
$mis> cardstrip service create "I will develop components" --price 75 --hourly --providers wendell,igor --tags "angular,vue,react,c#" --cover "https://cardstrip/images/components.jpg"

$mis> cardstrip service create "I will manage your project" --price 75 --hourly --providers igor --tags "angular,vue,react,c#" --cover "https://cardstrip/images/projects.jpg"

$mis> cardstrip service create "I will create your c# microservice" --price 75 --hourly --providers wendell --tags "c#,asp.net,docker,linux"

````