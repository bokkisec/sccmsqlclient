# sccmsqlclient (Extended)

Fork of [https://github.com/synacktiv/sccmsqlclient](https://github.com/synacktiv/sccmsqlclient) with extended features.

A dedicated MSSQL client for SCCM database exploration and exploitation.
- Recon queries
- Run PowerShell scripts on managed clients
- Extract secrets

## Usage 

Extended commands:
```
sccm_add_admin [Username] [Role]     - Add a user to a SCCM admin role
sccm_remove_admin [Username]         - Remove a user from all SCCM admin roles

sccm_impersonate_safe [your_user] [target_user]     - Safely impersonate a target admin
sccm_impersonate_full [your_user]                   - Impersonate the default "Full Administrator"
sccm_impersonate_targeted [your_user] [target_user] - Impersonate a target admin
```

## Requirements
- impacket