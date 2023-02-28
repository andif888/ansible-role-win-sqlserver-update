# ansible-role-win-sqlserver-update

Ansible Role to install SQL Server Updates on Windows

## Table of content

- [Default Variables](#default-variables)
  - [ps_tools_download_url](#ps_tools_download_url)
  - [ps_tools_filename_zip](#ps_tools_filename_zip)
  - [sql_server_update_download_url](#sql_server_update_download_url)
  - [sql_server_update_download_validate_certs](#sql_server_update_download_validate_certs)
  - [sql_server_update_extract_dir](#sql_server_update_extract_dir)
  - [sql_server_update_install_command](#sql_server_update_install_command)
  - [sql_server_update_install_exe](#sql_server_update_install_exe)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### ps_tools_download_url

Download URL for PSTools.

PSEXEC needs to be used to execute the SQL Server Update Installer

#### Default value

```YAML
ps_tools_download_url: https://download.sysinternals.com/files/PSTools.zip
```

### ps_tools_filename_zip

PSTools Package file name

#### Default value

```YAML
ps_tools_filename_zip: PSTools.zip
```

### sql_server_update_download_url

download url

#### Default value

```YAML
sql_server_update_download_url: https://catalog.s.download.windowsupdate.com/c/msdownload/update/software/updt/2022/09/sqlserver2019-kb5017593-x64_bd8ea599f044e3834b779bd99e8732a92ae869a8.exe
```

### sql_server_update_download_validate_certs

validate ssl certificates when downloading files

#### Default value

```YAML
sql_server_update_download_validate_certs: false
```

### sql_server_update_extract_dir

extract directory

#### Default value

```YAML
sql_server_update_extract_dir: C:\Windows\Temp\sqlupdate
```

### sql_server_update_install_command

Install command

#### Default value

```YAML
sql_server_update_install_command: psexec.exe -accepteula -nobanner -i 1 -s {{ sql_server_update_extract_dir
  }}\{{ sql_server_update_install_exe }} /IAcceptSQLServerLicenseTerms /Action=Patch
  /InstanceName=MSSQLSERVER /quiet
```

### sql_server_update_install_exe

Install filename

#### Default value

```YAML
sql_server_update_install_exe: SQLServer2019-KB5017593-x64.exe
```



## Dependencies

None.

## License

license (GPL-2.0-or-later, MIT, etc)

## Author

andif888
