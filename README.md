<img src="https://c.tenor.com/ZNu5AVd29LEAAAAC/steve-ballmer-microsoft.gif" width="100%">

# WSL - Windows Subsystem for Linux

- :books: Documentation

    - [WSL docs](https://docs.microsoft.com/en-us/windows/wsl/#get-started)

- :link: Links

    - [Why WSL](https://devblogs.microsoft.com/premier-developer/why-developers-should-install-wsl-today/)

### FAQ
<details>
<summary>OK, so what is WSL? (Windows Subsystem for Linux)</summary>
  
WSL is a system that allows you to run Linux inside Windows. Linux is an OS (operating system), just like Windows or MacOS. So what WSL allows you to do is to run an OS (Linux in this case) inside your own regular Windows OS! Wow, a computer inside your computer!
  
</details>
<details>
<summary>What is Linux, why do we even want it?</summary>
  
Linux is an operating system which works very differently from how Windows does. The way Linux is designed is preferrable to us developers, because it allows our workflow to be a lot quicker and easier. 
  
If you want to install PHP inside Linux, you simply run `sudo apt install PHP` instead of downloading some .exe file from a website, running its installer and then restarting your computer for it to be fully installed like how you usually do things inside Windows.
  
If you want to update your system, you simply run `sudo apt update && sudo apt upgrade` and it will download and install the latest updates without you having to even restart your computer. And even better, this updates **all** of your installed programs, not just the system!
  
</details>
<details>
<summary>Yeah so... Ubuntu???</summary>
  
OK, so. It's not as simple as Linux being 'one' operating system.
  
There are actually a bunch of different operating systems which are all based on Linux as it's core, and one of these is Ubuntu.
  
These different operating systems are called 'Linux distributions', they are called this as they are all different operating systems that use the same fundamental core. These OS's can vary quite a bit in how they look, what console commands you use, what software they come with and a bunch of other things. But ultimately they all run on the same foundation, which is the Linux Kernel. 
  
Ubuntu is our choice of Linux distribution, as it is quite accessible for new users and work great with WSL.
  
When we run Ubuntu inside WSL, all we see is a console window. This is a minified version of the OS without any graphical interface. But if you wish you can easily search for Ubuntu online and install it as an entire operating system on your computer, you could even replace Windows entirely if you wish. For a lot of people, this isn't what they are looking for though. So this is why WSL exists to give us a glimpse into Linux and for us to be able to reap the benefits of it's architecture without sacrificing the comfort and benefits that we enjoy of our own operating system of choice.
  
</details>

### WSL Specific Commands
Command | Description
------- | -----------
[`cd`](https://tldr.ostera.io/cd)  |  Typing `cd` without anything else will make you go to your home in linux <br>
`explorer.exe .` | Opens up the graphical interface for the map you are in. <br>
`explorer.exe .` | Open the location you are at inside the Windows File Explorer <br>
`code .` | Open VSCode for the project you are in.
`sudo apt update` | Check for updates. This is like searching for updates on Windows update but for your Linux/Ubuntu system.
`sudo apt upgrade` | Apply updates. This is downloading and installing the updates for your Linux.
`wsl`  |  If in PowerShell, open up your default WSL Linux distro. <br>
`exit`  |  If in PowerShell, exit from WSL back to PowerShell.

### General Console Commands.
Command | Description
------- | -----------
[`cd`](https://tldr.ostera.io/cd) | Go somewhere.
[`pwd`](https://tldr.ostera.io/pwd) | Check where you are.
[`ls`](https://tldr.ostera.io/ls) | List folder contents. 
[`cp`](https://tldr.ostera.io/cp) | Copy files/folders.
[`mv`](https://tldr.ostera.io/mv) | Move or rename files/folders.
[`mkdir`](https://tldr.ostera.io/mkdir) | Create a new folder.
[`rm`](https://tldr.ostera.io/rm) | Remove files or folders.
[`rmdir`](https://tldr.ostera.io/rmdir) | Removes a folder.
[`touch`](https://tldr.ostera.io/touch) | Create files.


`\\wsl$\Ubuntu`  This is the Ubuntu root directory  
`\\wsl$\Ubuntu\home\<yourname>` This is where your personal Linux files typically will be stored at

### Set up

1. Let's get started by setting up WSL the way we want it! First we want to set WSL 2 as our default version. 
Open up PowerShell and write `wsl --set-default-version 2`
If version 2 still does not run we will try writing this command instead: `wsl --set-version Ubuntu-20.04`
<br>

2. If Ubuntu starts root as default user we would like to change that. We want your username to be the default user. Enter the following command: `ubuntu config --default-user <yourname>`
where `<yourusername>` is the username you defined during installation. 
<br>
  
3. Your Linux files will typically be stored at `\\wsl$\Ubuntu\home\<yourname>`. It's best to use this as the starting folder in Windows Terminal. Let's open the settings in Windows Terminal and add the following configuration line to the Ubuntu profile: 
  ``` 
  "startingDirectory": "//wsl$/Ubuntu/home/<yourname>/"
  ```
  <br>
  
4. Now that we have our settings for the terminal let's install [Fish shell](https://fishshell.com/docs/current/tutorial.html).  
  `apt-get install fish`
  After installing fish lets try it out. Enter: `fish` in your terminal.
  You will be greeted by a prompt which means you are all set up. 
  
  If you'd like you can set Fish as your default shell instead of bash: 
  ``` 
  chsh -s /usr/bin/fish
  ``` 
  <br>
  5. With WSL you can easily access your windows system files whenever you want. This is defined by `/mnt/` 

  Type `cd /mnt/c` to access your C: harddrive. 
  
  Notice how fish helps you finish the syntax? 
  
  If you want to get back to Ubuntu from here you can simply type `cd` 
  
  6. Now you can start adding folders to your Ubuntu if you want. For example you can add a workspace folder for your projects and a lessons folder for your lessons. 
  <br> <br> 
  7. Don't forget to update WSL from time to time: <br> 
  `sudo apt update` <br>
`sudo apt upgrade`
