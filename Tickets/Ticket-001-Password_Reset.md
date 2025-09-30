# 🧾 Ticket 001 – Password Reset

**Date Opened:** 2025-09-21  
**Priority:** High  
**Requested By:** Clayton Kershaw (ckershaw@lab.local)  
**Assigned To:** IT Support Technician  

---

## Description  
User reported being unable to log into **PC01** workstation due to a forgotten password. Account appeared locked out after multiple failed attempts.  

---

## Environment  
- **Domain Controller:** DC01 (Windows Server 2022)  
- **Client Machine:** PC01 (Windows 10 Pro)  
- **Tools Used:** Active Directory Users and Computers (ADUC), Remote Desktop  

---

## Steps Taken  

1. Verified user identity via phone before proceeding and log in error.  
   ![Screenshot Placeholder – User Verification](Ticket001_step0.PNG)
   ![Screenshot Placeholder – User Log in Error](Screenshots/Ticket001_step1.PNG)  

2. Logged into **DC01** using RDP with `helpdesk1` account.  
   ![Screenshot Placeholder – RDP to DC01](Screenshots/Ticket001_step2.PNG)  

3. Opened **Active Directory Users and Computers (ADUC)**.  
   ![Screenshot Placeholder – ADUC Console](Screenshots/Ticket001_step3.PNG)  

4. Located `ckershaw` account → **Right-click → Reset Password**.  
   - Temporary Password: `TempPass123!`  
   - Checked **User must change password at next logon**.  
   ![Screenshot Placeholder – Password Reset in ADUC](Screenshots/Ticket001_step4.PNG)  

5. Confirmed user used temporary password and set a new password.  
   ![Screenshot Placeholder – Unlock Account](Screenshots/Ticket001_step5.PNG)  

6. Confirmed user was able to log in at **PC01**.  
   ![Screenshot Placeholder – User Login Success](Screenshots/Ticket001_step6.PNG)  

---

## Resolution  
- Password for **Clayton Kershaw** was reset successfully.  
- Account unlocked and configured for password change at next logon.  
- User confirmed successful login and regained access to workstation and O365 resources.  

---

## Lessons Learned  
- Always verify user identity before performing account changes.  
- Document password resets for compliance and auditing.  
- Ensure temporary passwords comply with domain security policy.  

---

## Next Steps / Future Enhancements  
- Explore **self-service password reset (SSPR)** to reduce help desk workload.  
- Automate routine password reset/unlock operations with **PowerShell scripts**.  