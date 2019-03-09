

## NPM - Node Package Manager


**Definition** - NPM is the package manager for JAvaScript and the world's largest software registry. Discover packages of reusable code - and assemble them in powerwful new ways.


**Initialization** - To create package.json file, run command "npm init". Once executed, it will prompt for
some details such as name, version, description, main, test, git-repository, author, license. Most of the
details you can keep the default one except the "name" as this would be the name that are going to be published in the npm global repository.


**Adding Node Pacakges**

- Local : All the npm pacakge installed without "-g" command. These package would be only 
        available to the project it is installed in.
```
    npm install express
    Locally installed dependencies would be copied in <PROJECT_DIR>\node_modules\
```

- Globally : Any package that is installed GLOBALLY, it can be used in any PROJECT. To do that, the package should be installed with "-g" command.

```
    npm install -g express
    Globally installed dependencies would be copied in %AppData%\npm\npm-modules 
```

- Dev Dependency : Dependencies that are going to aid in development only. These dependencies will not
be shipped to the production. Example : babel dependency for ES06 polyfill. 

The dependency should be installed with "--save-dev". This flag would tell the npm to install mentioned dependencies as a dev-tools, 
they will not be included in your Production Build, but will be used throughout the Development.

```
    npm install babel-cli --save-dev

    npm install babel-cli babel-preset-stage-0 babel-preset-es2015 --save-dev

```
The spec in the preset’s name is not the target version, but the source version. 
For example, babel-preset-es2015 would compile ES6(es2015) to ES5 and 
babel-preset-es2016 would compile ES7(es2016) to ES6(es2015)



To **Install** specefic version of NPM, run "npm install <name>@version".
Example : npm install -g eslint@5.2.0

To check **Outdated** dependencies, run "npm outdated".
Example : npm outdated -g. This would returns the list of the npm modules which are outdated along with the
current installed and latest available version details.

    Package             Current  Wanted  Latest  Location
    @angular/cli          7.0.5   7.3.5   7.3.5
    eslint                5.2.0  5.15.1  5.15.1


To **Fix/Update** outdated node modules error, either you can do "npm update <package_name>" OR "npm install <package_name> -g". The later one is more preferable.


To **Remove/uninstall** any deprecated library or module, we can use "npm uninstall <package_name>.
Example : npm uninstall babel-preset-es2015


**Semantic Versioning**
Example : eslint@5.15.1
    - The first number is for MAJOR Releases
    - The second number represents MINOR Releases
    - The last one is for any PATCH Relases

"^" (CARET) - This Means All minor and patches are OKAY, but not major. For example ^4.5.5 means, any minor or patch update can be installed but not any 5.x.x version or above should be installed.
EXAMPLE : ^4.x.x --> Only version 4 would be installed

"~" (TILDE) - This is more restrictive then the above one. All patches only.
    For exampple, ~4.5.12, would only install if there is any patch release 12..13..etc, not even minor release. EXAMPLE : ~1.5.X --> Only PATCH releases would be installed.

To install specific dependencies, simple mention the exact dependeny version without any TILDE or CARET sign.



**package-lock.json** - We use package-lock to ensure a consistent install and compatible dependencies. This will ignore "^" sematic rule and will install exact version which is mentioned in package.json file. It describes the exact tree that was generated such that subsequent installs are able to generate identical trees, regardless of intermediate dependency updates.

Difference between pacakge.json and package-lock.json:

package-lock.json: records the exact version of each installed package which allows you to re-install them. Future installs will be able to build an identical dependency tree.

package.json: records the minimum version you app needs. If you update the versions of a particular package, the change is not going to be reflected here.