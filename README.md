# GE-Proton10-34-assetto-corsa

## Setup instructions for installing Assetto Corsa with Content Manager and Custom Shaders Patch (latest preview working) running GE-Proton 10-34 for better performance... and because I can't live without my shifter.  

### *Based on and depends on Sihawido's script found [here](https://github.com/sihawido/assettocorsa-linux-setup)*

*From here I will refer to Assetto Corsa as AC, Content Manager as CM, and Custom Shaders Patch as CSP.

### Section 1: Using the script.

1. Install AC through steam.
  
2. Use protonup-qt ```$ yay -S protonup-qt``` to install GE-Proton 10-34.
  
  - You don't need to install GE-Proton 9-20, the script will handle that in the next steps.

<img width="360" height="111" alt="Screenshot_2026-05-20_22 02 56" src="https://github.com/user-attachments/assets/f40d0619-b98f-4c8a-b444-00f44be94e0b" />

  - You may need to reboot after this step.

3. Visit the repository above and grab the script, you can use the script by copying the curl command there and pasting it in terminal.

4. Run the script.
    
    - It should find your game directory automatically. Type `y` and press `enter`.
      
    - When it asks if you want to install GE-Proton 9-20, type `y` and press `enter`.

5. It will now ask you to close steam, relaunch it, and run AC to generate a new wine prefix.

    - Restarting steam is important! 

      - Tip: Make sure that GE-Proton 9-20 is set in compatibility tab before you do first launch.
          *Right click on the game in your library and click properties / compatibility.*
          *You should see GE-Proton 9-20 and GE-Proton 10-34 on the list.*
          *If neither GE-Protons show up after restarting steam, reboot and they should appear.*  

          >**IMPORTANT:**  
          >**FIRST LAUNCH IS GOING TO TAKE A WHILE.**  
          >It may appear nothing is happening but let it go until you get to the AC main menu.  

6. Close AC and rerun the script in terminal.
    
    - Again it should find your game directory automatically. Type `y` and press `enter`.
      
    - When it asks you to reinstall GE-proton 9-20, type `n` and press `enter`.
      
    - When it asks you if you want to delete the existing wine prefix, type `n` and press `enter`.
      
    - When it asks you to install CM, type `y` and press `enter`.
      
    - When it asks you to install CSP, type `y` and press `enter`.
       
       - Installing the CSP fonts can take a few minutes, just let it run.
      
    - When it asks if you want to resolve input mapping issues, type `n` and press `enter`.
      
    - When it asks to install dxvk, type `y` and press `enter`.

7. Launch AC from steam and it should open CM and ask for your game directory.
    
    - Your game directory will likely be in `/home/yourname/.local/share/Steam/steamapps/common/assettocorsa` replacing /yourname/ with your username.

      >**Add a Z: to the beginning when relating to CM. For example: `Z:/home/yourname/.local/share/Steam/steamapps/common/assettocorsa`** *This is how proton's filesystem detects your root drive.*

    - Install 7zip and fmod plugins and click `ok`, and immediately go to settings/content manager/appearance and tick these boxes to fix the graphical artifacting. Don't let CM restart, close it and relaunch, it will apply CM updates at that time.
    
      <img width="412" height="119" alt="gitssCM" src="https://github.com/user-attachments/assets/5d40e2b5-3c91-456c-8526-5c102b6fbbe0" />

8. Join a public server requiring CSP to ensure no CSP errors. If you receive a failed to patch AC error from CSP, the only know fix is to reinstall AC.

### Now the game should work fine for some of you, but on GE-Proton 9-20, my generic shifter isn't recognized and performance is poor. So now we'll configure GE-proton 10-34.  

### Section 2: Configuring GE-Proton 10-34

1. Go back to AC's compatibility settings and switch to GE-Proton 10-34.

>AFTER THIS STEP DO NOT LAUNCH THE GAME UNTIL THE END OF THE GUIDE OR IT WILL GENERATE A COMPLETELY NEW WINE PREFIX AND YOU WILL LIKELY HAVE TO REINSTALL.

2. Install protontricks ```$ sudo pacman -S protontricks``` and launch it.
   - It will have some errors, close them or click `no`.

3. Click `Assetto Corsa` and click `ok`.

4. Click `select the default wineprefix` and click `ok`.

5. Click `install a windows component or dll` and click `ok`.

6. Scroll through and select all cached items and click `ok`.

   - Installing these may take a while as well.

7. Click `run winecfg` and click `ok`.

8. Go to the libraries tab and in the new override textbox type `dwrite` and click `add`.

9. Scroll to dwrite in the menu and ensure it says `dwrite (native, builtin)` and click `apply` and `ok`.

10. Run AC from steam.

### Now the game should work running GE-Proton 10-34 with CSP working with better performance and usb device compatibility.

### Note:

- You can install cars and maps through CM but if you want other CSP versions you can download the lightspatch and extract it to the game directory. You'll also have to restart CM after installing anything for it to be recognized.

- Only tested on latest cachyOS kernel. (Linux 7.0.9-1-cachyos x86_64).

- I wasted a lot of time trying to get 10-34 working, and honestly the h pattern shifter and measurably better performance was worth it

- LMK if this works for you, and if it doesn't, leave an issue for me to check out [here](https://github.com/Vertex891/GE-Proton10-34-assetto-corsa/issues)

### Common Problems:

- Preview images aren't showing up (section 1, step 7), make sure to use the Z:/.
