# 5.2 🧪 Lab Instructions — Creating Users and Groups

---

>💬 \*\*Tip:\*\* Paste this study guide into ChatGPT and ask for \*\*more instructions\*\* by specifying:  
>- “Provide step-by-step lab instructions for this objective.”  
>- “Include which Linux distro to use (Debian/Ubuntu or RHEL/Fedora).”  
>- “Show examples of installing, verifying, and managing desktop and server applications.”  
>- “Include minimal command-line practice for package management and development tools.”  
>- “Focus only on what is most important for passing the LPI Linux Essentials exam.”  

>This will prompt ChatGPT to give \*\*practical, exam-focused lab steps\*\* for each section.

---

**Objective:** Learn to create users, assign passwords, manage groups, and verify account details on a Linux system.

---

### Instructions

1. **👤 Create a new user without a home directory**  
   - Open your terminal.  
   - Run the command: `sudo useradd alice`  
   - ✅ Confirm the user was created by viewing `/etc/passwd`:  
     `cat /etc/passwd | grep alice`

2. **🏠 Create a new user with a home directory**  
   - Run: `sudo useradd -m bob`  
   - ✅ Check that the home directory was created: `ls /home`  
   - 📂 Verify default skeleton files were copied: `ls /home/bob`

3. **🖥️ Assign a specific shell and supplementary groups to a new user**  
   - Run: `sudo useradd -m -s /bin/bash -G developers testuser`  
   - 🔍 Confirm shell and group membership: `id testuser`

4. **🔑 Set passwords for users**  
   - Run:  
     `sudo passwd alice`  
     `sudo passwd bob`  
     `sudo passwd testuser`  
   - ✅ Verify password works by switching user: `su - alice` (enter password to log in)

5. **👥 Create a new group and manage memberships**  
   - Run: `sudo groupadd interns`  
   - Add an existing user to the group: `sudo usermod -aG interns bob`  
   - 🔍 Verify membership: `id bob`  
   - 📄 Check group list: `cat /etc/group | grep interns`

6. **📂 Verify user details and system files**  
   - View `/etc/passwd` for all users: `cat /etc/passwd`  
   - View `/etc/shadow` (root only): `sudo cat /etc/shadow`  
   - View `/etc/group` to confirm groups and memberships: `cat /etc/group`

7. **💡 Practice tasks to reinforce learning**  
   - Create at least 2 more users with home directories.  
   - Assign them to different groups and verify using `id username`.  
   - Inspect `/etc/skel/` to see default skeleton files for new users.  
   - Change a user’s password and log in to confirm it works.  
   - Observe UID and GID for all users and note which are system vs. standard users.

**Tip:** ⏱️ Take your time with each step. Confirm each action with verification commands to understand how Linux tracks users and groups.
