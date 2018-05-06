### Installing the Anaconda Python Distribution for your OS

Personally, I think it makes a lot of sense to use the Anaconda Python Distribution to install Jupyterlab. Installing Anaconda can ease the installation of isolated Python environments, which can be enriched by additional (as you need) python packages.

To install the Anaconda Python Distribution, you can follow instructions (for your Operating System) on:
+ https://anaconda.org/
+ https://conda.io/docs/user-guide/install/index.html

#### Installing Anaconda Python Distribution on Mac OS X with homebrew

1. You would need to have installed [Homebrew](https://brew.sh/) and [Homebrew Cask](https://caskroom.github.io/).
2. `$ brew cask install anaconda`.
3. Modify your shell configuration to avoid anaconda messing up with Homebrew installations. I found [this blog post](https://hashrocket.com/blog/posts/keep-anaconda-from-constricting-your-homebrew-installs) useful. I use `zsh`, and here you can find a portion of my `~/.zshrc` that I found useful to keep anaconda and homebrew python installations separate.

    ```
    export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)

    SANS_ANACONDA="/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin"
    SANS_ANACONDA=${JAVA_HOME}/bin:${SANS_ANACONDA}
    SANS_ANACONDA=~/.local/bin:~/.cabal/bin:${SANS_ANACONDA}
    SANS_ANACONDA=/Library/Frameworks/Mono.framework/Versions/Current/bin:${SANS_ANACONDA}

    PATH="/usr/local/anaconda3/bin:$SANS_ANACONDA"
    export PATH
    
    alias perseus="export PATH="\$SANS_ANACONDA" && echo Medusa decapitated."
    alias medusa="export PATH="/usr/local/anaconda3/bin:\$SANS_ANACONDA" && echo Perseus defeated."

    brew () {
    perseus
    command brew "$@"
    medusa
    }
    ```

    If you use `bash` you can use a similar configuration in your `~/.bashrc`.

#### Installing Anaconda Python Distribution on Windows

1. Download an [installer for Windows](https://www.anaconda.com/download/#windows)
2. Make sure you have Anaconda available in your `%PATH` to be able to use if from the command line (if you ever plan to use the command line instead of the `anaconda-navigator`).

#### Installing Anaconda Python Distribution on a Linux Distribution

1. Download an [installer for Linux](https://www.anaconda.com/download/#linux)

2. Verify that the installer has permissions to be executed. Otherwise you can use `$ chmod +x Anaconda3-X.X.X-Linux-x86_64.sh` (modify this to use the actual name of the installer) to add execution permissions.
3. Run the installer. You may be able to do that with something like: `$ bash Anaconda3-X.X.X-Linux-x86_64.sh`.
4. Modify your `$PATH` environment variable so that you can find `conda` and all the `python` packages that come with Anaconda Python Distribution.