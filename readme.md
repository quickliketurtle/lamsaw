# Lamsaw

Super-powered setup script for Jigsaw and Valet.

## Installation

```bash
composer global require quickliketurtle/lamsaw
```

## Upgrading

```bash
composer global update quickliketurtle/lamsaw
```

## Usage

Make sure `~/.composer/vendor/bin` is in your terminal's path.

```bash
cd ~/Sites
lamsaw superApplication
```

This will create a new directory, change into that directory, composer require Jigsaw, make an initial Git commit, and open your web browser to that app.

### What exactly does it do?

- `mkdir $PROJECTNAME`
- `cd $PROJECTNAME`
- composer require tightenco/lambo
- Initialize Jigsaw
- Install node dependencies
- Build local Jigsaw site
- Initialize a git repo, add all of the files, and make a commit with the text "Initial commit."
- Open `$PROJECTNAME.$YOURVALETTLD` in your browser

There are also a few optional behaviors based on the parameters you pass (or define in your config file).

### Optional Arguments

- `-h` or `--help` to get the help dialog

  ```bash
  lamsaw --help
  ```

### Commands

- `make-config` creates a config file so you don't have to pass the parameters every time you use Lambo

  ```bash
  lamsaw make-config
  ```

### Config

You can create a config file at `~/.lamsaw/config` rather than pass the same arguments each time you create a new project.

```bash
lamsaw make-config
```

### After File

You can create an after file at `~/.lamsaw/after` to run additional commands after you create a new project.

```bash
lamsaw make-after
```

The after file is a bash script so you can include any commands here such as installing additional composer dependencies

```bash
# Install additional composer dependencies as you would from the command line.
echo "Installing Composer Dependencies"
composer require tightenco/mailthief tightenco/quicksand
```

or copying additional files to your new project.

```bash
# To copy standard files to new lambo project place them in ~/.lambo/includes directory.
echo "Copying Include Files"
cp -R ~/.lambo/includes/ $PROJECTPATH
```

You also have access to variables from your config file such as `$PROJECTPATH` and `$CODEEDITOR`.

## Requirements

- Mac or Ubuntu.
- Requires [Laravel Valet](https://laravel.com/docs/valet) to be globally installed.

> An Ubuntu fork of Valet can be find [here](https://github.com/cpriego/valet-ubuntu)

## Acknowledgements

Inspired by tightenco/lambo which is Inspired by Taylor Otwell and Adam Wathan's work on Valet.

Name inspired by Lambo's Name from TJ Miller, inspired by Taylor's love for the lambo.

![](https://i.imgur.com/CrS803Y.gif)
