Problems to solve

- Vertical scrolling treeboard
- Each plan has multiple interfaces
  - Wizard
  - Card
- Relations between cards
  - natural child
  - adopted child
- Translate relationship card to formula in executable js
- Compile a js smartcontract onto the blockchain as a Merklelized Abstract Syntax Tree (mast) 
  - http://www.mit.edu/~jlrubin/public/pdfs/858report.pdf
- Blockchain sync Block/Header/Info/Transaction
- zSnarks (to make crypto anonymous)
- equihash for asic resistant mining
  - https://github.com/digitalbazaar/equihash
- Dynamically loading plugins 
  - https://myview.rahulnivi.net/dynamically-importing-modules-related-components-angular-45/



@cardstrip/core (cs interfaces and shared classes)

@cardstrip/api (cs backend)

@cardstrip/app (cs frontend)

@cardstrip/devkit (plugin)

@cardstrip/ioi (plugin)



@cardstrip/wallet (plugin)

@cardstrip/bip32 (hd wallets) http://bip32.org/



@cardstrip/ioi-cli (ioi command line interface)

@cardstrip/devkit-cli  (cs generator)



@cardstrip/cms

@cardstrip/crm

@cardstrip/accounts



#### How to make crypto anonymous

- **z**ero **k**nowledge
- **s**uccinct
- **n**oninteractive
- **ar**gument of **k**nowledge

##### What does this look like in JavaScript?

resources: 

- [github](https://github.com/ConsenSys/zero-knowledge-proofs)
- [Vitaliks blog](https://medium.com/@VitalikButerin/zk-snarks-under-the-hood-b33151a013f6)
- Another blog but with JavaScript examples can be found [here](https://media.consensys.net/introduction-to-zksnarks-with-examples-3283b554fc3b).



#### How to stop and remove all running docker containers?

```
$ docker stop $(docker ps -a -q)
$ docker rm $(docker ps -a -q)
```



#### How to merge two files like git?

You do it like [this](https://stackoverflow.com/questions/9122948/run-git-merge-algorithm-on-two-individual-files?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)



````bash
$ docker-compose logs -f -t
````



# Neo4j

resources:

- [Awesome neo4j](https://github.com/neueda/awesome-neo4j)

## How to go from datamodel to nodes with typescript?

## How to go from nodes to datamodel with typescript?

## How to effectively query nodes with typescript?

Resources:

- [Cypher Query Builder](https://www.npmjs.com/package/cypher-query-builder)



# Angular cli

````bash
ng config -g cli.packageManager yarn
````

resources:

- [blog on using cli 6+](https://blog.angularindepth.com/creating-a-library-in-angular-6-87799552e7e5)
- Testing angular with [jest](http://brianflove.com/2018/05/26/angular-jest-testing/)

# GitKraken

- [explorer shell association](https://superuser.com/questions/1078883/cannot-associate-program-with-context-menu-action?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)

# Open questions

- What is a mast (Merkelized Abstract Syntax Tree)
- What should a capability look like
	 	${space:name}.${capability:name}: {
	 	`keybindings`
	 	`ui:package`
    commands: [{
    	command: ${command:name},
    	title: ${command:title},
    	description: ${command:description},
    	`arguments`,
    	`${smartcontract:address}`
    }]
}

## One step is
- A step index number
- A step title
- A description consisting of:
    - One image, gif or video
    - 100 characters long, hash tagged piece of text
- A command
    - default value filed in and runnable by clicking
- result
    - one image, gif or video
    - 100 tagged chars piece of text



- How to presents [transalations ](https://electronjs.org/languages)





#### How to create a symbolic link in windows 

````bash
$ mklink /D "C:\Link To Folder" "C:\Users\Name\Original Folder"
````



### Example how to do sections

- https://form.io/#/

  

- [ ] setup private package registry (network)

- [ ] Setup specs for users

- [ ] Setup specs for cards

- [ ] configure package to push and pull from private registry (network)

- [ ] setup private image registry (network)

- [ ] configure ci to push and pull from private image registry (app, api, core)

- [ ] Wireup auth api to auth app (app)

- [ ] Setup graphql endpoint (api)

- [ ] Figure out express dynamic plugins like [this](https://www.express-gateway.io/getting-started/)

- [ ] Generate plugins from database (mah)

- [ ] Setup dos protection for express (api)




