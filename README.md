# RDR 2 Cleaner
A tool to clean out mods from Red Dead Redemption 2 for online play, and restore them later.

## Download

Get the latest version from the [Releases](https://github.com/VictorGamer072YT/rdr2-cleaner/releases/latest) page.

[Download for Windows](https://github.com/ganeshh123/rdr2-VictorGamer072YT/releases/download/1.0.0/rdr2cleaner_1.0.0.zip)

## Usage
1. Download and extract 'rdr2cleaner.exe' to the root 'Red Dead Redemption 2' folder (same place as RDR2.exe)

2. Double Click and run 'rdr2cleaner.exe'

3. Enter your choice. Either 'clean' or 'restore'

  'clean' : Cleans your RDR 2 Installation of mods leaving you with the Base Game for Online Play
  
  'restore': Restores cleaned mods for Single Player

  ![usage](docs/usage.png)
  
4. Once the process is completed, press any key to exit the tool and open the game normally

5. If you use OpenIV or for extra safety, you should verify the integrity of your game files:
    - Steam: [https://help.steampowered.com/en/faqs/view/0C48-FCBD-DA71-93EB](https://help.steampowered.com/en/faqs/view/0C48-FCBD-DA71-93EB)
    - Rockstar Launcher: [https://support.rockstargames.com/articles/360036000713/](https://support.rockstargames.com/articles/360036000713/)
    - Epic Games Launcher: [https://www.epicgames.com/help/en-US/technical-support-c90/general-support-c91/how-do-i-verify-game-files-in-the-epic-games-launcher-a3638](https://www.epicgames.com/help/en-US/technical-support-c90/general-support-c91/how-do-i-verify-game-files-in-the-epic-games-launcher-a3638)

## Building
### Running on Node
1. Clone/Download the project and copy app.js and essentialFiles.js into the RDR 2 Installation root directory.

2. Open Command Prompt inside the RDR 2 Installation root directory and run ```node app.js```


### Compiling a Windows Executable
Executables are compiled with a very [specific version of nexe](https://github.com/cspotcode/nexe/tree/fix-vfs) that allows access to the filesystem, which has a tricky setup procedure.

#### Installing the correct version of nexe
Run **install_nexe_win.bat** as admin on **Windows**, will take about 5 minutes to install fully.

Alternatively, install manually like this:

1. Firstly, install the general [nexe](https://www.npmjs.com/package/nexe) globally with the command:

    ```bash
    npm install -g nexe
    ```
2. In the project root folder build some executables with this version of nexe to download node binaries for Windows:

    ```bash
    nexe . --target win32-x86-10.13.0
    ```

    This will download the binaries we need for later, delete the executables built with this for now.

3. Now we need to install a [specific version of nexe](https://github.com/cspotcode/nexe/tree/fix-vfs) that allows access to the filesystem:

    Run the command:

    ```bash
    npm install -g cspotcode/nexe#19a5046
    ```

Now we should have the correct version of nexe for building.

Confirm by running:

```bash
nexe -v
```

![nexe-version](docs/nexe-version.png)

Check that the version is `4.0.0-beta.4`

#### Compiling the exe
Run **build_win32.bat** on **Windows** to build a Windows Executable. This can be found in /dist.

To Compile Manually

To build a Windows Executable, run the command:
```bash
nexe . --target win32-x86-10.13.0 -o ./dist/rdr2cleaner.exe
```
in the root directory of the project.

## Credits
GTA 5 Cleaner by <a href="https://github.com/ganeshh123" title="Ganesh H">Ganesh H</a> from <a href="https://http://ganeshh123.github.io/" title="ganeshh123"> http://ganeshh123.github.io/</a>.
