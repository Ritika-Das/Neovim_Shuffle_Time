# Neovim_Shuffle_Time
Screenshots' walkthrough repository for setting up Neovim GUI on Windows 10 64-bit configuration.

# Using NeoVim as an effortless way to edit code – Installation and Setup Guide for Windows 10
Hey fellow Devs, it's Ritika here. 
I recently tried out NeoVim on my PC to see what it's like. Ever wanted to delete text between tags/braces, save files, switch to a certain line number in your code, undo, search for a word - all without having to touch your mouse? Try this fancy editor with me.

# What is NeoVim?
Neovim is a GUI that can help us maintain and contribute more by dividing the work, which can be installed on any platform such as Linux, Windows or macOS. We can replacing the code editors which take up a lot of disk space by installing this effective refactored version of Vim.

# Installing NeoVim on Windows 10 and adding it to system PATH variable
From NeoVim’s official repository on GitHub, download the zip file for Windows (64-bit) by [clicking here](https://github.com/neovim/neovim/releases/download/v0.4.4/nvim-win64.zip) or the zip file for Windows (32-bit) by [clicking here](https://github.com/neovim/neovim/releases/download/v0.4.4/nvim-win32.zip), which is of size 23 MB approximately. 

Then extract the zip file by clicking on it once and selecting “Extract All”.
![1.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/1.jpg)
After the extraction is completed, copy the location of your extracted folder and add it to system PATH variable.
![2.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/2.jpg)
<a id="Label">Right-click on This PC</a> -> Properties -> Advanced system settings on left side of Control Panel -> Environment Variables -> Double-click on Path in System Variables pane -> Add New Path by pressing New and pasting the extracted folder’s location and Click OK on all the three windows simultaneously.
![3.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/3.jpg)
![4.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/4.jpg)
![5.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/5.jpg)
![6.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/6.jpg)
![7.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/7.jpg)
Now go to the extracted nvim-win64 and go into the nested folders Neovim -> bin. You’ll come across an application named nvim-qt.exe which is a GUI NeoVim client not to be confused with the terminal NeoVim - run it. 
![8.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/8.jpg)
Neovim (nvim-qt) will open up like the following –
![9.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/9.jpg)
[Note:- The application may be slightly different due to plugins I’ve already installed, but similar dark background will appear with tilde in each line.]

# Accessing nvim from anywhere, without opening nvim-qt.exe
Remember how we just added the ~/AppData/Local/nvim folder to our system PATH? <a href="#Label">Click here to revisit the steps.</a> This time we’ll add the bin folder nested in nvim-win64 extracted folder, whose path looks like ~/nvim-win64/Neovim/bin. This will make Neovim more user-friendly for us, as it displays more options like :help for a walkthrough, :checkhealth for optimization on startup.
![10.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/10.jpg)
Your path will look something like this. Copy it and repeat the steps of right-clicking This PC -> Properties -> Advanced System Settings -> Environment Variables -> System variables’ pane -> Double-click Path -> Paste the bin folder location in a new line -> Click some OKs!
![11.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/11.jpg)
There you go! You can now open Neovim by pressing Windows + R keys (shortcut for Run), typing nvim and clicking OK.
![12.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/12.jpg)
You can also open up Command Prompt, type nvim and press Enter for the same result.
![13.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/13.jpg)
![14.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/14.jpg)
It’ll open up like this in both cases :
![15.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/15.jpg)

Boom! You have installed Neovim successfully. To exit Neovim for now, type :q and press Enter. The colon (:) takes Neovim into command mode, and q is for quit. If you want to have fun, let’s dive into configuring Neovim to make things more usable to you.

# Configuring NeoVim – the easiest way
The Neovim configuration file is named init.vim which can be edited for our purpose. It is usually found under the directory ~/AppData/Local/nvim. In case you’re not sure about the exact location, open Neovim from nvim-qt.exe, type :echo stdpath(‘config’) in Neovim and press Enter. 
![16.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/16.jpg)
![17.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/17.jpg)
See? It echoes or displays the exact location of your nvim folder on the command line, if it exists.

If not already present, we need to create the directory nvim within ~/AppData/Local i.e. we’ll put our init.vim file in ~/AppData/Local/nvim. 
Note :- Don’t get confused between nvim and nvim-data folders. Keep nvim-data folder untouched, and only create a new nvim folder if it doesn’t exist.
The easiest way to do so is to open up a new .txt file inside ~/AppData/Local/nvim, add the first and last lines at least i.e. 
```
call plug#begin('C:/Users/Ritika/AppData/Local/nvim/plugged') 
call plug#end()
```
Now we’ll add vim-plug for managing the plugins we are going to use in Neovim. For this, enter the Plug lines within the previous two lines. You don’t need to add all the plugins listed below; instead choose some plugins from them like onedark, coc.nvim, vim-airline. If you want cool icons beside folders and files, you can use the command 
```
Plug 'ryanoasis/vim-devicons'
```
although I haven’t used it in this installation.
![18.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/18.jpg)
```
call plug#begin('C:/Users/Ritika/AppData/Local/nvim/plugged')
" below are some vim plugins for demonstration purpose.
" add the plugin you want to use here.
Plug 'joshdick/onedark.vim'
Plug 'iCyMind/NeoSolarized'
Plug 'neoclide/coc.nvim'
Plug 'junegunn/vim-easy-align'
Plug 'https://github.com/junegunn/vim-github-dashboard.git'
Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }
Plug 'tpope/vim-fireplace', { 'for': 'clojure' }
Plug 'rdnetto/YCM-Generator', { 'branch': 'stable' }
Plug 'fatih/vim-go', { 'tag': '*' }
Plug 'nsf/gocode', { 'tag': 'v.20150303', 'rtp': 'vim' }
Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
call plug#end()
```
When you are happy with your list of plugins, save the init configuration file as All Files, and add the .vim extension after filename init. Delete the init.txt file previously saved.
![19.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/19.jpg)

# Vim-plug
Vim-plug makes it easy to manage all your plugins on Neovim by downloading plugins into separate directories and loading them correctly. Open Windows PowerShell on your PC. 
![20.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/20.jpg)
Then copy the following command, paste it into PowerShell prompt, and hit Enter to execute it.
```
md ~\AppData\Local\nvim\autoload
$uri = 'https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
(New-Object Net.WebClient).DownloadFile(
  $uri,
  $ExecutionContext.SessionState.Path.GetUnresolvedProviderPathFromPSPath(
    "~\AppData\Local\nvim\autoload\plug.vim"
  )
)
```
![21.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/21.jpg)
I received the first error because I already have vim-plug installed with the same commands. You don’t have to worry about it. Go ahead and press Enter after you arrive at this.
This automatically creates a folder called autoload inside your ~/AppData/Local/nvim folder and a file called plug.vim inside the autoload folder after the aforementioned command execution.
![22.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/22.jpg)
![23.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/23.jpg)
If you made it till this far, you are ready to install some plugins using vim-plug!

# Installing plugins using vim-plug
We included some Plug commands in our init.vim file to install a lot of plugins for Neovim. We can now install them into Neovim using vim-plug. Create a new folder called plugged inside the ~/AppData/Local/nvim as follows. This (plugged folder) is where all your plugins would get installed. Restart nvim if you already have it open.
![24.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/24.jpg)
Open nvim by Run command, type the command :PlugInstall into the Neovim window and press Enter. You’ll notice that all the plugins you desired to get into Neovim by writing those down into init.vim will now start to get installed one-by-one. It takes a few minutes to install new plugins.
![25.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/25.jpg)
![26.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/26.jpg)
You’ll receive a confirmation like this when Neovim is done installing the available plugins using vim-plug. To verify, check if we got any folders of our installed plugins inside plugged folder.
![27.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/27.jpg)
There they are!
You can delete, add new plugins, check status of installed plugins or update existing ones using commands like :PlugStatus for status check and :PlugUpdate for updating existing plugins. Always restart Neovim before you use any vim-plug commands like this, otherwise plugins may not get properly installed.
![28.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/28.jpg)
![29.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/29.jpg)
As in above, the plugins onedark.vim and coc.nvim got updated. You can use :PlugDiff command to examine the changes between the previous version of the plugin and the current update.
![30.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/30.jpg)
You successfully installed these plugins, updated them and compared the differences. If you are feeling adventurous, you can use :help vim-plug to find out more information about how you can use vim-plug to the fullest.

# Setting up HTML, CSS, JSON, TypeScript extensions for Neovim using coc.vim
coc.vim is a plugin which can be installed using vim-plug, which helps us in editing generic web development or other language code in a lot of supported languages. Check if you have the coc.vim plugin already installed using :PlugStatus command. 
**Quick Tip :-**
Instead of using certain apps to open .vim files and .json files for viewing contents, you can copy the exact location of the required file, paste it in any browser and hit Enter. 
![31.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/31.jpg)
If not installed, open up init.vim for editing like before and include the following Vim command and save it as init.vim again.
```
Plug 'neoclide/coc.nvim', {'branch': 'release'}
```
Restart nvim, and install it using :PlugInstall. Then restart nvim again.
Type the command :checkhealth in Neovim and press Enter. It’ll show you if the coc service is already running. If yes, use :CocInfo for details on the service.
![32.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/32.jpg)
To install language extensions, we need to use :CocInstall lang1 lang2 lang3 format command.
We can include as many as we want, with at least one language. For example, if we want to install only the extension for TypeScript, we use 
:CocInstall coc-tsserver
else if we want to install extensions for HTML, CSS and JSON all at one go, we use
:CocInstall coc-html coc-css coc-json
You’ll see a message saying it has been installed (here I only installed the one for HTML).
![33.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/33.jpg)

# Uninstalling a coc extension 
We use :CocUninstall command followed by the extension name to uninstall the particular extension. Example – to uninstall a previously installed CSS extension for coc, we use
```
:CocUninstall coc-css
```

# Updating a coc extension
We use :CocUpdate command to update a coc extension.
![34.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/34.jpg)
It will update the available coc extensions.

# Configuring coc-settings to support not implemented languages and checking existing coc extensions list
The list of all available coc-extensions are listed here. 
You can quickly check all the installed extensions available to you by :CocList extensions command.
![35.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/35.jpg)
A plus (+) sign before the extension means that it is loaded. A minus (-) sign before it means that it has been disabled. An asterisk (*) sign indicates that it has been activated. A question (?) mark implies that it is an invalid extension. In the above example, coc-prettier has been activated and the rest have been loaded. Press Esc key to go back after you have checked your extensions.
To edit the configuration file for coc.vim, we use :CocConfig command, which opens up coc-settings.json for us to edit and add other languages. Delete all the pre-existing text using :%d command from Normal Mode to Command Mode, paste the following code into the editor by right-clicking into the empty file and save the configuration file coc-settings.json using :w command.
```
{
  "suggest.noselect": false,
  "eslint.nodePath": "/home/user/.config/yarn/global/node_modules",
  "coc.preferences.formatOnSaveFiletypes": [
    "javascript",
    "typescript",
    "typescriptreact",
    "json",
    "javascriptreact",
    "typescript.tsx",
    "graphql",
    "html"
  ]
}
```
![36.jpg](https://raw.githubusercontent.com/Ritika-Das/Neovim_Shuffle_Time/main/Screenshots/36.jpg)
Use keys h, j, k and l to navigate left, down, up and right respectively on the file to be edited in Normal Mode, and press i to Insert. Press Esc key to go back to Normal Mode from Insert Mode. In the coc.preferences.formatOnSaveFiletypes array, type in your preferred languages as array elements within double quotation marks such as “html”, and remove any if not required. Save the file again using :w command.

Did you find this useful? Or did you get stuck somewhere in the middle? Comment below to let me know :)
