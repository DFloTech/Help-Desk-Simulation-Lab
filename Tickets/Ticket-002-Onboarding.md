# 🧾 Ticket 002 – Account Creation (Onboarding New User)

**Date Opened:** 2025-09-23  
**Priority:** Medium  
**Requested By:** HR – Nursing Department  
**Assigned To:** IT Support Technician  

---

## Description  
HR requested a new Active Directory account for **Mary Poppins**, a new hire joining the **Nursing Staff** team at the Phoenix clinic.  
The account must:  
- Be placed in the **Nursing OU**.  
- Assigned to the **Nursing Staff security group**.  
- Have an email address provisioned (placeholder for Office 365).  
- Require password change at first login.  

---

## Environment  
- **Domain Controller:** DC01 (Windows Server 2022)  
- **Client Machine:** PC01 (Windows 10 Pro)  
- **Tools Used:** Active Directory Users and Computers (ADUC), Group Memberships  

---

## Steps Taken  

1. Logged into **DC01** with administrator credentials.  

   ![Screenshot Placeholder – DC01 login](Screenshots/Ticket002_step1.PNG)  

2. Opened **Active Directory Users and Computers (ADUC)**.  

   ![Screenshot Placeholder – ADUC open](Screenshots/Ticket002_step2.PNG)  

3. Navigated to the **Nursing OU** → Right-click → **New → User**.  
   - First Name: Mary  
   - Last Name: Poppins  
   - User Logon Name: mpoppins  

   ![Screenshot Placeholder – Create User Wizard](Screenshots/Ticket002_step3.PNG)  

4. Set temporary password (`Welcome123!`) and checked **User must change password at next logon**.  

   ![Screenshot Placeholder – Password Options](Screenshots/Ticket002_step4.PNG)  

5. Assigned Mary to the **Nursing Staff security group**.  

   ![Screenshot Placeholder – Group Membership](Screenshots/Ticket002_step5.PNG)  

6. Verified user object exists in AD and replicated properly.  

   ![Screenshot Placeholder – User in ADUC](Screenshots/Ticket002_step6.PNG)  

7. Logged into **PC01** with Mary’s credentials to confirm access.  

   ![Screenshot Placeholder – Login with Temporary Credentials](Screenshots/Ticket002_step7.PNG)  
   ![Screenshot Placeholder – Successful Login](Screenshots/Ticket002_step8.PNG)

---

## Resolution  
- New account for Mary Poppins was created successfully in the Nursing OU.  
- Added to the `Nursing Staff` security group.  
- Verified login on test client machine.  
- Account configured to force password reset at next login.  

---

## Lessons Learned  
- Practiced **end-to-end onboarding process** using ADUC.  
- Reinforced importance of **OU structure** and **group-based access control**.  
- Demonstrated ability to verify account functionality before closing ticket.  

---

## Next Steps / Future Enhancements  
- Automate onboarding with a PowerShell script.  
- Integrate mailbox creation using **Exchange/Office 365 hybrid**.  
- Document a **user termination (offboarding)** ticket for lifecycle management.  