# Malicious Software

## The CIA Triad

The CIA Triad consists of:

+ Confidentiality

  Keeping things hidden.

  + Integrity

  Keeping our data accurate and untampered with.

	+ Availability

  The Information we have is readily accessible to those people that should have it.

## Essential Security Terms

### Risk

The possibility of suffering a loss in the event of an attack on the system.

### Vulnerability

A flaw in a system that could be exploited to compromise the system.

### 0-day vulnerability (zero day)

A vulnerability that is not known to the software developer or vendor, but is known to an attacker.

### Exploit

Software that is used to take advantage of a security bug or vulnerability.

### Threat

The possibility of danger that could exploit a vulnerability.

### Hacker

Someone who attempts to break into or exploit a system.

  + White-hat hackers
  + Black-hat hackers

![[Pasted image 20221012063718.png]]

### Attack 

An actual attempt at causing harm to a system.

![[Pasted image 20221012063917.png]]

## Malicious Software

### Malware

A type of malicious software that can be used to obtain your sensitive information, or delete or modify files.

![[Pasted image 20221012063917.png]]

### Adware

Software that displays advertisements and collects data.

### Trojan

Malware that disguises itself as one thing but does something else.

![[Pasted image 20221012064405.png]]

### Spyware

A type of malware that's meant to spy on you.

### Keylogger

A common type of spyware that's used to record every keystroke you make.

### Ransomeware

“A type of attack that holds your data or system hostage until you pay some sort of ransom.”

If the computer has one or more of the following symptoms, it may be infected with malware:

  + Running slower than normal
  + Restarts on its own multiple times
  + Uses all or a higher than normal amount of memory

After you’ve gathered information, verify that the issues are still occurring by monitoring the computer for a period of time. One way to monitor and verify is to review the activity on the computer’s resource manager, where you can see open processes running on a system.

When looking at the resource manager, you might see a program with a name you do not recognize, a program that is using a lot of memory, or both. If you see a suspicious program, you should investigate this application by asking the user if it is familiar to them. 

### Quarantine malware

Some malware communicates with bad actors or sends out sensitive information. Other malware is designed to take part in a distributed botnet. A botnet is a number of Internet-connected devices, each of which runs one or more bots. Because of malware’s potential ability to communicate with other bad actors, you should quarantine the infected device. 

To quarantine, or separate, the infected device from the rest of the network, you should disconnect from the internet by turning off Wi-Fi and unplugging the Ethernet cable. Once the computer is disconnected, the malware can no longer spread to other computers on the network. 

You should also disable any automatic system backup. Some malware can reinfect a computer by using automatic backup, because you can restore the system with files infected by the malware.

### Remove malware

Once you have confirmed and isolated the malware on a device, you should attempt to remove the malware from the device. First, run an offline malware scan. This scan helps find and remove the malware while the computer is still disconnected from the local network and internet.

All anti-virus/anti-malware programs rely on threat definition files to identify a virus or malware. These files are often updated automatically, but in the case of an infected computer they may be incomplete or unable to update. In this case, you may need to briefly connect to the internet to confirm that your malware program is fully updated.

The scan should successfully identify, quarantine, and remove the malware on the computer. Once the process is complete, monitor the computer again to confirm that there are no further issues.

To help ensure that a malware infection doesn’t happen again, threat definitions should be set to update automatically, and to automatically scan for and quarantine suspected malware. 

After the malware has been removed from the computer, you should turn back on the automatic backup tool and manually create a safe restore point. If the computer needs attention in the future, this new restore point is confirmed safe and clean.

### Malware education

One of the most important things an IT professional can do to protect a company and its employees is to educate users about malware. The goal of education is to stop malware from ever gaining access to company systems. Here are a few ways users and IT professionals can protect their computer and the company from malware: 

  + Keep the computer and software updated
  + Use a non-administrator account whenever possible
  + Think twice before clicking links or downloading anything
  + Be careful about opening email attachments or images
  + Don't trust pop-up windows that ask to download software
  + Limit your file-sharing
  + Use antivirus software

When all employees are on the lookout for suspicious files, it’s much easier to prevent malware and viruses from taking hold.

### Botnets

Designed to utilize the power of the internet-connected machines to perform some distributed function.

![[Pasted image 20221012065853.png]]

### Backdoor

