# Gophish Phishing Campaign - Learning Project

This project was a learning exercise in setting up a phishing campaign using Gophish, an open-source phishing framework. The project documents how I learned how to install, configure, and execute a simple phishing campaign against my friend.


## Table of Contents
- [Project Setup](#project-setup)
- [Steps for Creating a Phishing Campaign](#steps-for-creating-a-phishing-campaign)
- [Results and Observations](#results-and-observations)
- [Lessons Learned](#lessons-learned)
- [Disclaimer](#disclaimer)

## Project Setup
- **Gophish Version**: v0.12.1 
- **Operating System**: Windows 11
- **Mail Server**: Used Gmail SMTP
- **Landing Page Hosting**: Hosted it locally

### Installation Instructions:
1. Download and install Gophish from [Gophish Downloads](https://getgophish.com/).
2. Configure an SMTP server (e.g., Gmail).
3. Create a phishing email template and landing page.


## Steps for Creating a Phishing Campaign
1. **Install Gophish**:
   - Follow the official installation guide for your OS.
   - Start Gophish by running `./gophish` in your terminal.
   - from the terminal you can then find the login credentials

2. **Set up SMTP**:
   - Use Gmail SMTP with "Less Secure Apps" enabled, if possible.
   - Input the following:
     - Host: `smtp.gmail.com`
     - Port: 587
     - Username: Your Gmail account
     - Password: Your Gmail password
   - OR add an app password to your gmail account.
     - Enable 2-factor authentication
     - Go to settings -> security -> app passwords to generate a unique password for the gophish application.

3. **Create a Sending Profile**:
   - use "smtp.gmail.com" as your host
   - use your email and app password
   - The SMTP From section can be customized to look like a legitimate sender.
     
4. **Create an Email Template**:
   - Go to the Email Templates tab.
   - Write a phishing email with variables for customization (e.g., `{{.FirstName}}`).
   - Add dynamic variables to adress the user, like {{.FirstName}}, {{.LastName}}, or {{.Email}}.
   - Add a {{.URL}} tag if you want to direct users to a landing page.
   - Add images to make it look more real
   - Emphasize urgency
   - Make sure to tick the "Add Tracking Image" box. 

5. **Create a Landing Page**:
   - Set up a simple landing page hosted on Netlify, GitHub Pages, or another platform.
   - The landing page could include a simulated login form or an educational message.
   - If you are in a proffesional setting and have explicit consent then you can tick the "Capture Submitted Data" box (I didn't)

6. **Set up your Users and Groups**:
   - Either import a csv file of emails and accounts or manually input the details of who you wish to fish.

7. **Create a Campaign**:
   - Choose the email template and landing page that you created.
   - Add your target from users and groups (your friend’s email, with permission).
   - Add the url of where the landing page is hosted (preferably on the server that is also hosting Gophish).
   - Set the rest of the parametres and launch.

8. **Monitor Results**:
   - Track email opens, clicks, and any submitted data through the Gophish dashboard.


## Results and Observations
- **Emails Sent**: 1 (to my consenting friend).
- **Open Rate**: 100%.
- **Click Rate**: 100%.
- **User Behavior**: The target clicked on the phishing email but did not submit any credentials, demonstrating awareness of potential phishing attempts and that they are helpfull to the learning exercice.

### Key Insights:
Crafting convincing phishing emails is a complex task that requires balancing realism and ethics.
The closer to realism you go the closer you are at actually copying legitimate emails (like from amazon or other services) to fool potential victims.

As this was just a small project to learn the gophish tool I took many shortcuts and simplyfied the posses to its bare minimum. I also did not wish to land in any legal or ethical trouble.
So, I didn't craft a super convincing email or landing page as I didn't wish to actually fool my consenting friend or the email systems he was using.
I also didn't spoof the sendind email address, or host an online phishing landing page.
Again, the point was to learn the tool and process of launching a phishing campaign.


## Lessons Learned
 - There was/is a bug with Gophish where if you had a custom email name to your sending profile (in the "From SMTP:" section) then testing that sending profile would lead to an error. When using that sending profile for a campaign though it would work just fine.


## Disclaimer
This project was conducted in a controlled and ethical manner with the full consent of the participants. The sole purpose of this project was to learn about phishing and educate others on the importance of phishing awareness. No malicious intent or harm was intended.
