# H7 assignment

## X. Summaries

I spent quite significant amount of time on finding an article that is somewhat interesting, new enough, is peer-reviewed, can be found from JUFO with a number between 1-3 AND is free to read. Many interesting articles were sadly behind a paywall. 
Finally made it and decided to read **[A Comprehensive Survey: Evaluating the Efficiency of Artificial Intelligence and Machine Learning Techniques on Cyber Security Solutions](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10403908)** (JUFO rating 1, released in 2024, found from Google Scholars)

Update: I got a feedback that my article was not a review article but here's a screenshot to prove that I used "Review articles" filter on and there were article that I chose...:

<img width="1089" alt="Screenshot 2024-12-08 at 17 37 05" src="https://github.com/user-attachments/assets/fbae535e-e78b-4b4b-99d9-c574650d196a">


### Summary

As technology becomes more integrated into daily life, it brings conveniences but also increases cybersecurity risks. The rapid growth of data and sophisticated hackers with advanced knowledge make securing systems more challenging.
- High-profile cyberattack example: Colonial Pipeline Ransomware (2021), A ransomware attack caused fuel shortages in the U.S. by targeting the pipeline's operations.

**Machine Learning (ML) in Cybersecurity**
Key Benefits:

- Improved Accuracy: ML can process large volumes of data and recognize complex patterns that might be difficult for human analysts to identify. => improves threat detection accuracy
- Faster Detection: ML analyzes data in real time => fast identification and response to threats
- Automation: ML automates time-consuming tasks such as monitoring and threat detection
- Scalability: ML algorithms can scale to analyze large datasets, making them ideal for handling extensive cybersecurity operations, especially in large enterprises

Limitations:

- Data Quality: ML models rely on high-quality data. Predictions could be flawed if the training data is inaccurate or incomplete
- Complexity: Some ML models are very complex making it challenging for cybersecurity professionals to understand why certain decisions were made by the algorithm
- Vulnerability to Attacks: ML systems can be vulnerable to adversarial attacks (attackers manipulate data to bypass detection by the algorithm)

How ML is currently being used:

- Intrusion Detection: ML algorithms monitor network traffic and detect abnormal patterns that may indicate cyber threats. For example, identifying unusual traffic indicative of a Distributed Denial of Service (DDoS) attack
- Malware Detection: ML models classify and identify malware by analyzing its behavior or characteristics. Supervised learning models can e.g. detect new malware by comparing it with known malware patterns in a training dataset
- Fraud Detection: ML is used to detect fraudulent activities, particularly in financial transactions. By analyzing transaction patterns, ML can identify suspicious behaviors and flag potential fraud

----

**Evaluation of ML Based Methods That Used in Cybersecurity Field**

I chose some evaluations that I was able to understand without going too deep in the machine learning world:

Cloud-based DDoS Attack Detection
- Core Concept: ML methods detect DDoS attacks in cloud environments using data from cloud server hypervisors and virtual machines
- Pros: The system successfully detects over 99.7% of DDoS attacks without degrading performance
- Cons: Limited to cloud-based systems, might not generalize well to all environments

IoT Security with Machine Learning
- Core Concept: Detects IoT network attacks
- Pros: The new dataset and novel features lead to stronger attack detection, improving IoT network security
- Cons: Dataset may not cover all types of IoT device vulnerabilities

DDoS Mitigation with Multi-Class Classifiers
- Core Concept: A multi-class classifier for identifying specific DoS/DDoS attacks using the Bot-IoT dataset.
- Pros: Achieves 99.81% accuracy in identifying and mitigating DDoS attacks.
- Cons: Focuses only on certain types of attacks, which may limit its broader applicability.

----

Reference:
Ozkan-Ozay, M., Akin, E., Aslan, Ö., Kosunalp, S., Iliev, T., Stoyanov, I. and Beloev, I., 2024. A Comprehensive Survey: Evaluating the Efficiency of Artificial Intelligence and Machine Learning Techniques on Cyber Security Solutions. URL: https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10403908
