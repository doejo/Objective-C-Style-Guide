# __APP_NAME__

This is a source code of __APP_NAME__ iPhone app. It can be compiled with Xcode 4.4+ and it uses ARC.

## Installation

New install:

```Bash
git clone __GIT__URL__
cd appfolder-ios
rake install
```

To update existing installation:

```Bash
rake update
```

## Submodules

Use submodules to install third-party components, for example:

`
git add submodule __git_url__ Library/ComponentName
`

## Folder structure

`Library` - all third-party frameworks and controls must be placed in this folder.
`App/Classes/Controllers` - application controllers
`App/Classes/Helpers` - application helpers, categories, singletons, configuration objects, etc.
`App/Classes/Models` - model objects, Core Data models
`App/Classes/Views` - Custom UIView's, UITableViewCell's, etc.