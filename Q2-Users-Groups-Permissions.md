## Q2. Users, Groups & Permissions

### Objective

Practiced Linux user management, group management, file/directory ownership, permissions, and access testing using a real-world application directory scenario.

### Users Created

```bash
sudo useradd -m support1
sudo useradd -m devloper
```

### Group Created

```bash
sudo groupadd appteam
```

### Add Users to Group

```bash
sudo usermod -aG appteam support1
sudo usermod -aG appteam devloper
```

### Verify User and Group Membership

```bash
id support1
id devloper
```

### Create Application Directory

```bash
sudo mkdir /opt/appdata
```

### Set Directory Ownership

```bash
sudo chown root:appteam /opt/appdata
```

### Set Directory Permissions

```bash
sudo chmod 770 /opt/appdata
```

Permission meaning:

```text
770 = rwx rwx ---
       Owner Group Others
```

* Owner (`root`) → Full access
* Group (`appteam`) → Full access
* Others → No access

### Test User Access

Checked directory access as `support1`:

```bash
sudo -u support1 ls -ld /opt/appdata
```

Tested file creation as `support1`:

```bash
sudo -u support1 touch /opt/appdata/support-test.ext
```

### Verify File Ownership

```bash
sudo ls -l /opt/appdata/
```

Example result:

```text
-rw-r--r-- 1 support1 support1 support-test.ext
```

### Key Concepts Learned

* Linux users and groups
* Primary and supplementary groups
* File and directory ownership
* `chmod` permissions
* `chown` ownership
* Directory permissions
* Testing access using `sudo -u`
* Real-world application directory access control

### Real-World Scenario

Created an application directory `/opt/appdata` where the `appteam` group has full access while other users have no access. Tested access by running commands as an application/support user.

### Result

Successfully created users and groups, configured directory ownership and permissions, and verified user access through practical Linux commands.
