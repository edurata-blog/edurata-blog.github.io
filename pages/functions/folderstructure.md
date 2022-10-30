## Folder structure

Note that in the following the `root` folder can also be a subfolder in a repository and doesn't have to 
You have freedom about how to structure your files except the following:
- **The root contains an index.ts**: This is the entrypoint of the function and contains the handler function.
- **The root contains a package.json**: In order for us to know which dependencies to install you need to provide a `package.json` in the root directory.
- **The root contains an interface.d.ts**: Since we need information about the signature/interface of your function you need to provide this file that contains only typescript types.