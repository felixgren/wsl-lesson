# wsl-lesson
Ida &amp; Felix WSL lektion 4 n00bz

### Commands 

[`cd`](https://tldr.ostera.io/cd)  |  Change the current working directory to WSL <br>
`explorer.exe .` | Opens up the graphical interface for the map you are in. <br>
`wsl`  |  Opens up your default WSL Linux distro if you are in PowerShell <br>
`exit`  |  Takes you back to PowerShell

`\\wsl$\Ubuntu` | This is the Ubuntu root directory  
`\\wsl$\Ubuntu\home\<yourname>` This is where your personal Linux files typically will be stored at

### Set up

1. Let's get started by setting up WSL the way we want it! First we want to set WSL as our default version. 
Open up PowerShell and write `wsl --set-default-version 2`

2. Unfortunately, Ubuntu will now use root as the default user. We don't want that! We want your username to be the default user. Enter the following command: `ubuntu config --default-user <yourname>`
where `<yourusername>` is the username you defined during installation. 
  
3. As listed above your Linux files will typically be stored at `\\wsl$\Ubuntu\home\<yourname>`. It's best to use this as the starting folder in Windows Terminal. Let's open the settings in PowerShell and add the following configuration line to the Ubuntu profile: 
  `"startingDirectory": "//wsl$/Ubuntu/home/<yourname>/"`
