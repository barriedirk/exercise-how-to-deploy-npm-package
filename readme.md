```shell
$ npx tsc --init
```


note: files indicate the files that should be sent to npm


{
  "name": "dthm-exercise-tiny-npm-deploy",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "files": [
    "dist"
  ],



  "publishConfig": {
    "access": "public"
  },
  "bin": "dist/index.js",

add prepublishOnly

  "scripts": {
    "build": "tsc",
    "prepublishOnly": "npm run build"
  },



  The line #!/usr/bin/env node is called a shebang (or hashbang) and is used in scripts to indicate the path of the interpreter that should be used to run the file.

Here's a breakdown of what each part does:

#!: This is the shebang syntax. It tells the operating system that the file should be executed by an interpreter specified in the path that follows it.
/usr/bin/env: This is the path to the env command, which is used to find and run other programs. It's a more flexible way of specifying the interpreter, as it looks for node in the system's environment variable PATH, allowing the script to be run on different systems where the location of Node.js may vary.
node: This specifies that the script should be run using Node.js. It tells the system to execute the file using the Node.js runtime.
Why is this used?
This shebang allows you to run the TypeScript (or JavaScript) file as an executable script directly from the command line, without needing to explicitly type node before the filename. For example:

Without the shebang, you'd need to run:

bash
Copy
node script.ts
With the shebang (#!/usr/bin/env node), you can make the file executable and run it directly:

bash
Copy
./script.ts
For this to work, you'd typically need to give the file executable permissions (e.g., using chmod +x script.ts on Unix-based systems).

In summary:
The shebang tells the operating system how to run the file.
Using /usr/bin/env node ensures that the script is executed using the correct version of Node.js, regardless of where it's installed on the system.
It’s common in Node.js scripts and can be helpful when distributing scripts that need to be run on different environments.




