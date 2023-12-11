**Network File Shares & Permissions Lab Steps**

1. **Create Sample File Shares with Permissions**
   - Connect to DC-1 as domain admin (mydomain.com\jane_admin).
   - Log into Client-1 as a normal user (mydomain\<someuser>).

2. **Set Up Folders on DC-1**
   - On C:\ drive of DC-1, create folders: “read-access,” “write-access,” “no-access,” “accounting.”
   - Assign permissions for "Domain Users" group:
     - “read-access”: Read permissions.
     - “write-access”: Read/Write permissions.
     - “no-access”: Read/Write permissions (for "Domain Admins").

3. **Test Access as Normal User**
   - On Client-1, go to shared folder (\\dc-1).
   - Attempt access to the created folders. Observe access and create permissions.

4. **Create "ACCOUNTANTS" Security Group**
   - On DC-1, in Active Directory, create a group named “ACCOUNTANTS.”
   - Set permissions for "ACCOUNTANTS" on the “accounting” folder: Read/Write.

5. **Test Access for Accountants**
   - On Client-1 as <someuser>, try to access “accounting” folder (should fail).
   - Log out, make <someuser> a member of “ACCOUNTANTS” on DC-1.
   - Log in as <someuser> on Client-1 and try accessing the “accounting” share (verify if it works now).
