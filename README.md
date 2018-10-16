The Terminal Trio
==============================

You can use this repo to configure your ZSH Tmux and Prezto terminal.

This project is based on the original [Prezto Repo](https://github.com/sorin-ionescu/prezto).


Installing ZSH
--------------

### Linux Ubuntu

**[Open a terminal window](https://help.ubuntu.com/community/UsingTheTerminal). Copy & paste the following** into the terminal window and **hit `Return`**. You may be prompted to enter your password.

```shell
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install zsh
```


### Mac OS
**Copy & paste the following** into the terminal window and **hit `Return`**.

1. Install Homebrew
    ```shell
    ruby -e "$(curl -fsSL https://raw.zshhubusercontent.com/Homebrew/install/master/install)"
    brew doctor
    ```

2. Instll ZSH
    ```shell
    brew install zsh
    ```


Installing TMUX
---------------

### Linux Ubuntu

```shell
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install tmux
```

### Mac OS

```shell
brew install tmux
```


Installing Prezto
-----------------

1. Launch Zsh:

    ```console
    zsh
    ```

2. Clone the repository:

    ```console
    git clone --recursive https://github.com/alisezer/my-terminal.git "${ZDOTDIR:-$HOME}/.my-terminal"
    ```

3. Create a new Zsh configuration by copying the Zsh configuration files
    provided:

    ```sh
    setopt EXTENDED_GLOB
    for rcfile in "${ZDOTDIR:-$HOME}"/.my-terminal/runcoms/^README.md(.N); do
      ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
    done
    ```

    Note: If you already have any of the given config files, ln will error. In
    simple cases you can add `source "${ZDOTDIR:-$HOME}/.zprezto/init.zsh"` to
    the bottom of your `.zshrc` to load prezto but keep your config intact. For
    more complicated setups, it is recommended that you back up your original
    configs and replace them with the provided prezto runcoms.

4. Set Zsh as your default shell:

    ```console
    chsh -s /bin/zsh
    ```

5. Open a new Zsh terminal window or tab.

Updating
--------

Run `zprezto-update` to automatically check if there is an update to zprezto.
If there are no file conflicts, zprezto and its submodules will be
automatically updated. If there are conflicts you will instructed to go into
the `$ZPREZTODIR` directory and resolve them yourself.

To pull the latest changes and update submodules manually:

```console
cd $ZPREZTODIR
git pull
git submodule update --init --recursive
```

For anything else, please refer to the original prezto repo.