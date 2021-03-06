# Ng2Sample
This repository holds a Visual Studio 2015, Asp.net Core version of the TypeScript source code of the 
[angular.io quickstart](https://angular.io/docs/ts/latest/quickstart.html),the foundation for most of
the Angular 2 documentation samples and potentially a good starting point for your application. This is 
basically a update of this [Typescript Asp.net Core tutorial](http://www.typescriptlang.org/docs/handbook/asp-net-core.html)
to use the most recent libraries and quickstart code.

## Create a new project based on this QuickStart Template

Clone this repo into new project folder (e.g., `my-proj`).

## Install npm packages

Install the npm packages described in the `package.json`. Normally this is done for you by visual studio
when you open the solution. But visual studio NPM tool has a difficult time resolving the packages and so the
initial install needs to be done from the command line in the 'src\Ng2Sample' folder. 

Note: The folder path length can become an issue with some of the nested modules, this issue has been addressed in
the newer version of NPM. I would recommend using this [tool](https://github.com/felixrieseberg/npm-windows-upgrade) to
upgrade to a version of NPM > 3.0.

```bash
npm install
```
### Gulp Scripts

These scripts are the basic scripts described in the Typescript Asp.net Core tutorial [here](http://www.typescriptlang.org/docs/handbook/asp-net-core.html). For completeness I modified the script to move most of the angular 2 node_modules into the scripts/lib directory, this allows for you to work with the Angular 2 documentation samples. Also I added a seperate folder for styles, all of these files are moved in a post build event. In order to have these gulp tasks start subscribing to these build events you may need to right click on the 'gulpfile.js' and open the Task Runner Explorer. I have also added a webserver task that will start a simple http server on port 8000 in the wwwroot directory with a browserlink websocket that causes the browser to refresh when there are changes. Simply start the webserver task them as you make changes and save run the default task to move the changes into the wwwroot directory which causes a refresh. This is a great method for doing rapid development and not having to wait for kestrel to start.

### Usage

After installing the npm packages and verifying gulp tasks are attached, open the .sln file in Visual Studio 2015 with the latest version of the Typscript tools for Visual Studio (at the time of this writing it is version 2.0.3). Next just build the application and use the web command to launch kestrel and navigate to http://localhost:5000.

Enjoy!

### Dependencies
* Visual Studio 2015 update 2
* DNX SDK version 1.0.0-rc1-update1
* Typescript for Visual Studio version 2.0.3
* Node version 6.2.0
* NPM version 4.0.0 (optional, but recommended)
