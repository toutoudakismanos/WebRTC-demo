##### JavaScript

---------

A. How node works
  1.  Node is non-blocking Asynchronous ,single thread ,  Asp.net  : blocking synchronous.
  2. node is for I/O intensive apps. not for CPU-intensive apps.
  3. Node is c++ program that use chrome V8 javascript engine

-----------

B.  First node program
 1.  " node -- version "  : check current version 
 2.  " mkdir first-app "  : make new directory 
 3.  " cd first-app "        : goto first-app folder
 4.  " code . "                 : open visual studio code
 5.  " node app.js "       : to run app.js


 C. Global Object
 1. In Javascript we have " window " object but in node we don't have " window " object
 2. Instead we have " global " in node.js. eg : global.console.log(1+12);

D. Modules
 1. In node every file is module and the variables and functions defined in that file are scoped to that module.
 2. " module.exports.endName = userName " // exports userName as        endName can be accessed as 
        const name = require( " ./ fileName")
        console.log(name.endName);
 3. " module.exports  = mySum "  // export mySum function 
      eg:  const  sum = require('./fileName.js')
              console.log( sum(1,2) ) ; 
 4.  variables and functions defined in the module are scoped to that module they're private and not visible from outside.
 5.  At runtime node wraps code in following function 
      ( function ( exports , require , __filename,  __dirname ) {
              our code .... ;
      }) 
    we call this function as Module wrapper function
 
E.  Exploring Build in modules ( path module ) 

1. Path module
 const path = require("path")
 const pathObj = path.parse(__filename)
 console.log(pathObj)
-------
 Output : 
{
  root: '/',
  dir: '/home/runner/SlateblueAgitatedPresses',
  base: 'index.js',
  ext: '.js',
  name: 'index'
}
------
2. Os module 
const os = require("os")
console.log(os.freemem())
console.log(os.totalmem())
console.log(os.version())
console.log(os.type())
console.log(os.cpus())



F. File System module 
 
1. const fs = require ( 'fs) 
  console.log(fs.readdirSync('./')) // sync method
  fs.readdir('./',(err,fd)=>{     // asynchronous method
    if(err) console.log(err)
    else console.log(fd)
  })

G. Events Module 
1. 
    const EventEmmiter = require('events');
    const emmiter = new EventEmmiter();

     // can use "on" instead of "addListener"
     emmiter.addListener("myEmmiter",( args)=>{
    console.log("called", args)
   })
ennuter.emit( " myEmmiter"  , {id: 1 , url : ' http:// " } );