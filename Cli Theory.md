# Command Line Interface Tool Theory

A command line interface is a tool first then whatever the author imagined it to be second. As a tool the cli or cli application gives the user certain capability. Many tools are poorly authored since the tool maker only sets out the accomplish a certain goal without putting much taught in how the tool will be used once it gets in the wild. Here are a set of rules to help the tool maker craft or recraft it into a masterpiece.

We are going to outline our theory with examples of imaginary tool called example tool, et for short.



## Rule 1: Everything starts with nothing

A cli is meant to transform state on a filesystem objects like files and folders. Files and folders start life always as nonexistent or empty. We should accept that the initial state always starts out that way no matter what. Empty is only a temporary or a transitional state so for this rule we disregard it and assume that before the tool does anything the state of the target object is nonexistent. So, if it's nonexistent we need to initialize it.



````bash
C:\\tool1 > $ et init
````



Initialization of what? I might hear you say? That first initial default state. The state that is convention for something. Something? I imagine you wonder. Let me clarify with an example.



````bash
C:\\tool1 > $ et init package

$ LOG CREATE: package.json

C:\\tool1 > $ et print package.json
{
    name: 'tool1'
}
````



Package is a scripted plan that et executes behind the scenes that consists of its own commands namely.

````bash
$ et create package.json > '{name: $folder}'
$ et format package.json
````

These commands have been hidden since we don't want to see the log of child scripts if we don't have to but if you need to you can change the command a bit to get the full picture.

````bash
C:\\tool1 > $ et init package --verbose

$ LOG INIT:PACKAGE:START: ['--verbose']
$ LOG CREATE: ${folder} / package.json
$ LOG APPEND: ${file} > '{name: $folder}'
$ LOG FORMAT:JSON: {
    name: 'tool1'
}
$ LOG INIT:PACKAGE:END 
````



