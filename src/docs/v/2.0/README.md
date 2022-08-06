---
title: "Version 2.0"
---

# 🍁 Sugar Maple

![Latest Stable Version](https://poser.pugx.org/leafs/cli/v/stable)
![Total Downloads](https://poser.pugx.org/leafs/cli/downloads)

Leaf CLI v2 (Sugar Maple) builds on the functionality provided by the earlier version. It comes with faster load times, full scaffolds, bug fixes and a ton of other powerful functionality. You can now work with presets, scaffold projects using both v2 and v3 of leaf.

Unlike leaf CLI v1, v2 supports all leaf scaffolds: leaf, leaf mvc, leaf api and skeleton. It also uses in-built scaffolds instead of zip files packaged on leaf downloads coupled with composer downloads which make Leaf CLI 2 faster and even more reliable.

::: tip What's new?
To find out what's new, you can [read the changelog](https://github.com/leafsphp/cli/releases/latest)
:::

## Installation

You can quickly install Leaf CLI using composer. Simply run:

```sh
composer global require leafs/cli
```

You may have to add your composer bin directory to your system paths to use the `leaf` command from everywhere. Full steps to do that can be found on the [installation page](/docs/#installation).

## Upgrading from v1

You can upgrade from v1 by simply running the [installation script](/docs/#installation).

Version 2 of Leaf CLI has auto upgrades which means that it will keep itself up to date.

## Creating a leaf app

::: info Video Docs
You can take a look at our leaf cli video on youtube.

<VideoLesson href="https://www.youtube.com/watch?v=PuOk5xqTIsA" title="Install leaf PHP">Learn how to generate leaf apps with the create command</VideoLesson>
:::

To start a new project, simply open up your console or terminal and move into the directory you want to generate your project. From there, you can use the `create` command:

```bash
leaf create <project-name>
```

with leaf 3:

```sh
leaf create <project-name> --v3
```

or with leaf 2:

```sh
leaf create <project-name> --v2
```

This will now prompt you to select a preset <Badge text="New in v2" />

```sh
Creating a new Leaf app "<project-name>" in ./projects-directory.

* Please pick a preset 
  [0] leaf
  [1] leaf mvc
  [2] leaf api
  [3] skeleton
 > 
```

::: tip
Note that you are to select a number, not type the name of the preset.
:::

Selecting a number will generate a leaf app based on the associated preset. As you can see, there are 4 presets:

- **Leaf**: a bare leaf project
- **Leaf MVC**: a leaf MVC project with leaf 2
- **Leaf API**: a leaf API project with leaf 2
- **Skeleton**: a leaf skeleton project

After picking a preset, if no version was specified, leaf will display an interactive version picker like the one above:

```sh
* Select a version to use 
  [0] v3
  [1] v2
 >
```

your project will be automatically generated and initialized. All you need to do is open it up and start coding 🚀

### Adding Tests <Badge text="New in v2.3" />

From Leaf CLI v2.3, you will be asked if you want to add tests to your project. You can add tests by replying `y`.

```sh
* Add testing with Leaf Alchemy? [y, n] y

 - Adding alchemy for tests
```

### Quick presets

Leaf CLI also provides a quicker way to initialize your project without having to go through the interactive installer. You can use the `--mvc`, `--api`, `--basic` and `--skeleton` options to generate your project based on a specific presets. `--basic` generates a raw leaf project.

eg: `leaf create backend-api --api`

This will create a leaf api project named `backend-api`.

### Versioning

If no version is specified, leaf displays the interactive installer to you, however, to quickly install a particular version, you can use the `--v2` or `--v3` options. These can be coupled with presets as well.

Leaf API 3 example:

```sh
leaf create backend-api --api --v3
```

## Running your leaf apps

After generating your leaf app, you can `cd` into the directory and spin up a local dev server using leaf cli's `serve` command.

```sh
cd backend-api
leaf serve
```

You can also specify the port to run your leaf app on using the `--port` or `-p` options.

```sh
leaf serve -p 3000
```

### File watching <Badge text="New in v2.1.0" />

In v2.1, you can also start the leaf server with hot module watching. This reloads your application anytime a change is made to your application code. To get started, simply start the leaf server with the `--watch` flag.

```sh
leaf serve --port 8000 --watch
```

### Dependency Management <Badge text="New in v2.0.10" />

The serve command also now installs dependencies when there is no `vendor` folder present in the current working directory.

::: info Video Docs
You can take a look at our leaf cli video on youtube.

<VideoLesson href="https://www.youtube.com/watch?v=K9jSl_xpr48" title="Working with packages on the Leaf CLI">Working with packages and the leaf cli</VideoLesson>
:::

## Testing your Leaf apps <Badge text="new in 2.3.0" />

Testing helps prevent bugs in your app which you may not catch until you publish your app to production. Leaf introduced a test runner which helps you initialize testing and run tests in your app without needing any config first. Alchemy has also been integrated into the Leaf CLI and so you can use it's functionality directly.

### Setting up tests

Leaf CLI allows you to setup tests in your project with one command:

```sh
leaf test:setup
```

This command will generate Pest PHP tests for your application. If you however want to use PHPUnit, you'll need to pass the `--phpunit` option to the command.

```sh
leaf test:setup --phpunit
```

### Running tests

To run tests you've setup or created, you can simply run the `test` command.

```sh
leaf test
```

## Installing packages

This cli tool also adds a feature to install leaf packages from composer.

```bash
leaf install leafs/ui
```

If you are installing a leaf module or package, you can leave out the `leafs/` part.

```sh
leaf install ui
```

You can also pass in a bunch of packages to install at once.

```sh
leaf install ui db illuminate/support
```

***Versioning <Badge text="new in 2.0.5" />***

Leaf CLI also allows you to install a particular version of any package using `@`

```sh
leaf install ui@1.0 illuminate/support@9.0.2
```

***Package Chaining <Badge text="new in 2.0.5" />***

You can now add a bunch of packages to install as done with composer, npm and other CLIs as well.

```sh
leaf install db illuminate/support
```

Using this method, you can even add specific versions of some packages like this:

```sh
leaf install db illuminate/support@9.0.2 nesbot/carbon
```

## Interactive Shell

You can also use the interactive shell to interact with your app.

```bash
$ leaf interact
...
>>> $user = new User;
...
>>> $user->name = "Mychi";
...
>>> $user->save();
```

## Updating leaf cli

v2 contains an easy way to quickly update leaf cli to the latest version.

```bash
leaf update
```

## Running Scripts <Badge text="New in v2.0.9" />

Leaf CLI also now allows you run scripts defined in your `composer.json` file. For example, if you have this in your composer.json:

![image](https://user-images.githubusercontent.com/26604242/166419297-225b0b00-c979-4096-a23d-4f7858def8fb.png)

You can run the test script like this:

```sh
leaf run test
```

## Usage Guide

```sh

 _              __    ___ _    ___ 
| |   ___ __ _ / _|  / __| |  |_ v2.0.10
| |__/ -_) _` |  _| | (__| |__ | | 
|____\___\__,_|_|    \___|____|___|                       


Usage:
  command [options] [arguments]

Options:
  -h, --help            Display help for the given command. When no command is given display help for the list command
  -q, --quiet           Do not output any message
  -V, --version         Display this application version
      --ansi|--no-ansi  Force (or disable --no-ansi) ANSI output
  -n, --no-interaction  Do not ask any interactive question
  -v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

Available commands:
  completion  Dump the shell completion script
  create      Create a new Leaf PHP project
  help        Display help for a command
  install     Add a new package to your leaf app
  interact    Interact with your application
  list        List commands
  run         Run a script in your composer.json
  serve       Run your Leaf app
  uninstall   Uninstall a  package
  update      Update leaf cli to the latest version
```

This is the full list of commands available with Leaf CLI 2. A new update command has been added to allow you seamlessly update leaf CLI without having to run a bunch of commands. You don't even need to run this manually since leaf cli will automatically check for updates and upgrade to the latest stable release.
