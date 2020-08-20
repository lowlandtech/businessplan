# CardStrip Cli

## Composition commands

With cardstrip cli you can compose your application anyway you want. A feature or a recipe is a complete functionality piece of code on to itself which you can customize after having been add to the project workspace

$ cs add feature ngx-sidebar [options]

avaliable options

--as=code => (will use wget to download feature code as a module)
--as=submodule (will use git to add the feature code as a submodule in a module folder)
--as=tree (will use git to add the feature code as subtree in a module folder)

--as=package (will use yarn to add feature code as a package in node_modules folder



````$ cs add component card
$ cs apply --plan ng --to user --in somefolder --with jest,nodemon,webpack --save-script --show
````

Examples of recipes:

- @angular/cli
- @angular/nest
- @cardstrip/ngx