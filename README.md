# XCodeproj Script Experiments

This repo holds experimental Ruby scripts that use the gem https://github.com/CocoaPods/Xcodeproj/

# WARNING

THESE SCRIPTS ARE EXPERIMENTAL.  NO WARRANTY / NO SUITABILITY OF PURPOSE GRANTED OR IMPLIED.

- - -

# installation

Ruby 3.2.0 or later required, clone the repo and use the script(s) in ‘./bin/`

Knowledge of git, Ruby, filesystems and XCode required to install these scripts, is
the requirement to use them.

### Ok, if you’re still here...

Basically, these scripts could blow up an XCode project. 

If you weren’t able to fix it up if things go sideways, despite all the
warnings, you’d be on your own. Issues will close without comment.

Good thing you know how to get yourself out of that sort of mess!

# Scripts

## `bin/xcodeproj-add-ref`

Add files to a XCode project and it’s main Target source build phase.

The ${name}.xcodeproj should follow a convention. Where the project, source
group and build target share the same name, e.g.

    ${name}.xcodeproj
    Build Target Name: ${name}
    Main Source Group/Folder: ${name}
    
### Usage

    Usage: xcodeproj-add-ref "<project name>" <files> [files...]
   
    <project name> This is expected to be:
      - project
      - source group (folder)
      - target name
   
    - <files> added to the source group and target source build phase
    - The source group is then sorted
    - The project is saved.

## `bin/...`

... TODO
