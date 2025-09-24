# 🧾 Ticket #003 – Outlook Setup (New Hire Account)

**Date Opened:** 2025-09-23  
**Priority:** Medium  
**Requested By:** New Hire – Mary Poppins (mpoppins@lab.local)  
**Assigned To:** IT Support Technician  

---

## Description  
User reported they were unable to log into Outlook on workstation **PC02** after onboarding. Outlook prompted for credentials repeatedly and failed to connect to the mail server.  

---

## Environment  
- **Domain Controller:** DC01 (Windows Server 2022)  
- **Client Machine:** PC02 (Windows 10 Pro)  
- **Mail Server (Simulated):** DC01 acting as placeholder for Exchange (`ex01.lab.local`)  
- **Tools Used:** Outlook 2019 client, Command Prompt, Active Directory Users and Computers (ADUC)  

---

## Steps Taken  

1. Verified user identity via phone before troubleshooting.  
   ![Screenshot Placeholder – User Verification](Screenshots/Ticket003_step1.PNG)  

2. Verified network connectivity by pinging the **mail server** from **PC01**.  
   - Command:  
     ```cmd
     ping ex01.lab.local
     ```  
   - Simulated Exchange by pointing `ex01.lab.local` to **DC01** in DNS.  
   - Confirmed replies were received.  

   ![Screenshot Placeholder – Ping Mail Server](Screenshots/Ticket003_step2.PNG)  

3. Logged into **DC01** with `helpdesk1` and confirmed `mpoppins` account was active in ADUC.

   ![Screenshot Placeholder – Verify AD Account](Screenshots/Ticket003_step3.PNG)  

4. (Simulation) Outlook not currently installed on PC02.  
   - In a real environment: Open **Control Panel → Mail (Microsoft Outlook)** or run `control mlcfg32.cpl`.  
   - Add a new Outlook profile for `mpoppins@lab.local`.  
   - Since Outlook is not installed in the lab, this step is documented for process demonstration only.

   ![Screenshot Placeholder – Outlook Profile](Screenshots/Ticket003_step4.PNG)    

5. On **PC02**, opened **Mail Setup – Outlook** (normally found in Control Panel → Mail) and added a new Outlook profile for `mpoppins@lab.local`.  
   - (Simulation: Outlook not installed in lab, step documented for process demonstration.)  

   ![Screenshot Placeholder – Outlook Profile Setup](Screenshots/Ticket003_step5.PNG)  

6. (Simulation) Launched Outlook and confirmed mailbox initialization completed without errors.  
   - In production: User would log in, mailbox would sync, and a test message could be sent/received.  
   - In the lab: Step documented conceptually since Outlook isn’t installed.  

   ![Screenshot Placeholder – Outlook Success](Screenshots/Ticket003_step6.PNG)  
 

---

## Resolution  
- Outlook successfully configured for `mpoppins@lab.local` on PC02.  
- User confirmed ability to log in, send, and receive email.  

---

## Lessons Learned  
- Even without a full Exchange deployment, DNS aliasing can simulate real-world mail connectivity tests.  
- Always validate network/DNS connectivity before deeper application troubleshooting.  
- Outlook setup is one of the most common help desk tickets — documenting step-by-step adds real value.  

---

## Next Steps / Future Enhancements  
- Add a lightweight **mail server simulation** (hMailServer or MailEnable) for realistic email testing.  
- Automate Outlook profile creation via PowerShell or Group Policy for onboarding.  
- Expand testing to include **mobile device setup** for lab domain email accounts.  
