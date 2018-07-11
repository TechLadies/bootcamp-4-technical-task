# Setup Guide

To participate in the TechLadies prebootcamp workshops, and in the actual bootcamp itself, we expect you to have your machines set up for development. This guide will walk you through installing the necessary software and dependencies to get started. The instructions will differ depending on the operating system you're on.

<!-- vim-markdown-toc GFM -->

* [UN*X systems (macOS/Linux)](#unx-systems-macoslinux)
  * [Your text editor](#your-text-editor)
  * [The command-line/terminal](#the-command-lineterminal)
  * [Xcode Command Line Tools (macOS only)](#xcode-command-line-tools-macos-only)
  * [Homebrew (macOS only)](#homebrew-macos-only)
  * [Git](#git)
    * [macOS](#macos)
    * [Ubuntu/Debian](#ubuntudebian)
  * [NodeJS and npm](#nodejs-and-npm)
    * [Installing the asdf version manager](#installing-the-asdf-version-manager)
    * [Install NodeJS through asdf](#install-nodejs-through-asdf)

* [Windows Systems](#windows-systems)
  * [Chocolatey (windows only)](#chocolatey-windows-only)
  * [Git for Windows](#git-for-windows)

* [That's all folks!](#thats-all-folks)
<!-- vim-markdown-toc -->

## UN*X systems (macOS/Linux)
### Your text editor

We will be using Visual Studio Code as our text editor. Download and install it from [here](https://code.visualstudio.com/Docs/setup/setup-overview).

### The command-line/terminal

As a developer, you'll have to get comfortable with using the command-line, also called the terminal. That's the little black box you type cryptic commands into to do magical stuff. Well, it won't be quite so magical after you get used to doing it. To open up your terminal, search for Terminal in your applications (whether your're on macOS or a Linux distro, standard installations should include a default terminal emulator).

As a sanity check, type the following into the terminal:

```bash
echo "Hello world!"
```

You should see `Hello world!` output on the next line. See, using the command-line ain't that hard :)

### Xcode Command Line Tools (macOS only)

If you are on macOS, please follow this [guide](https://www.maketecheasier.com/install-command-line-tools-without-xcode/) to install the Xcode Command Line Tools. You will need this to install other software in the later steps. Do note that at the step when you see this prompt:

![xcode-install-prompt](https://www.maketecheasier.com/assets/uploads/2016/05/cmdtools-install.png)

Make sure that you click **Install** and **NOT** 'Get Xcode' or you will end up installing the whole Xcode IDE, which will take quite awhile.

### Homebrew (macOS only)

If you are on macOS, please install the [Homebrew package manager](https://brew.sh/). This allows you to easily install software through your command-line (you must already have Xcode Command Line Tools installed). Open your Terminal and paste the following in:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Once Homebrew is installed, you should get access to the `brew` command. Open a new Terminal window, and type:
```bash
brew
```

You should see output something like this:
```
Example usage:
  brew search [TEXT|/REGEX/]
  brew info [FORMULA...]
  brew install FORMULA...
  brew update
  brew upgrade [FORMULA...]
  brew uninstall FORMULA...
  brew list [FORMULA...]

Troubleshooting:
  brew config
  brew doctor
  brew install --verbose --debug FORMULA

Contributing:
  brew create [URL [--no-fetch]]
  brew edit [FORMULA...]

Further help:
  brew commands
  brew help [COMMAND]
  man brew
  https://docs.brew.sh
```

Congrats, you've got brew up and running!

(NOTE: If you're on Linux, not macOS, your system should already come with a package manager installed, that's why you can safely skip this section. Examples for some popular distros: Debian and Ubuntu systems should have apt (Advanced Packaging Tool), while Fedora and CentOS systems should have yum (Yellow Dog Updater, Modified).)

### Git

We will be using git as a tool for version control. You can (and are encouraged to!) read more about [version control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) and [git](https://git-scm.com/). For now, we're just interested in setting it up on your system. Depending on your system you may already have a default git installed. You can try it out by opening your Terminal and typing:

```bash
git --version
```

If it complains with a line like "command not found" then git has not yet been installed. Otherwise it will print out the version of git you have installed. Even if you already have git installed, it's best to upgrade it to the latest version anyway.

#### macOS
On macOS, open your Terminal and do the following:

1. Update Homebrew and installed packages
```
brew update && brew upgrade
```

2. Install git with Homebrew
```
brew install git
```

3. Link your git executable to the one you just installed
```
brew link --force git
```

4. Close and re-open your Terminal, then check your git version
```
git --version
```

It should output the latest version of git you just installed.

#### Ubuntu/Debian
If you're on a Ubuntu or Debian system, open your Terminal and do the following:

1. Add the git PPA (personal package archive) to get the latest git version (you will need to key in your password)
```bash
sudo add-apt-repository ppa:git-core/ppa
```
1. Update your package repositories:
```bash
sudo apt-get update
```
2. Install git
```bash
sudo apt-get install git
```
3. Check your installation
```bash
git --version
```

It should output the latest version of git you just installed.

### NodeJS and npm

You will need NodeJS and npm (node package manager) installed to develop JavaScript projects.

#### Installing the asdf version manager
Install NodeJS through the [asdf](https://github.com/asdf-vm/asdf) version manager. (Installing NodeJS will install npm along with it). Please read through the asdf project page linked to above. It provides the instructions required to setup asdf. Do the following (you should already have git installed):

1. Open your command-line/terminal (search for Terminal in your applications)
2. Paste the following (clones the asdf project code onto your machine):
```bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.5.0
```
3. And the following (sets up configuration for asdf in your terminal):
```
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bash_profile
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bash_profile
```
4. Close and re-open your Terminal and type:
```bash
asdf
```

If asdf was successfully installed, you should see something like:
```
version: v0.5.0

MANAGE PLUGINS
  asdf plugin-add <name> [<git-url>]   Add a plugin from the plugin repo OR, add a Git repo
                                       as a plugin by specifying the name and repo url
  asdf plugin-list                     List installed plugins
  asdf plugin-list --urls              List installed plugins with repository URLs
  asdf plugin-list-all                 List plugins registered on asdf-plugins repository with URLs
  asdf plugin-remove <name>            Remove plugin and package versions
  asdf plugin-update <name>            Update plugin
  asdf plugin-update --all             Update all plugins


MANAGE PACKAGES
  asdf install <name> <version>        Install a specific version of a package or,
                                       with no arguments, install all the package
                                       versions listed in the .tool-versions file
  asdf uninstall <name> <version>      Remove a specific version of a package
  asdf current                         Display current version set or being used for all packages
  asdf current <name>                  Display current version set or being used for package
  asdf where <name> <version>          Display install path for an installed version
  asdf which <name>                    Display install path for current version
  asdf local <name> <version>          Set the package local version
  asdf global <name> <version>         Set the package global version
  asdf list <name>                     List installed versions of a package
  asdf list-all <name>                 List all versions of a package


UTILS
  asdf reshim <name> <version>         Recreate shims for version of a package
  asdf update                          Update asdf to the latest stable release
  asdf update --head                   Update asdf to the latest on the master branch


"Late but latest"
-- Rajinikanth
```

#### Install NodeJS through asdf
First you need to install the [nodejs plugin for asdf](https://github.com/asdf-vm/asdf-nodejs).

If you are on macOS, please install the following dependencies through Homebrew (open your Terminal):
1. GNU Coreutils
```bash
brew install coreutils
```
2. GnuGPG
```bash
brew install gpg
```

Then install the plugin:
```bash
asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git
```
And import the Node.js release team's OpenPGP keys to main keyring:
```bash
bash ~/.asdf/plugins/nodejs/bin/import-release-team-keyring
```

Now you need to install a specific NodeJS version. I recommend installing the latest LTS (long-term support) version, which is 8.11.3:
```bash
asdf install nodejs 8.11.3
```

Then set your node version:
```bash
asdf global nodejs 8.11.3
```

If you've successfully installed NodeJS through asdf, you should be able to do:
```bash
node --version
```
which should output `v8.11.3`

And if you run
```bash
node
```
you will get an interactive prompt where you can try out some JavaScript code, for example:
```javascript
> message = "Hello world!"
```

Installing node should also have installed npm. Try:
```bash
npm --version
```
which should give you something like `5.6.0` (don't worry if your version is slightly different).

## Windows systems (Windows 7+)
### Your text editor

We will be using Visual Studio Code as our text editor. Download and install it from [here](https://code.visualstudio.com/Docs/setup/setup-overview).

### Chocolatey (Windows only)

[Chocolatey](https://chocolatey.org/) is the "Homebrew" for Windows. This allows you to easily install software through your command-line.

1. To set it up, you will need Administrator access to cmd or Powershell. 
[Open CMD with Administrator access](https://www.thewindowsclub.com/how-to-run-command-prompt-as-an-administrator)

2. In your cmd (with administrator access) copy - paste the following code to download and install Chocolatey.
```bash
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

### NodeJS
Subsequently, installing nodejs and git will be seamless. 
```bash
choco install nodejs
```

Nodejs commands will then be similar across the different operating systems. :)


### Git
Open your command prompt with Administrator access (As explained above).

1. Install git using chocolatey
```bash
choco install git
```
2. Check your git version
```bash
git --version
```

## That's all folks!

You're done with the setup! Now you can check out the pre-bootcamp workshop git repos, and read the README for instructions on how to run the code!
