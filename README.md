# MBSA, BPA, and SCW

## Lab Overview

This lab involves using tools like Microsoft Baseline Security Analyzer (MBSA), Best Practices Analyzer (BPA), and Security Configuration Wizard (SCW) to assess and enhance security configurations on Windows systems.

## Preparation

1. Ensure Windows 7 VM has both Host Only and NAT adapters.
2. Log in to the Windows 7 VM using the Domain Admin account.

## Lab Tasks and Screenshots

### 1 MBSA Install and Configuration (Windows 7 VM)

- Download and install the MBSA.
- Perform a scan of the local system.
- **Screenshot 1**: Top of the results page showing computer name and Security Update Scan Results.
  
  <img src="https://i.imgur.com/dLcVegu.png" height="400px" width="auto" alt="MBSA Scan Results"/>

### MBSA Analysis

- Review the scan results focusing on areas like Windows Security Updates, Automatic updates, Password expirations, Windows Firewall, and File System.


### MBSA Analysis Questions

1. **Failed Password Expiration Check**: 6 out of 7 accounts failed the expiration check including Administrator, Guest, HomeGroupUser$, User, User-Admin, User-Limited.
2. **Passed Password Expiration Check**: 1 account passed the expiration check.
3. **Windows Firewall Status**: Disabled.
4. **Local Account Password Test**: 2 of 7 accounts have blank or simple passwords. "User-Admin" and "User-Limited" have weak passwords.
5. **Autologon Configuration**: Not configured.
6. **Guest Account Status**: Disabled.
7. **Multiple Administrators**: More than 2 administrators found including ANAMEKE\User-Admin and Administrator.
8. **Potentially Unnecessary Services**: None found.
9. **Shares Available**: ADMIN$, C$, and Users.

### 2 Network Scan Configuration

- Reconfigure VM network settings and perform a network scan.
- **Screenshot 2**: All information below the scan results.
  <img src="https://i.imgur.com/1foB0gY.png" height="400px" width="auto" alt="MBSA Network Scan"/>

### 3 MBSA Command Line Tool

- Use the command line tool to perform a scan and output the results.
- **Screenshot 3**: Output of net config workstation, mbsacli /l command, and the scan command.
  <img src="https://i.imgur.com/Omn3DPo.png" height="400px" width="auto" alt="MBSA Command Line Tool"/>

### 4 Best Practice Analyzer (Server 2008 R2 VM)

- Run BPA on the Active Directory Domain Services Role.
- **Screenshot 4**: Results of the BPA scan.
  <img src="https://i.imgur.com/A1mupaw.png" height="400px" width="auto" alt="BPA Results"/>

### 5 Security Configuration Wizard

- Create and apply a new security policy using SCW.
- Transform the policy to a GPO.
- **Screenshot 5**: Audit policy summary and Group Policy Management Console settings.
  <img src="https://i.imgur.com/kNW3tGN.png" height="400px" width="auto" alt="Security Configuration GPO"/>

### 6. Convert Policy to a GPO and Verify Settings

After creating a security policy using the Security Configuration Wizard, convert it to a Group Policy Object for application and management across the network.

- **Task**: Use the `scwcmd transform` command to convert `INFO6003.xml` Policy to a `INFO6003` GPO.
- **Verification**: Open Group Policy Management Console, navigate to the newly created `INFO6003` GPO, and display its settings, particularly focusing on audit policies.

- **Screenshot 6**: Show your domain, the `INFO6003` GPO, and the audit policy settings.
  <img src="https://i.imgur.com/j7tFNMB.png" height="400px" width="auto" alt="GPO Conversion and Settings"/>






