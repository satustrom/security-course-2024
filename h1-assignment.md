# H1 assignment

## X. Summaries

#### **[Hutchins et al 2011: Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains](https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf):**

- APT = Advanced Persistent Threat, focused on compromising data to gain economic or military advantages
- The "kill chain" is a model that describes the steps an attacker will follow during an intrusion. By analyzing each stage, defenders can disrupt the attack at any point, preventing the adversary from reaching their goal
- CND = Intelligence-driven computer network defense, a risk management strategy with a focus on understanding and countering threats by analyzing adversaries: their goals, capabilities, strategies and weaknesses
- Indicator is crucial part of the kill chain model. Indicator describes the intrusion and its type can be atomic, computed or behavioral
- Kill chain consists of following seven steps:
  - **Reconnaissance**, researching and finding a target
  - **Weaponization**, creating a deliverable package that contains a remote access trojan and an exploit
  - **Delivery**, delivering the package to the victim host
  - **Exploitation**, triggering the attacker's code
  - **Installation**, installing the package
  - **C2** = Command and control, enabling the interaction with the victim host
  - **Actions on Objectives**, collecting/encrypting/extracting information from the victim's host
- Defenders should move their detection and analysis up the kill chain and
  implement courses of actions through the kill chain.
- Defenders should perform campaign analysis, finding the patterns and behaviors of adversaries, their tactics, techniques and procedures. This way defenders will be able to understand how they operate. Another reason for campaing analysis is to understand the intent of the adversary.

Reference: Hutchins et al 2011. Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains. URL: https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf. Accessed: 26 October 2024.

---

#### **[Darknet Diaries, EP 1: The Phreaky World of PBX Hacking:](https://darknetdiaries.com/transcript/1/)**

- PBX = Private Branch Exchange, an internal telephone network
- VOIP phones = Voice-over IP phones = instead of old telephone system, the phone is plugged into the regular office network
- PBX Hacking = A hacker sets up call forwarding to a company's VOIP phone PBX system so that the phone calls get forwarded to the hacker's own expensive numbers and is able to charge the company for it. Hackers use robo-dialers and therefore can make enormous amounts of phone calls in company's phone bill
- Vulnerabilities in the VOIP = company's ineptitude to configure the PBX safely, is allowing this kind of hacking to happen
- Securing a PBX is quite complicated since it must be on the interned in order to receive incoming calls, also some workers have the system at home which complicates the set up even more
- It is hard to catch PBX Hackers for many reasons, for example forwarderd calls are most often dialed to foreign countries and the police are not equipped to hadle international crimes
- Farhan Arshad and Noor Aziz Uddin were arrested for PBX hacking in Pakistan in 2015, but there are still thousands of other PBX hackers free without any idea who and where they are

Reference: Darknet Diaries, 2017. EP 1: The Phreaky World of PBX Hacking. URL: https://darknetdiaries.com/episode/1/. Accessed: 26 October 2024.

---

### **[MITRE ATT&CK FAQ](https://attack.mitre.org/resources/faq/)**

- Tactic means "why", tactical goal, and the reason to execute an action. For example, the adversary is trying to run malicious code
- Technique means "how", the way to reach the tactical goal. For example, the adversary may use cloud management services to run commands within VM (virtual machine)
- Procedure means a particular implementation that the adversary uses for technique. For example, adversary run commands on Azure VMs using the VM Agent

Reference: MITRE ATT&CK. FAQ. URL: https://attack.mitre.org/resources/faq/. Accessed: 26 October 2024.

---

## A. Cyber Kill Chain <> ATT&CK Enterprise Matrix

### How would you compare Cyber Kill Chain and ATT&CK Enterprise matrix?

- Cyber Kill Chain is a high-level document of describing the steps through intrusion. ATT&CK Enterprise matrix on the other hand seems to give rather detailed examples of what kind of tactics or techniques or procedures the adversary might use while going down the kill chain.

### Who do you think could benefit from these models?

- I think every organization or employee in IT industry. These models could be used for example to improve business' current security level or help to implement safer IT solutions

## B. Pick a security incident and learn about it

### **[Cyber Security Sauna: Breaking Views – The Vastaamo case](https://www.youtube.com/watch?v=2qqKcke20cM)**

- A data breach of Finnish Psychotherapy provider Vastaamo in 2020. A guy with a nick name of "ransomman" stole the whole patient data by hacking into the Vastaamo's database at least twice. There were 31 980 records in the database. A year after the breach the hacker tried to extort money from Vastaamo and later on from the victims. The hacker also released a parts of the data as a threat to the dark web and later on accidentally his whole server that contained all stoled Vastaamo data but also evidents to catch him.
- Mr Kivimäki is being arrested for the case. He has 10-year history of various hacks
- Database was built by Vastaamo and was not well secured, admins had enabled remote access to the server. The database didn't have a password, meaning that the root account was there free to take over.
- Vastaamo went to bankrupt because of the breach

## C. Installing Debian on Virtualbox

**Steps I did to install..**

1. Opened my old HP ProBook laptop (Windows) and decided to install Debian there instead of my rather new M1 Mac.
2. Followed a link in the instruction page and downloaded debian live 12.7.0, amd64, xfce version
3. Followed a link to install VirtualBox and chose the Windows installer
4. Starting the VirtualBox installation failed because of missing Microsoft Visual C++ 2019 version, I installed that (X64 architecture)
5. Got a warning that I would need Python core package and win32api in order to properly use VirtualBox, so I installed Python for now
6. Started VirtualBox installation
7. VirtualBox got successfully installed :)
8. I also followed the instructions to create the virtual machine and to insert Debian ISO Image as a Virtual CDROM.
9. Also Booting worked but the main menu looked a bit different.
