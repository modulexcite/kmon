Kestrelmon
==========

ASP.NET 5 wrapper for [nodemon](https://github.com/remy/nodemon). It will use nodemon to watch your source folder for changes and kill and restart your
web server whenever a change is detected. Main use is when making web apps without Visual Studio and it's design time host. 

## Add Kestrelmon to your web project: 

`kpm install Kestrelmon` to install from Nuget.org

Add a `mon` command to your project.json file: 

```
"commands": {
    /* Change the port number when you are self hosting this application */
    "web": "Microsoft.AspNet.Hosting --server Microsoft.AspNet.Server.WebListener --server.urls http://localhost:5000",
    "gen": "Microsoft.Framework.CodeGeneration",
    "ef": "EntityFramework.Commands",
    "mon" : "Kestrelmon --ext cs,json,js"
},
```
From the command line, run `k mon`. It's pronounced *"kuh-mon"*. 

You can call it something else than `mon`, but then you can't shout out "kuh-mon!" when you run it. 

Kestrelmon passes parameters on to nodemon so `--ext cs,json,js` are nodemon parameters telling it to watch files ending in 
one of those extensions.

## Known issues
This is the first release and a work in progress. Critical issues:
* Initial proof of concept only works on Windows and runs the web command. Need some work to run on Mono and run Kestrel. 
* Little or no error handling. 