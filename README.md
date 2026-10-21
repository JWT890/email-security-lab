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
So lets go buy a domain from Cloudflare and look for a .com or .org and buy it. After buying, click on manage and go to DNS records/configurations to verify:   
![DNS](./images/dns.png)    
Then go back to Settings -> Domains in 365 and click on add domain and enter the domain that was bought and get here:   
![Verify](./images/verify1.png) 
Since it detects cloudflare the auto method is available but lets click on different options to add a TXT record and hit continue and reach the add a record to verify ownership screen and copy it and go to Cloudflare and click on add record.   
In add record, set the type to TXT, for name type @, and for content put the MS=text that was generated and click on save. 
Then in a command prompt type nslookup -type=TXT jon-maillab.org to see the MS pop up.  
Then go back to 365 and click on verify:    
![Connect](./images/connect.png)    
Choose the Add your own DNS option and get to the Add DNS records screen and since I don't have the Business Basic Standard trial I'll have to get the trial for it to use Exchange so hit continue and add. Shortly after doing this I got the trial. Then assign the license to the admin user and create 2 users with the domain bought and the licenses.    
![Users](./images/users.png)    

