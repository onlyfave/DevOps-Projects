# Project Documentation: Linux User and Group Management

---

## Create Groups

### Groups: `devops`, `aws`

```bash
groupadd devops
groupadd aws
```

---

## Modify User Group Membership

### Change primary group of `user2` and `user3` to `devops`:

```bash
usermod -g devops user2
usermod -g devops user3
```

### Add `aws` group as a secondary group to `user1`:

```bash
usermod -aG aws user1
```

---

## Directory and File Operations

### Create Directory Structure:
Replicate the directory structure shown in your project diagram.

Example:

```bash
mkdir -p /dir1 /dir7/dir10
```

### Change Ownership and Permissions:
Update ownership and group for specific directories and files:

```bash
chown user1 /dir1 /dir7/dir10 /f2
chgrp devops /dir1 /dir7/dir10 /f2
```

---

## Advanced Operations

### File Manipulations as `user1`:

#### Create directories and move/rename files as required:

```bash
mkdir /home/user2/dir1
mv /opt/dir14/dir10/f1 ~user1/
```

#### Write to files using command-line tools:

```bash
echo "Linux assessment for a DevOps Engineer!! Learn with Fun!!" > /f3
```

#### Perform Edits Using `vi`:

Copy, paste, and search/replace operations in `/f3`:

```bash
:1y
:10p
:%s/Engineer/engineer/g
```

---

## AWS Operations

### Create and Manage EBS Volume:
1. Create a 5GB EBS volume in the same AZ as the instance.
2. Attach it to the EC2 instance.
3. Format and mount the volume:

```bash
mkfs.ext4 /dev/xvdf
mount /dev/xvdf /data
df -h
```

---

## Cleanup Operations

### Remove Users and Groups:

#### Delete users and their home directories:

```bash
userdel -r user1
userdel -r user2
```

#### Remove groups:

```bash
groupdel devops
```

### Unmount and Delete EBS Volume:

```bash
umount /data
rm -rf /data
```

### Terminate EC2 Instance:
Detach the volume and terminate the instance in AWS.

---

## Troubleshooting

### Error: "Group not removed because it is still in use."
- **Solution:** Ensure no users are associated with the group before deletion.

### Error: "Permission Denied."
- **Solution:** Check file and directory permissions using `ls -l`.

---

## Conclusion
By completing these steps, you’ve practiced Linux user and group management, file and directory permissions, and AWS EC2 resource management. Repeat the steps as necessary for mastery.



