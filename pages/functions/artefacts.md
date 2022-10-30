## Handling of Files (Artefacts)

If you want to make use of the filesystem to create or read from files you have to place them under the `/tmp/` directory. 

If you want to use file/files as input or output of your function you use the `Artefact` type or any of its subtypes provided by the [@edurata/types](https://www.npmjs.com/package/@edurata/types) package in the interface. The function wrapper will automatically handle uploading/downloading the file from cloud storage. 

In order to specify an artefact you either pass in an object of type File or a shorthand string that includes all information about the file.

```typescript
type Path = string // e.g. /path/to/file/
type FileName = string // e.g. foo
type FileType = string // e.g. txt

export type File = {
    path: Path 
    fileName: FileName
    fileType: FileType
}

type FileStr = `file:${Path}/${FileName}.${FileType}`

export type Artefact = File | FileStr

```
