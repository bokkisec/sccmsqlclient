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
sccm_remove_admin [Username] [Role]  - Remove a user from a SCCM admin role
```

## Requirements
- impacket