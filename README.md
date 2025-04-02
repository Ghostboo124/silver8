# silver8
My own CPU

# Linux Instructions
1. Build it from source

    1a. run one of the following command to update your system packages depending on your distribution (All need to be run as superuser)
    ```sh
    sudo apt update && sudo apt upgrade -y
    sudo yum update
    sudo dnf update
    sudo pacman -Syu
    sudo apk update && sudo apk upgrade
    ```

    2a. Install build tools using one of the following commands based on your distro.
    ```sh
    sudo apt install build-essential, git
    sudo yum install centos-release-scl, git && sudo yum install devtoolset-7-gcc* && scl enable devtoolset-7 bash
    sudo dnf install gcc, git
    sudo pacman -S gcc, git
    sudo apk add build-base, git
    ```

    2b. Clome the repo and build from soource
    ```sh
    git clone https://github.com/Coloured568/silver8
    cd silver8
    gcc -o silver8 main.c -static
    ```

3. Run `./silver8 [optional path to a .s8 file]`
4. Boom! You now have an emulator for this custom CPU.

# Windows Instructions
1. Either build it from the source (preferred) or [download it](https://github.com/Coloured568/silver8/releases) from the latest release.

   1a. To build it from source, first install [MSYS2](https://msys2.org) from the website or in powershell using the command `winget install --id MSYS2.MSYS2 --scope user` and follow the instructions of the installer

   1b. Then, once installed, open `MSYS2 UCRT64` and type the following commands to install the compilation tools (the first command will close the window, just reopen it and continue):
   ```sh
   pacman -Syu
   pacman -S ucrt64/mingw-w64-ucrt-x86_64-gcc
   pacman -S msys/git
   ```

   1c. Then, type clone this repo using some type `git clone https://github.com/Coloured568/silver8.git` and then enter it with `cd silver8` (Please note that you will only be able to use this repo within MSYS UCRT64 if you do this, if you want to be able to use it from within windows easily, then type `cd /c/users/{your username}/` and type the `git` command after that)

   1d. Then type `powershell -C "./compile.ps1"`

   1e. Aaand you are done

6. To run the file type `./silver8 [optional path to a .s8 file]` within powershell or MSYS2 or `.\silver8.exe` within command prompt (when you are in the silver8 github repo)
7. It should output whatever program you ran!

P.S the program file *has* to be named "program.s8" it will not work otherwise. i havent really implemented a "file-loader" or anything like that yet.
# Yes I am totally interested and want to write programs for this emulator!
Documentation is coming soon (Or maybe never?)
