# remote-dev-environment-nodejs

Description:
This is a development environment where you can have in a remote docker container all the configuration to code your nodejs project.

Characteristics:
OS:                     Alpine linux
SHELL:                  Zsh with Oh-My-Zsh (plugins for autocompletion, and a nice theme)
EDITOR:                 Visual Studio Code
COMMAND LINE EDITOR:    Neovim + plugins

Usage:
I order to use this environment, you must create a new folder for your project. This folder's name must end in "-PROJ" in order to be detected by the environment and work properly.

In .devcontainer all the files to setup the remote environment, don´t touch if you don't know what you are doing but you can use...
devcontainer.env    // Set all the environment variables you'll need in your project 

In .devcontainer/config path you will find all the environment config files that you will can customize.
.zshrc          // Configuration file that contains the commands that run the zsh shell
.zsh_history    // We can have some frecuent commands in orther to use by the autocompletion
.gitconfig      // Git configuration
init.vim        // Neovim configuration

Requirements:
`Docker desktop` - `WSL2`

