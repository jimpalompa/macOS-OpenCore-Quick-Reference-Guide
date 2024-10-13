# macOS and OpenCore Quick Reference Guide
These are some of my go-to macOS and OpenCore commands, guides, fixes and features I use from time to time in my environment. They act as my quick-reference guide and checklist whenever I need to do any updates, debugging or previous fixes and features I lost.

### iCloud Drive activity
<details>
  <summary>Terminal commands to restart and monitor iCloud Drive.</summary>
  <br>

  **Terminate and restart the iCloud daemon**
  ```
  killall bird
  ```
  <br>

  **Monitor the iCould syncronisation**
  ```
  brctl monitor -i
  ```
  <br>

  <sup>***Reference: https://apple.stackexchange.com/questions/446479/icloud-sync-problems#answer-448505***</sup>
  <br>
</details>

### Updating OpenCore
<details>
  <summary>Quick guide on how to update OpenCore.</summary>
  <br>

  Workinonit..
  <br>

  <sup>***Reference: https://dortania.github.io/OpenCore-Post-Install/universal/update.html***</sup>
  <br>
</details>

### Debugging OpenCore
<details>
  <summary>Quick guide on how to debug OpenCore with my releases.</summary>
  <br>

  My releases are prepared for easy dubugging, all you have to do is download the DEBUG version of [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg). Reminder, it's a good idea booting the debug EFI from a USB stick.
  
  **Swap the following files:**

  EFI > BOOT > `BOOTx64.efi`<br>
  EFI > OC > `OpenCore.efi`<br>
  EFI > OC > Drivers > `OpenRuntime.efi`

  **Change to the following values in** `config.plist`**:**

  Misc > Debug > AppleDebug > `True`<br>
  Misc > Debug > ApplePanic > `True`<br>
  Misc > Debug > DisableWatchDog > `True`<br>
  Misc > Debug > Target > `67`<br>
  NVRAM > Add > 7C436110-AB2A-4BBB-A880-FE41995C9F82 > boot-args > `-v keepsyms=1`

  Restart computer and make sure you boot from the same volume you made the changes in. Verbose mode is now active and log files will be saved to the same volume. When you're done and everything works, swap back files from the RELEASE version and revert the values in config.plist.

  <sup>***Reference: https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/debug.html***</sup>
  <br>
</details>

### Disable or enable Gatekeeper
<details>
  <summary>Terminal commands to disable, enable or check status on Gatekeeper.</summary>
  <br>

  **Disable Gatekeeper**
  ```
  sudo spctl --master-disable
  ```
  <br>

  **Enable Gatekeeper**
  ```
  sudo spctl --master-enable
  ```
  <br>

  **Check status on Gatekeeper**
  ```
  spctl --status
  ```
  <br>
</details>

### Disable or enable SIP
<details>
  <summary>Terminal commands to disable, enable or check status on SIP (System Integrity Protection).</summary>
  <br>

  First, you have to enter [Recovery Mode](https://support.apple.com/en-us/HT201314), then launch Terminal from the Utilities menu.
  <br><br>

  **Disable SIP**
  ```
  csrutil disable
  ```
  Restart your computer.
  <br><br>

  **Enable SIP**
  ```
  csrutil enable
  ```
  Restart your computer.
  <br><br>

  **Check status on SIP**
  ```
  csrutil status
  ```
  <br>

  <sup>***Reference: https://developer.apple.com/documentation/security/disabling_and_enabling_system_integrity_protection***</sup>
  <br>
</details>

### Remove delay on Dock autohide
<details>
  <summary>Terminal commands to remove or restore the Dock autohide delay.</summary>
  <br>

  **Remove Dock autohide delay**
  ```
  defaults write com.apple.dock autohide-delay -float 0 && killall Dock
  ```
  <br>

  **Restore Dock autohide delay**
  ```
  defaults delete com.apple.dock autohide-delay && killall Dock
  ```
  <br>
</details>

### Reset all Finder views
<details>
  <summary>Terminal commands to reset all Finder views for either one or all users.</summary>
  <br>

  Workinonit..
  <br>
</details>

### Fix localized system folders
<details>
  <summary>Terminal commands to localize system folder that has not been translated correctly.</summary>
  <br>

  Workinonit..
  <br>
</details>

### Always open TextEdit with new document
<details>
  <summary>Terminal commands to start TextEdit with a new document by default.</summary>
  <br>

  **Always open TextEdit with a new document**
  ```
  defaults write -g NSShowAppCentricOpenPanelInsteadOfUntitledFile -bool false
  ```
  <br>

  **Restore to TextEdit default settings**
  ```
  defaults delete -g NSShowAppCentricOpenPanelInsteadOfUntitledFile
  ```
  <br>
</details>

### Enable HiDPI on a non-retina display
<details>
  <summary>Script to simulate macOS HiDPI on a non-retina display, and have a "native" scaled in System Preferences.</summary>
  <br>

  I'm using a [headless dummy plug](https://www.amazon.com/dp/B07YMTKJCR/) to control my builds via screen sharing, which does not have HiDPI enabled by default.
  
  Basically just run this script in Terminal and it will guide you all the way:  
  ```
  bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
  ```
  <br>

  **My preferred options**
  1. Run script in Terminal.
  2. Choose `(2) Enable HIDPI (with EDID)`
  3. Display icon `(6) Do not change`
  4. Resolution config `(5) 3000x2000 Display`
  5. You may need to enter your password.
  6. Restart.
  <br>

  **Disable and reset HIDPI**
  1. Run script in Terminal.
  2. Choose `(3) Disable HIDPI`
  3. Choose `(2) Reset all settings to macOS default`
  4. You may need to enter your password.
  5. Restart.
  <br>

  <sup>***Reference: https://github.com/xzhih/one-key-hidpi***</sup>
  <br>
</details>

### Prevent a volume from mounting at startup
<details>
  <summary>Terminal commands to prevent volumes from mounting at startup.</summary>
  <br>

  Workinonit..
  <br>

  <sup>***Reference: https://discussions.apple.com/docs/DOC-7942***</sup>
  <br>
</details>
