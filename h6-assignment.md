# H6 assignment

## X. Summaries

#### **[Dingledine, Mathewson and Syverson 2004: Tor: The Second-Generation Onion Router](https://css.csail.mit.edu/6.858/2022/readings/tor-design.pdf):**

**3. Design goals and assumptions**

**Goals**: Tor aims to prevent attackers from connecting users to their communications while also evolving based on different needs

- Deployability: Must be affordable, easy to implement, and not burden operators, while not requiring non-anonymous parties, like websites, to run special software
- Usability: Must be easy to use to ensure more users and better anonymity. Tor should work with familiar applications, avoid slowdowns, require minimal setup, and be compatible with common platforms without needing OS changes.
- Flexibility: The protocol should be flexible and well-defined, allowing Tor to support future research without redesigning core features
- Simple design: The protocol should be straightforward and well-understood, avoiding unnecessary complexity to ensure stability, security, and ease of deployment

**Non-goals**: Some goals are deferred due to not being solved or being fixed somewhere else

- Not peer-to-peer: Tor avoids fully decentralized peer-to-peer systems, which still face many unresolved challenges, especially with adversary-controlled servers.
- Not secure against end-to-end attacks: Tor doesn’t fully solve end-to-end timing or intersection attacks
- No protocol normalization: Tor doesn’t normalize protocols like Privoxy or Anonymizer. To hide client differences or protect against identity leaks, Tor must be used with an external proxy
- Not steganographic: Tor does not hide the identities of users connecting to the network.

**Threat Model**: Tor assumes an adversary who can observe, modify, delay, or delete traffic, control some onion routers, or compromise others. The goal is to prevent traffic analysis attacks, where an attacker uses patterns to link users or learn about their behavior. While Tor does not fully protect against strong adversaries, it focuses on defending against attacks like traffic correlation, active manipulation, and attempts to undermine network reliability.

Refererence: Dingledine, Mathewson and Syverson 2004. Tor: The Second-Generation Onion Router. URL: https://css.csail.mit.edu/6.858/2022/readings/tor-design.pdf. Accessed: 2 December 2024.

#### **[Karunanayake, Ahmed, Malaney, Islam and Jha 2021: Tor: De-anonymisation attacks on tor: A survey](https://ieeexplore.ieee.org/ielx7/9739/9621320/09471821.pdf):**

**Abstract**:

- Tor is popular for protecting online privacy but is also misused for illegal activities. This survey reviews attacks on Tor, techniques for de-anonymising users and services, and explores improvements to prevent such attacks

**Introduction**:

- As privacy concerns grow, especially for whistle-blowers and citizens in repressive regimes, anonymous networks have become crucial. Early systems, like Babel, had too high latency, paving the way for faster alternatives
- Tor = The Onion Router project, the most popular low latency anonymity network (so far)
- Tor's main vulnerability is de-anonymisation, and researchers have worked to improve its security in response. As Tor has grown, security improvements have protected it against many legacy attacks.

**Background**:

- Onion Proxy (OP): A small software installed on the user's device that communicates with directory servers, connects to the Tor network, and manages connections for the user's applications. Also called as Tor client
- Directory Servers (DS): Trusted servers which maintain up-to-date information about the networks. OPs download this information to select relays and establish communication circuits
- Entry Node/Guard: The first relay a Tor client connects to and it knows the client’s IP address. Early attacks targeted entry nodes to de-anonymise users. To reduce this risk, Tor introduced guard nodes—trusted relays selected by the client for multiple circuits, reducing the chance of an adversary-controlled entry node being chosen. Guard nodes are assigned based on some factors like network experience, and become eligible after eight days in the Tor network
- Exit Node: The final relay in the Tor circuita and it knows the IP address of the destination server. Since the last layer of Tor encryption is removed here (unless end-to-end encryption like TLS is used), a malicious exit node can potentially observe the traffic passing through it
- Hidden Services (HS) = Onion Services. Tor provides anonymity to users but doesn’t hide the identity of websites they visit. To address this, HS allows websites to be hosted within the Tor network, with addresses ending in .onion. These services protect both the user and the website’s identity. However, HS has also attracted illegal activities, leading law enforcement agencies to target and shut down these services
- Introduction Points: Random nodes selected by a HS to register with Tor. Multiple points are used to prevent DoS (Denial of Service) attacks, and they don't know the HS’s IP, as connections are routed through a Tor circuit
- Rendezvous Points (RPs): A random Tor node selected by the client to connect through a Tor circut, ensuring the RP doesn’t know the client's identity
- Bridges: To prevent censorship by service providers, bridges are Tor relays not listed in the public directory. They replace guard nodes in a circuit and are provided in limited numbers to clients. Bridges allow encrypted connections to censored Tor relays, without the need for middle or exit relays

