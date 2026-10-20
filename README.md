# email-security-lab

Email security is vital for making sure emails are coming from the right place and good senders based off secure settings. SPF makes sure which mail servers are authorized, DKIM adds a signature so that systems can validate the domain's public key, while DMARC makes sure both are aligned and specifies how each one should handle failures and reporting. 

# Setup
After setting up a Microsoft 365 domain, go to Settings -> Domains and get here:    
![Domain](./images/domain.png)  
And you will be greeted by the add a domain screen, so I'll put jon-myemaillab and click on use this domain:    
![Email](./images/email.png)    
And make sure to add a .com at the end and click on use this domain. Then on the next screen:   
![Verify](./images/verify.png)  
Click on the first option for adding a .TXT option and reach the add a record to verify ownership screen and save the TXT name, value and TTL for freeDNS.  
Then go to freeDNS here: https://freedns.afraid.org/menu/   
And click on subdomains -> Add a Subdomain and get here:    
![Record](./images/record.png)  
Change the type to text, enter in the subdomain details and change the domain, enter the destination as the MS value in "" and enter the codes but I usually reach this:    
![Fail](./images/fail.png)  