A way to get into a system if the other methods to get in the system aren't allowed.

### Rootkit

A collection of software or tools that an Admin would use.

![[Pasted image 20221012070117.png]]

### Logic bomb

A type of malware that's intentionally installed.

[Disgruntled worker 'tried to cripple UBS in protest over $32,000 bonus'](https://www.independent.co.uk/news/business/news/disgruntled-worker-tried-to-cripple-ubs-in-protest-over-32-000-bonus-481515.html)

# Network Attacks

A network attack that is simple in concept, but can cause a lot of damage is:

  + DNS Cache Poisoning attack

It works by tricking the DNS server to serve, fake DNS request.

[Major DNS Cache Poisoning Attack Hits Brazilian ISPs](https://threatpost.com/major-dns-cache-poisoning-attack-hits-brazilian-isps-110711/75859/)

**Man-in-the-middle attack** is an attack that places the attacker in the middle of two hosts that think they're communicating directly with each other.

![[Pasted image 20221012072252.png]]

The methods of Man-in-the-middle attack are:

  + Session or Cookie hijacking
  + Rogue AP
  + Evil twin

### Rogue AP

An access point that is installed on the network without the network administrator's knowledge.

![[Pasted image 20221012072558.png]]

### Evil Twin

The premise of an evil twin attack is for you to connect to a network that is identical to yours. This identical network is our network's evil twin and is controlled by our attacker.

![[Pasted image 20221012072748.png]]

## Denial-of-service (DoS) attack

An attack that tries to prevent access to a service for legitimate users by overwhelming the network or server.

![[Pasted image 20221012073249.png]]

1) The ping of death or **POD** is an example of DoS attack, where the attacker sends the large number of pings to take down the server.

![[Pasted image 20221012073404.png]]

2) Another example is a **ping flood**, sends tons of ping packets to a system. More specifically, it sends **ICMP** echo requests.

![[Pasted image 20221012073556.png]]

3) Similar is a **SYN flood**, to make a TCP connection a client needs to send a **SYN** packet to a server it wants to connect to. Next, the server sends back a **SYN-ACK** message, then the client sends in ACK message.

In a SYN flood, the server is being bombarded with SYN packets.

![[Pasted image 20221012073938.png]]

During SYN flood, the TCP connection remains open, so it is also called a **Half-open attack**.

### Distributed denial-of-service attack (DDoS)

A DoS attack using multiple systems.

### How to prevent DDoS Attacks

[How to Stop DDoS Attacks: Prevention & Response](https://www.esecurityplanet.com/networks/how-to-stop-ddos-attacks-tips-for-fighting-ddos-attacks/)

[What is a DDOS Attack & How to Protect Your Site Against One ](https://aws.amazon.com/shield/ddos-attack-protection/)

[DDoS Protection, Mitigation, and Defense: 8 Essential Tips](https://www.indusface.com/blog/ddos-protection-mitigation-and-defense-8-essential-tips/)
# Other Attacks

## Client-Side Attacks

  + Injection attack
    + Cross-site scripting (XSS) attacks
    + SQL injection attack

### Cross-site scripting (XSS) attacks

A type of injection attack where the attacker can insert malicious code and target the user of the service.

### SQL injection attack

![[Pasted image 20221012080725.png]]

## Password Attacks

Utilize software like password-crackers that try and guess your password.

### Brute Force Attack

A Catchpa, can save your website from brute force attack.

![[Pasted image 20221012080902.png]]

### Dictionary Attack

![[Pasted image 20221012081025.png]]

## Deceptive Attacks

### Social Engineering

An attack method that relies heavily on interactions with humans instead of computers.

![[Pasted image 20221012081226.png]]

The popular types of social engineering attacks:

  + Phishing attack – Use of email or text messaging

![[Pasted image 20221012081913.png]]

  + Spear phishing — Attack individuals

![[Pasted image 20221012081956.png]]

  + Email Spoofing

![[Pasted image 20221012082138.png]]

  + Baiting – Entice a victim to do something

  + Tailgating

![[Pasted image 20221012082328.png]]

  + Whaling – Spear phishing a high value target
  + Vishing - Use of Voice over IP (VoIP)

### Spoofing

A source masquerading around as something else.

### Tailgating

Gaining access into a restricted area or building by following a real employee in.

