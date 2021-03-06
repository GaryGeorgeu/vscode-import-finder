# Import Finder
Allows you to import a file by searching for it through the file finder.
Default hotkey: `ctrl+i`

## Features
- Calculates the relative path to the file
- Support for aliases

## Extension Settings
* `importFinder.importString`:
  - The template that should be used for the import. `$fileName` is replaced with a camel cased version of the file name. `$relativePath` is replaced with the relative path of the file.
  - Type: `string`
  - Default: `import $fileName from '$relativePath'`
* `importFinder.allowIndexFile`:
  - Decides whether or not to include the "index.js" file in the imported path.
  - Type: `boolean`
  - Default: `false`
* `importFinder.allowFileExtension`: 
  - Decides whether or not the file extension will be included in the imported path.
  - Type: boolean
  - Default: `false`
* `importFinder.aliases`:
  - Declares directory aliases to be used instead of the relative file path
  - Type: `Array<Alias>`,
    Alias: `{ 
      match: string,
      replace: string
    }`
  - Default: []
  - Example: If a value of `[{ match: '/components', replace: '@components' }]` was used, then the imported path would be `@components/my-component` instead of `../../components/my-component`
* `importFinder.include`:
  - Files to be included in results
  - Type: `string`
  - Default: `'**/*.{js,ts,jsx}'`
* `importFinder.ignore`:
  - Files and folders to be ignored
  - Type: `string`
  - Default: `'**/node_modules/**'`

## Installation
Download the [(vsix file)](https://github.com/GaryGeorgeu/vscode-import-finder/raw/master/import-finder-0.0.1.vsix). Use the overflow menu under extensions in vscode to select "Install from VSIX".

## Examples
- Importing a file from another folder
  - ![example1](https://github.com/GaryGeorgeu/vscode-import-finder/blob/master/examples/example1.gif)

- Importing index.js file with `[{ match: '/out', replace: '@out' }]` alias set.
  - ![example2](https://github.com/GaryGeorgeu/vscode-import-finder/blob/master/examples/example2.gif)