**Standard Tor Circuit Establishment**:
Tor uses 512-byte fixed-length cells for communication to make traffic analysis harder. There are two types: control cells and relay cells. Control cells issue commands like create or destroy, while relay cells carry end-to-end data and include a relay header with a stream ID, checksum, payload length, and relay command. The header and payload are encrypted using AES-CTR with symmetric keys from Diffie-Hellman key exchange (DHKE)

**Circuit Establishment for Tor HS**:
To connect to a Hidden Service (HS), the HS selects introduction points and advertises its service descriptor via the Directory Server (DS). Users find the HS’s onion address and the OP fetches the descriptor. The OP establishes a circuit to a Rendezvous Point (RP) and sends a message to the HS via the introduction point. The HS creates a circuit to the RP, and communication occurs over a six-hop circuit, keeping the HS’s identity hidden.

**Figure 6**:

- Figure 6 shows happened attacks on tor
- There are four main categories: de-anonymisation attacks, network disruption attacks, censorship attacks, and generic attacks. Figure concentrates on de-anonymisation attacks
- divided into passive (adversary only observes) and active attacks (adversary manipulates the network traffic)

Reference: Karunanayake, Ahmed, Malaney, Islam and Jha 2021. De-anonymisation attacks on tor: A survey. URL: https://ieeexplore.ieee.org/ielx7/9739/9621320/09471821.pdf. Accessed: 2 December 2024.

#### **[Halonen, Ollikainen, Rajala 2023: PhishSticks - The Ethical Hackers tool for BadUSB ](https://www.youtube.com/watch?v=bDzVevtZiWE):**

- PhishStick = a USB stick with a malicious content in it
- When user connects the stick into the computer, malicious code gets installed and the attacker can e.g. log the keyboard and hence steal sensitive information such as password

Reference: Halonen, Ollikainen, Rajala 2023. PhishSticks - The Ethical Hackers tool for BadUSB. URL: https://www.youtube.com/watch?v=bDzVevtZiWE. Accessed: 2 December 2024.

## a. Install TOR

1. Googled "tor browser installation"
2. Chose the link that redirected to the installation page
3. Clicked download button and chose download for Linux, since I am browsing with virtual machine

