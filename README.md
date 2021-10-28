# macOS and OpenCore Quick Reference Guide
These are some of my go-to macOS and OpenCore commands, guides, fixes and features I use from time to time in my environment. They act as my quick-reference guide and checklist whenever I need to do any updates, debugging or previous fixes and features I lost.

## Updating OpenCore
<details>
  <summary>Condensed guide on how to update OpenCore.</summary>
  <br>

  Workinonit..
  <br>

  <sup>***Reference: https://dortania.github.io/OpenCore-Post-Install/universal/update.html***</sup>
  <br>
</details>

## Debugging OpenCore
<details>
  <summary>Condensed guide on how to debug OpenCore.</summary>
  <br>

  Workinonit..
  <br>

  <sup>***Reference: https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/debug.html***</sup>
  <br>
</details>

## Disable or enable Gatekeeper
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

## Disable or enable SIP
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

## Remove delay on Dock autohide
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

## Reset all Finder views
<details>
  <summary>Terminal commands to reset all Finder views for either one or all users.</summary>
  <br>

  Workinonit..
  <br>
</details>

## Fix localized system folders
<details>
  <summary>Terminal commands to localize system folder that has not been translated correctly.</summary>
  <br>

  Workinonit..
  <br>
</details>

## Enable HiDPI on a non-retina display
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

## Prevent a volume from mounting at startup
<details>
  <summary>Terminal commands to prevent volumes from mounting at startup.</summary>
  <br>

  Workinonit..
  <br>

  <sup>***Reference: https://discussions.apple.com/docs/DOC-7942***</sup>
  <br>
</details>
