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

`Library` - all third-party frameworks and controls must be placed in this folder.<br />
`App/Classes/Controllers` - application view controllers.<br />
`App/Classes/Helpers` - application helpers, categories, singletons, configuration objects, etc.<br />
`App/Classes/Models` - model objects, Core Data models<br />
`App/Classes/Views` - Custom UIView's, UITableViewCell's, etc.<br />
`App/Images` - image files, all UI customization images must be stored in consequent folders, e.g. UITTabBar custom images must be stored in `App/Images/UITabBar` and so on.<br />
`App/Fonts` - bundled fonts.<br />
`App/HTML` - bundled HTML files.

## Project structure