![image](https://github.com/user-attachments/assets/0ac918f7-7d5d-4e60-93e1-1927c493c3c4)

![image](https://github.com/user-attachments/assets/3060c7b6-1fb6-4703-bd87-be8cc0ca7c8f)

4. Tried to extract the start browser file but it did not work
   ![image](https://github.com/user-attachments/assets/06202b55-ac27-459d-9faf-16218733b1eb)

5. Lost some screenshots and steps, since my virtual machine crashed. I started to install the tor again, but my virtual machine is just slow and TOR won't start

6. Decided to try to install without virtual machine. My testing laptop is ready to go to trash anyway :)

7. Installed the TOR for Windows, and clicked "Finish":

![image](https://github.com/user-attachments/assets/07dc68f0-1603-41c3-94bd-65954b12c807)

8. After clicking the "Finish" button the TOR opened just like that

![image](https://github.com/user-attachments/assets/a8dd935c-0fd5-4068-9038-64bb76523e15)

## b) Browse TOR network

- **Search engine for onion sites**

When the TOR opened, DuckDuckGo was suggested to be used as a search engine:

![image](https://github.com/user-attachments/assets/9e6136fc-5318-45dd-b3dd-db7f40cc202c)

I also tried Ahmia, which seemed to have easier access to onion sites

![image](https://github.com/user-attachments/assets/29f75866-32c3-45aa-973c-1bb3d967b5c2)

- **Human rights or civil rights organization**

I searched with those words in DuckDuckGo and Amnesty was one of the first options.

![image](https://github.com/user-attachments/assets/894d5ce8-bd2d-4fb3-adc1-09ce14f35b35)

(I first landed on "original" amnesty site, but saw this button to move to onion site:)

![image](https://github.com/user-attachments/assets/a31b7be1-1ce8-40c4-8352-0dbebaef165c)

- **Marketplace**

I ended up to this site which had a list of different marketplaces and their onion site links:

![image](https://github.com/user-attachments/assets/22743509-6001-434f-94a3-9056cbb1158d)
However, none of those links worked so I opened Ahmia search engine and searched marketplaces from there. Found this:

![image](https://github.com/user-attachments/assets/eeb36f70-cb83-40b5-8a4e-c464a3636fed)

- **Fraud**
  My thought is that TOR is quite full of frauds. Teacher showed during the class that every single "serial killer" site is fraud, so I don't think I need a screenshot of such site here.

- **Forum**

Searched forums from Ahmia and I found this "hackers room":

![image](https://github.com/user-attachments/assets/67737845-f2b2-4da9-a0d7-86c5bfbedc19)
It doesn't seem to be that popular since there is only one online (me? :D)

- **A well known organization (with regular postal addresses, offices or similar presence outside darknet)**

Maybe New York times magazine fits for this section?:

![image](https://github.com/user-attachments/assets/3527c4e9-40c7-43fe-bdbb-389919937442)

## c) Onion

- Anonymity in Tor works by routing traffic through multiple relays in a layered encryption system, making it difficult for anyone to trace a user's activity back to them. When a user connects to Tor, their traffic is encrypted multiple times with different public keys as it passes through a series of relays. Each relay decrypts one layer of encryption to reveal the next hop, but no relay knows both the origin and destination of the traffic. (Amanda_James_Min, 2020)

- Tor uses public key cryptography for this process, particularly with Diffie-Hellman key exchange to establish shared symmetric keys between relays. For the actual encryption, Tor uses AES in Counter mode (AES-CTR) to encrypt the data, ensuring its confidentiality and integrity. The traffic is split into fixed-length cells, each containing a small piece of the data and encrypted headers that route it correctly. This layered encryption and random routing make it extremely difficult for an adversary to track the user's identity or the sites they visit. (Karunanayake, Ahmed, Malaney, Islam and Jha, 2021)

References:
Amanda_James_Min 2020. Understanding the Tor Network. URL: https://medium.com/systems-and-network-security/understanding-the-tor-network-b9bf5ffca226. Accessed: 2 December 2024.

Karunanayake, Ahmed, Malaney, Islam and Jha 2021. De-anonymisation attacks on tor: A survey. URL: https://ieeexplore.ieee.org/ielx7/9739/9621320/09471821.pdf. Accessed: 2 December 2024.

## d) What kind of the threat models could TOR fit?

Tor could for example fit Global active adversary because of its actions to prevent denial of service. In Global active adversary an attacker not only monitors the traffic (passive attack) but also can actively manipulate or disrupt it (e.g., by compromising nodes, injecting traffic, or launching denial-of-service (DoS) attacks). Tor tries to defence these with entry/guard nodes, circuit-based encryption and bridges: entry/guard nodes help mitigate risks where an adversary controls entry points and tries to intercept traffic, circuit-based encryption ensures that even if a node is compromised, the attacker cannot easily compromise the entire network, and bridges help evade censorship by hiding the IP addresses of relays.

Reference:
Karunanayake, Ahmed, Malaney, Islam and Jha 2021. De-anonymisation attacks on tor: A survey. URL: https://ieeexplore.ieee.org/ielx7/9739/9621320/09471821.pdf. Accessed: 2 December 2024.

## e) Don't stick that stick

- Attacker could for example switch original USB stick with one that has malicious code in it and when it's being connected to the computer, attacker will be able to get into sensitive information, such as passwords, bank accounts, and why not business secrets
- In my opinion anything could happen with this kind of attack if the victim does not notice anything before it's too late
- Risk could be mitigated by not using any kind of USB sticks at all since the data can be transferred other ways too
