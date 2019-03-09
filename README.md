

## NPM - Node Package Manager


**Definition** - NPM is the package manager for JAvaScript and the world's largest software registry. Discover packages of reusable code - and assemble them in powerwful new ways.


**Initialization** - To create package.json file, run command "npm init". Once executed, it will prompt for
some details such as name, version, description, main, test, git-repository, author, license. Most of the
details you can keep the default one except the "name" as this would be the name that are going to be published in the npm global repository.


**Adding Node Pacakges**

    - Local : All the npm pacakge installed without "-g" command. These package would be only 
              available to the project it is installed in.

    npm install express
    Locally installed dependencies would be copied in <PROJECT_DIR>\node_modules\

    - Globally : Any package that is installed GLOBALLY, it can be used in any PROJECT. To do that, the package should be installed with "-g" command.

    npm install -g express
    Globally installed dependencies would be copied in %AppData%\npm\npm-modules 

     - Dev Dependency : Dependencies that are going to aid in development only. These dependencies will not
     be shipped to the production. Example : babel dependency for ES06 polyfill. 

    The dependency should be installed with "--save-dev". This flag would tell the npm to install mentioned dependencies as a dev-tools, they will not be included in your Production Build, but will be used throughout the Development.

     npm install babel-cli --save-dev

    npm install babel-cli babel-preset-stage-0 babel-preset-es2015 --save-dev
    The spec in the preset’s name is not the target version, but the source version. For example, babel-preset-es2015 would compile ES6(es2015) to ES5 and babel-preset-es2016 would compile ES7(es2016) to ES6(es2015)

