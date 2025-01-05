
# Installation Guide: Nerd Font and Starship

Follow these steps to set up JetBrains Mono Nerd Font and Starship prompt for your terminal.

## Step 1: Install Nerd Font
Starship works best with a Nerd Font for symbols and special characters. We recommend JetBrains Mono Nerd Font.

### 1.1 Download JetBrains Mono Nerd Font
1. Visit the [JetBrains Mono Nerd Font GitHub Releases](https://github.com/ryanoasis/nerd-fonts/releases).
2. Download the latest version of the font (e.g., `JetBrainsMono.zip`).

### 1.2 Install the Font
1. Extract the downloaded ZIP file.
2. Open the folder and select all font files (e.g., `JetBrainsMonoNerdFont-Regular.ttf`).
3. Right-click the selected files and choose **Install**.

### 1.3 Set the Font in Your Terminal
1. Open your terminal (e.g., Windows Terminal, PowerShell, or another application).
2. Go to the settings and set the newly installed font (`JetBrains Mono Nerd Font`) as the default font.

## Step 2: Install Starship
### 2.1 Download and Install Starship
1. Open PowerShell as Administrator.
2. Run the following command to install Starship using Winget:

   ```powershell
   winget install --id Starship.Starship
   ```

   Alternatively, install Starship with a PowerShell script:

   ```powershell
   Invoke-Expression (Invoke-WebRequest -Uri "https://starship.rs/install.ps1" -UseBasicParsing).Content
   ```

3. Confirm the installation when prompted.

## Step 3: Configure PowerShell Profile
### 3.1 Create a Profile File (if not already present)
Run the following command to create a profile file:

```powershell
New-Item -ItemType File -Path $PROFILE -Force
```

### 3.2 Add Starship to the Profile
1. Open the profile file:

   ```powershell
   notepad $PROFILE
   ```

2. Add the following line to initialize Starship:

   ```powershell
   Invoke-Expression (&starship init powershell)
   ```

3. Save the file and close the editor.

## Step 4: Adjust Execution Policy (if needed)
To allow PowerShell scripts to run, adjust the execution policy.

1. Check the current policy:

   ```powershell
   Get-ExecutionPolicy
   ```

2. If the policy is set to `Restricted`, change it to `RemoteSigned`:

   ```powershell
   Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

## Step 5: Restart PowerShell
Close and reopen PowerShell. Starship should now be correctly loaded, displaying your new prompt.

## Step 6: Configure Starship (Optional)
Starship can be customized via a configuration file located at:

```bash
~/.config/starship.toml
```

You can create a custom configuration or refer to the [official Starship documentation](https://starship.rs/config/) for guidance.

## Step 7: Troubleshooting
If Starship does not work as expected, check the following:

1. Is Starship installed?

   ```powershell
   starship --version
   ```

2. Is the path to Starship in the PATH environment variable?

   ```powershell
   Get-Command starship
   ```

3. Are the logs helpful?

   ```powershell
   starship diagnose
   ```
