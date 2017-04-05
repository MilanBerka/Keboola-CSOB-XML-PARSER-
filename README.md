# Keboola-CSOB-XML-PARSER-

**Keboola-CSOB-XML-PARSER-** is highly customized script, that connects to Google Drive (using PyDrive with `settings.yaml` file provided externally through Keboola Configuration JSON) 

## Keboola Config JSON
Keboola Config JSON may looks like this:
``` 
{
"folderNames" : ["Folder1","Folder2"]
"pathToFile":"/./././settings.yaml"}
```

### `folderNames`
is a list of folders on Google Drive containing ZIP files with XML files

### `pathToFiles`
is path to `settings_file` required in PyDrive's Auth Flow. The `settings_file` must have `.yaml` suffix and has following structure:
```
client_config_backend: 'settings'
client_config:
  client_id: "{{CLIENT_ID <- ATTENTION! NEEDS TO BE ADDED FROM GOOGLE CONSOLE}}"
  client_secret: "{{CLIENT_SECRET <- ATTENTION! NEEDS TO BE ADDED FROM GOOGLE CONSOLE}}"

save_credentials: True
save_credentials_backend: 'file'
save_credentials_file: "{{ PATH TO CREDENTIAL FILE (example: /data/in/files/ID_credentials.dat)}}"
get_refresh_token: True

oauth_scope:
  - "{{DETERMINED_SCOPE", (example: https://www.googleapis.com/auth/drive)}}"
  ```
