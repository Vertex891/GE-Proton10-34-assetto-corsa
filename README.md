# GE-Proton10-34-assetto-corsa

## setup instructions for installing assetto corsa with content manager and csp (latest preview working).  

### *based on siha's script found [here](https://github.com/sihawido/assettocorsa-linux-setup)*

1. Install assetto corsa through steam
  
2. use protonup-qt ```$ yay -S protonup-qt``` to install GE-Proton 10-34.
    - you don't need to install GE-Proton 9-20, the script will handle that in the next steps.
  
3. visit the github above and grab the script, you can use the script by copying the curl command there and pasting it in terminal.

4. run the script.
    - it should find your game directory automatically. if correct, type `y` and press `enter`.
      
    - it will ask you if you want to install GE-Proton 9-20. type `y` and press `enter`.
      
    - it will now ask you to close steam, relaunch it, and run assetto corsa to generate a new wine prefix
      - Restarting steam is important! 
        - tip: make sure that GE-Proton 9-20 is set in compatibility tab before you do first launch.
          *right click on the game in your library and click properties / compatibility*
        - If GE-Proton9-20 still doesn't show up after restarting steam, reboot and it should appear.  
          >**IMPORTANT:**  
          >**FIRST LAUNCH IS GOING TO TAKE A WHILE**  
          >it may appear nothing is happening but let it go until you get to the assetto corsa main menu  

5. close assetto corsa and rerun the script in terminal.
    - again it should find your game directory automatically. type `y` and press `enter`.
      
    - when it asks you to reinstall GE-proton 9-20, type `n` and press `enter`.
      
    - it will also ask you if you want to delete the existing wine prefix. type `n` and press `enter`.
      
    - now it will ask to install content manager. type `y` and press `enter`.
      
    - it will ask you to install csp.  type `y` and press `enter`.
       - installing the fonts can take a few minutes, just let it run.
      
    - it will ask if you want to resolve input mapping issues. type `n` and press `enter`.
      
    - it will ask to install dxvk. type `y` and press `enter`.

6. launch assetto corsa from steam and it should open content manager and ask for your game directory
    - your game directory will likely be in `/home/yourname/.local/share/Steam/steamapps/common/assettocorsa` replacing /yourname/ with your username
      >>add a Z: to the beginning when relating to content manager.
      >>>for example `Z:/home/yourname/.local/share/Steam/steamapps/common/assettocorsa`

7. join a public server requiring csp to ensure no csp errors.
    - if you receive a failed to patch assetto corsa error from csp, the only know fix is to reinstall AC

### now the game should work fine for some of you, but on GE-Proton 9-20, my generic shifter isn't recognized and performance is poor. so now we'll configure GE-proton 10-34.  
1. go back to assetto corsa's compatibility settings and switch to GE-Proton 10-34

>AFTER THIS STEP DO NOT LAUNCH THE GAME UNTIL THE END OF THE GUIDE OR IT WILL GENERATE A COMPLETELY NEW WINE PREFIX AND YOU WILL LIKELY HAVE TO REINSTALL

2. install protontricks ```sudo pacman -S protontricks``` and launch it.

3. click `assetto corsa` and click `ok`.

4. click `select the default wineprefix` and click `ok`.

5. click `install a windows component or dll` and click `ok`.

6. scroll through and select all cached items and click `ok`.
   - installing these may take a while as well.

7. click `run winecfg` and click `ok`.
   - go to the libraries tab and in the new override textbox type `dwrite` and click `add`
   - scroll to dwrite in the menu and ensure it says `dwrite (native, builtin)` and click `apply` and `ok`.

8. run assetto corsa from steam

## Now the game should work running GE-Proton 10-34 for better performance and usb device compatibility

### Note
- only tested on latest cachyOS kernel.
- i wasted a lot of time trying to get 10-34 working, and honestly the h pattern shifter and measurably better performance was worth it
- lmk if this works for you, and if it doesn't, leave a issue [here](https://github.com/Vertex891/GE-Proton10-34-assetto-corsa/issues)
