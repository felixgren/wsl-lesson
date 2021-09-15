# WSL 

<img src="https://media0.giphy.com/media/A06UFEx8jxEwU/giphy.gif?cid=ecf05e473yvpc9epyt2bokina5hjf0372ocyavxodfdvsawz&rid=giphy.gif&ct=g" />

-   :books: Documentation
  -   [WSL docs](https://docs.microsoft.com/en-us/windows/wsl/#get-started)

-   :link: Links
-   [Why WSL](https://devblogs.microsoft.com/premier-developer/why-developers-should-install-wsl-today/)

### Commands 
Command | Description
------- | -----------
[`cd`](https://tldr.ostera.io/cd)  |  Change the current working directory to WSL <br>
`explorer.exe .` | Opens up the graphical interface for the map you are in. <br>
`wsl`  |  Opens up your default WSL Linux distro if you are in PowerShell <br>
`exit`  |  Takes you back to PowerShell

`\\wsl$\Ubuntu` | This is the Ubuntu root directory  
`\\wsl$\Ubuntu\home\<yourname>` This is where your personal Linux files typically will be stored at
`sudo apu update` | update wsl 

### Set up

1. Let's get started by setting up WSL the way we want it! First we want to set WSL as our default version. 
Open up PowerShell and write `wsl --set-default-version 2`
If version 2 still does not run we will try writing this command instead: `wsl --set-version Ubuntu-20.04`
<br>

2. Unfortunately, Ubuntu will now use root as the default user. We don't want that! We want your username to be the default user. Enter the following command: `ubuntu config --default-user <yourname>`
where `<yourusername>` is the username you defined during installation. 
<br>
  
3. As listed above your Linux files will typically be stored at `\\wsl$\Ubuntu\home\<yourname>`. It's best to use this as the starting folder in Windows Terminal. Let's open the settings in PowerShell and add the following configuration line to the Ubuntu profile: 
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

  Type `/mnt/c` to access your C: harddrive. 
  
  Notice how fish helps you finish the syntax? 
  
  If you want to get back to Ubuntu from here you can simply type `cd` 
  
  6. Now you can start adding folders to your Ubuntu if you want. For example you can add a workspace folder for your projects and a lessons folder for your lessons. 
  <br> <br> 
  7. Don't forget to update WSL from time to time:
  `sudo apt update`
