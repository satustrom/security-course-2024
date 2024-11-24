# H5 assignment

## X. Summaries

This time we joined the HelSec event and were given a task to summarize HelSec presentations. I chose the first two.

### Jos Helmich - Industrial Cyber Security

**Summary:**

- Enisa = The European Union Agency for Cybersecurity
- General EU Laws & Directives:
  - GDPR
  - NIS-2
  - CRA
  - AIA
- When choosing a supplier, would be good to check some security aspects, like minimal password length or products’ cybersecurity level
- Artificial Intelligence Act is new legislative framework. Contains product safety requirements, Data requirements (GDPR), cyber resilience Act

**Thoughts**

- The presentation was quite fast and short, it was quite hard to catch up
- Slides and explanations for them could have been visible a bit longer
- It was interesting to hear about ENISA as I haven't heard about it before

### Heikki ”zokol” Juva - State of Union

**Summary:**

- Two ongoing regulation projects at Traficom: RED (radio equipment directive) and CRA (cyber resilience act)
- Timeline: RED started Q1/2022 and CRA Q2/2024, RED will be enforced Q3/2025, CRA 2027
- Black box testing = was done with new devices without the help of manufacturer
- Testing in the project: How do consumer devices communicate? Why?
- **Case Eagle**, contained IP camera and O2meter/heart rate monitoring sock
- in **Part 1** they tested whether the system forces to update, if device storage is secure, if has vulnerabilities and whether passwords are unique/strong. Only one requirement was unfortunately met (forcing to update).
- in **Part 2** they tested the privacy: If has sensors that may affect the privacy, if user is being notified about privacy policy, is GDPR met and if user can delete all the information from the device. Only one requirement was unfortunately met. For example, after removing all the information from the device, there were still some information stored, such as wifi password
  - Also after some more investigation, there were also sensitive information about the company, such as how much R&D costs are

**Thoughts**

- Heikki's investigation/testing on the device was very interesting, I haven't thought about security and privacy in such devices that much before
- Hopefully there will be more legislation to support customer's right to privacy in such devices in the near future
