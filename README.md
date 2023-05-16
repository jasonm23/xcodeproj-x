# XCodeproj Script Experiments


- [xcproj-extract](#xcproj-extract)
- [xcodeproj-add-ref](#xcodeproj-add-ref)

If you plan to use these, please ensure all project changes committed to git, so you can do a clean reset on the changes it performs in event of an error.

# Install

Clone this repo and symlink scripts in `./bin` to somewhere in your `$PATH`.
They use the Ruby gem https://github.com/CocoaPods/Xcodeproj/ you will need to
install Ruby and the gem yourself.

As the project is experimental it is not polished to a user friendly state, but you are encouraged to use the ideas and build cool tools with them.  I honestly can't believe this isn't something XCode just does anyway, so hopefully that'll happen.

# Scripts

## xcproj-extract

Bash script to extract `class`, `struct`, `enum`, `protocol`, `extension` from a file and create new files for each. 

The files are then added to the `${project_name}.xcodeproject` and build target, so the project will compile immediately with no additional manual steps.

### Usage

```shell
Usage: 

xcproj-extract <project_name> <swift_file>
```
`<project_name>` will be used for:
        
- Location of: `<project_name>`.xcodeproj
- Source Group: `<project_name>`
- Build Target: `<project_name>`

The file will be shown in `fzf` and you must select the start and end line of
each code <a title="Any code block that defines a class, struct, enum, protocol
or extension">definition</a> you want to extract. You may extract any that are
in the file at once. If the definition is at the beginning or end of the file,
you must still select the start and end of it. The script will exit early if it
does not get an even number of lines selected.

<kbd>TAB</kbd> is used to select/de-select a line, and <kbd>Enter</kbd> is used
to confirm your selections, <kbd>Esc</kbd> quits.  Default fzf keyboard bindings
are used.  

`xcproj-extract` uses `xcodeproj-add-ref` so it will need to find its location in your `$PATH`

## xcodeproj-add-ref

Add file(s) to a XCode project, they will be added to a source group and target/build
phase. The source group is also sorted.
    
### Usage

``` shell
Usage: 

xcodeproj-add-ref <project name> <files> [files...]
```
`<project_name>` will be used for:
        
- Location of: `<project_name>`.xcodeproj
- Source Group: `<project_name>`
- Build Target: `<project_name>`

# License

Licensed under GPL.
