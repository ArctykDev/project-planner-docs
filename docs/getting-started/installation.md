---
title: Installing Project Planner
date:
  created: 2026-01-15
  updated: 2026-01-15
---

# Installing Project Planner

Project Planner is currently available for Obsidian Desktop. There are two supported ways to download and install Project Planner in Obsidian.

## Install Project Planner manually

1. Download the latest release from the [Project Planner GitHub repository](https://github.com/ArctykDev/obsidian-project-planner/releases)

   - Download `main.js`, `manifest.json`, and `styles.css` from the latest release

2. Navigate to your Obsidian vault's plugins folder:

   - Open Obsidian and go to **Settings** → **General** → **About**
   - Click the folder icon next to "Vault location" to open your vault folder
   - Navigate to `.obsidian/plugins/` (create the `plugins` folder if it doesn't exist)

3. Create a new folder named `obsidian-project-planner` inside the plugins directory

4. Copy the downloaded files (`main.js`, `manifest.json`, and `styles.css`) into the `obsidian-project-planner` folder

5. Restart Obsidian or reload the app (Ctrl/Cmd + R)

6. Enable the plugin:
   - Go to **Settings** → **Community plugins**
   - Find "Project Planner" in the list
   - Toggle it on

## Install Project Planner using Obsidian BRAT community plugin

[BRAT (Beta Reviewers Auto-update Tester)](https://github.com/TfTHacker/obsidian42-brat) is a community plugin that allows you to install and test beta plugins directly from GitHub repositories.

1. Install the BRAT plugin (if not already installed):

   - Go to **Settings** → **Community plugins** → **Browse**
   - Search for "BRAT"
   - Click **Install**, then **Enable**

2. Add Project Planner to BRAT:

   - Go to **Settings** → **BRAT**
   - Click **Add Beta plugin**
   - Enter the repository URL: `ArctykDev/obsidian-project-planner`
   - Click **Add Plugin**

3. Enable Project Planner:
   - BRAT will automatically download and install the plugin
   - Go to **Settings** → **Community plugins**
   - Find "Project Planner" in the list
   - Toggle it on

!!! tip
BRAT will automatically check for and install updates to Project Planner, keeping you on the latest version.

## Take your first steps

Now that you've installed Project Planner, you are ready to [take your first steps](first-steps.md).
