---
title: Privacy Policy
date:
  created: 2026-01-26
  updated: 2026-01-26
readtime: 5
---

# Privacy Policy

**Effective Date:** January 26, 2026  
**Last Updated:** January 26, 2026

## Introduction

Project Planner is a plugin for Obsidian developed by James Hawkins, a.k.a ArctykDev. This privacy policy explains how Project Planner handles your data and protects your privacy.

## Our Core Commitment

**We do not collect, transmit, or store any of your data on external servers.** Project Planner is built on a foundation of local-first, privacy-focused principles that align with Obsidian's core philosophy.

## Data Storage and Location

### Local Storage Only

All data created and managed by Project Planner is stored **exclusively on your local device** within your Obsidian vault:

- **Primary Data Storage**: `.obsidian/plugins/obsidian-project-planner/data.json`
- **Markdown Task Files**: `{ProjectName}/Tasks/{TaskTitle}.md` (when markdown sync is enabled)
- **Plugin Settings**: Stored within Obsidian's plugin configuration
- **Browser LocalStorage**: Used only for view preferences (e.g., panel split widths)

### No Cloud Services

Project Planner does not:

- Send any data to external servers
- Use cloud storage services
- Connect to remote APIs or databases
- Require internet connectivity to function
- Transmit any information outside your device

## Data Collection

### What We Don't Collect

Project Planner does **not** collect:

- Personal information
- Usage analytics or telemetry
- Task content or project data
- User behavior or interaction data
- Error reports or crash logs
- Device information
- IP addresses or network data

### What Data Stays Local

All data remains within your Obsidian vault, including:

- Project names and structures
- Task titles, descriptions, and metadata
- Status, priority, and tag assignments
- Start dates, due dates, and timestamps
- Task dependencies and relationships
- Subtasks and checkbox lists
- Links and attachments
- Custom bucket and tag configurations

## Data Processing

### On-Device Processing

All data processing occurs locally on your device:

- Task synchronization between JSON and markdown formats
- Metadata parsing and YAML frontmatter processing
- View rendering and visualization (Grid, Board, Timeline, Dashboard, Dependency Graph)
- Search and filtering operations
- Data validation and integrity checks

### Bidirectional Markdown Sync

When **Enable Markdown Sync** is enabled:

- Tasks are written to markdown files in your vault
- Changes to markdown files update the plugin's internal data
- All synchronization happens locally using Obsidian's Vault API
- File watching uses Obsidian's metadata cache events
- No external services are involved in the sync process

### Daily Note Tagging

When **Daily Note Sync** is enabled:

- The plugin scans specified folders in your vault for tagged tasks
- Task detection uses local regex pattern matching
- Imported tasks are added to your project data locally
- No external services are involved in scanning or importing

## Third-Party Services

### None Used

Project Planner does not integrate with or use any third-party services:

- No analytics services (e.g., Google Analytics)
- No crash reporting tools
- No advertising networks
- No social media integrations
- No external authentication providers

## Data Sharing

### We Don't Share Your Data

Because we never access your data in the first place, we cannot and do not:

- Share data with third parties
- Sell or rent your information
- Provide data to advertisers
- Transfer data to service providers
- Disclose data to government entities (unless legally required through your device)

## Your Data Rights

### Complete Control

You have absolute control over your data:

- **Access**: All data is stored in human-readable formats (JSON and markdown)
- **Modification**: Edit task files directly or through the plugin interface
- **Export**: Copy your vault folder to back up all project data
- **Deletion**: Uninstall the plugin and delete the plugin folder to remove all data
- **Portability**: Use standard file system tools to move or copy your data

### Data Backup and Recovery

- **Your Responsibility**: Back up your vault using your preferred method (version control, cloud storage, local backups)
- **Plugin Data**: Included in Obsidian vault backups automatically
- **No Cloud Backup**: Project Planner does not provide cloud backup services

## Data Security

### Local Security

Your data security depends on:

- **Device Security**: Protect your device with passwords, encryption, and security software
- **Vault Encryption**: Consider encrypting your Obsidian vault if needed
- **File Permissions**: Ensure appropriate file system permissions on your device
- **Network Security**: Project Planner doesn't transmit data, but ensure Obsidian Sync (if used) is configured securely

### No Transmission Security Needed

Because Project Planner never transmits data over networks, there are no risks associated with:

- Man-in-the-middle attacks
- Data interception
- Server breaches
- Network eavesdropping

## Children's Privacy

Project Planner does not collect any data from users of any age. The plugin is safe for all users, including children, as it operates entirely locally without any data collection or transmission.

## Obsidian Sync Compatibility

If you use **Obsidian Sync** or other third-party vault synchronization services:

- Project Planner data files are included in your vault sync
- The plugin itself does not control or access sync services
- Refer to Obsidian's or your sync provider's privacy policy for how synced data is handled
- **Recommendation**: Disable "Sync on Startup" setting to prevent duplicate tasks when using Obsidian Sync

## Open Source and Transparency

Project Planner is developed with transparency in mind:

- Plugin source code is available for review
- No obfuscated or hidden functionality
- Community contributions are welcome
- Development is conducted openly through GitHub

## Changes to This Policy

We may update this privacy policy to reflect:

- Changes in data handling practices
- New features or functionality
- Legal or regulatory requirements
- Community feedback

When we make changes:

- The "Last Updated" date will be revised
- Significant changes will be announced through plugin release notes
- Continued use of the plugin constitutes acceptance of the updated policy

## Contact Information

For questions, concerns, or feedback about this privacy policy:

- **Developer**: James Hawkins
- **GitHub**: [https://github.com/ArctykDev](https://github.com/ArctykDev)
- **Plugin Repository**: [https://github.com/ArctykDev/obsidian-project-planner](https://github.com/ArctykDev/obsidian-project-planner)

## Legal Compliance

### GDPR Compliance

Under the General Data Protection Regulation (GDPR):

- Project Planner does not act as a data controller or processor
- No personal data is collected or processed by us
- All data remains under your direct control
- You are the sole controller of your data

### Other Privacy Laws

Project Planner complies with privacy laws including CCPA, PIPEDA, and others by virtue of not collecting, processing, or transmitting any user data.

## Summary

**In short:** Project Planner respects your privacy completely. Your tasks, projects, and data never leave your device. We built this plugin to empower you with professional-grade project management while maintaining absolute privacy and data ownership—consistent with Obsidian's philosophy and our core values.

---

**Last Reviewed:** January 26, 2026  
**Version:** 1.0

