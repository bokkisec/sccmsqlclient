# sccmsqlclient (Extended)

A dedicated MSSQL client for SCCM database exploration and exploitation.
- Recon queries
- Extract secrets
- Manage and impersonate admins
- Run PowerShell scripts on managed clients individually and across device collections

Associated blog post: [https://bokkisec.com/blog/SCCM_MSSQL](https://bokkisec.com/blog/SCCM_MSSQL)

## Credit
- Original tool: [https://github.com/synacktiv/sccmsqlclient](https://github.com/synacktiv/sccmsqlclient)
-  Project idea and mentorship: Garrett Foster (<a href="https://x.com/unsigned_sh0rt">@unsigned_sh0rt</a>)

## Usage
- Run `sccmsqlclient.py` without arguments to get help for connection arguments, then run with arguments to connect to a remote MSSQL server on a SCCM environment.
- After you connect, use `help` to view prebuilt commands or execute raw queries

## Commands 

Extended commands:
- Make sure to specify unique usernames (e.g. domain\username)
```
sccm_show_admins [Name]              - Show SCCM admins (use argument to filter admins)
sccm_add_admin [Username] [Role]     - Add a user to a SCCM admin role
sccm_remove_admin [Username]         - Remove a user from all SCCM admin roles

sccm_impersonate_safe_targ [your_user] [target_user] - Safely impersonate a target admin
sccm_impersonate_safe_full [your_user]               - Safely impersonate the default "Full Administrator"
sccm_impersonate_targ [your_user] [target_user]      - Impersonate a target admin
sccm_impersonate_full [your_user]                    - Impersonate the default "Full Administrator"
sccm_restore_targ [SID_encoded] [target_user]        - Restore target user's SID to the one specified
sccm_restore_full [SID_encoded]                      - Restore default FA's SID to the one specified

collection_run_script [site_id]   - Run powershell script across device collection
collection_list [Name]            - List device collections (use argument to filter collections)
collection_members [site_id]      - Show members of the specified collection

sccm_programs [Name]           - Show installed programs (use argument to filter devices)
sccm_operatingsystems [Name]   - Show operating systems (use argument to filter devices)
```

Original commands:
```
lcd {path}                 - changes the current local directory to {path}
exit                       - terminates the server process (and this session)
show_query                 - show query
mask_query                 - mask query
set_limit                  - set top limit [default 100]

# SCCM
sccm_sites                 - List Sites

sccm_devices [Name]
sccm_devices_bgbstatus [Name]
sccm_devices_status [Name]


sccm_run_script [ResourceID]                      - Run PowerShell script on a given device

sccm_ScriptsExecutionStatus [ScriptGuid | TaskID] - Get the output of script executions
sccm_BGB_Tasks_clean [GUID]                       - Cleans all traces related to a given task
    
sccm_useraccounts [UserName]                      - List User Accounts (NAA, ClientPush)
sccm_add_apps [Name]                              - List Azure AD Application configurations
sccm_decrypt_blob [ResourceID] [HEXBLOB]          - Run script to decrypt secret blob on a Management Point
    

show_ps1_script
set_ps1_script [Content]
load_ps1_script [filename]

    
last_task_info          - Print latest task GUIDs
last_task_output        - Show execution results of the latest Task launched with sccm_run_script
last_task_output_print  - Pretty print the execution's output
last_task_clean         - Clean Task and Script of the last sccm_run_script execution

sccm_set_sitecode [SITE_CODE]

sccm_scripts [ScriptName | ScriptGuid]
sccm_scripts_full [ScriptName | ScriptGuid]
sccm_script_add [ScriptName]
sccm_script_delete [ScriptGuid]
sccm_script_printbody [ScriptName | ScriptGuid]

sccm_BGB_Server [ServerName]

sccm_BGB_Tasks [GUID]
sccm_BGB_Task_add [ScriptGuid]
sccm_BGB_Task_delete [GUID]

sccm_BGB_ResTask [TaskID]
sccm_BGB_ResTaskHistory [TaskID]
sccm_BGB_ResTaskPush [TaskID]
sccm_BGB_ResTaskPushHistory [TaskID]
sccm_BGB_ResTaskPushPending [TaskID]
```

## Requirements
- impacket
