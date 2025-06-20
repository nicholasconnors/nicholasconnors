Astrophysics is unique in that everyone has a Mac for some reason so a lot of libraries are Unix-based meaning you'll need to install Linux to get them working on a non-Apple computer.

### Windows Subsystem for Linux
- Open command prompt as administrator (windows 11: search "command prompt", right-click, run as admin)
- Type `wsl --install`
- Reboot when done
- Once you've restarted run `wsl --install Ubuntu` or whichever Linux distro you prefer. Follow installation instructions. Reboot again when done.

With wsl installed you can run `wsl` in command prompt to enter Linux. From here you can run code normally.
By default `wsl` has its own file system separate from your regular Windows files. To access your Windows filesystem from `wsl` type in `cd /mnt`

### Anaconda on wsl
- Download Miniconda installer for Anaconda from their [website](https://www.anaconda.com/download/success) (select the first one for Linux which will be a bash file).
![image](https://github.com/user-attachments/assets/1812f72d-5b6e-4ef9-852e-1265597e17c7)
- In your `wsl` command prompt navigate to where the file has downloaded e.g. `cd /mnt/c/Users/<your username>/Downloads` and run `bash <installer name>.sh`
- Restart command prompt when done and re-enter WSL by typing `wsl` in command line.
- Run `sudo apt update`
- Run `sudo apt install python3-pip`

With this done you should have conda and pip set-up on wsl so you can start installing packages and running your code.

### Visual Studio Code on wsl

Microsoft has instructions on how to do this [here](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode).
Once vscode is installed you can open it within wsl by navigating to the folder where your project is and running `code .` in command prompt (after running `wsl` of course).

### Jupyter notebooks on wsl
There are some steps you have to take to have Jupyter notebooks run on `wsl` automatically open in your browser.

- Run `sudo apt install wslu`
- Nagivate to `/home/[your username]` in the Linux filesystem (you can do this in your regular file explorer in Windows)
- Modify `.bashrc` (you might have to enable displaying hidden files) and add this line to it: `export BROWSER=wslview`
- Run `pip install notebook` to install Jupyter notebooks (it's probably already installed from installing Miniconda though)
- Now if you run `jupyter notebook` from the `wsl` command prompt it will properly open in your browser.
