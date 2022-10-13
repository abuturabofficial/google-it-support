# Risk in the Workplace

## Security Goals

If your company handles credit card payments, then you have to follow the **PCI DSS**, or **Payment Card Industry Data Security Standard**.

PCI DSS is subdivided into 6 broad objectives:

1) Build and maintain a secure network and systems.
2) Protect cardholder data.
3) Maintain a vulnerability management program.
4) Implement strong access control measures.
5) Regularly monitor and test networks.
6) Maintain an information security policy.

## Measuring and Assessing Risk

Security is all about determining **risks** or exposure; understanding the likelihood of **attacks**; and designing **defenses** around these risks to **minimize** the impact of an attack.

  + Security risk assessment starts with **threat modeling**.
  + High-value data usually includes account information, like usernames and passwords. Typically, **any kind of user data is considered high value**, especially if payment processing is involved.
  + Another way to assess risk is through vulnerability scanning.
  + Conducting regular penetration testing to check your defenses.

### Vulnerability Scanner

A computer program designed to assess computers, computer systems, networks, or applications for weaknesses.

Some examples are:

  + [Nessus](https://www.tenable.com/products/nessus/nessus-professional)
  + [OpenVAS](https://www.openvas.org/)
  + [Qualys](https://www.qualys.com/forms/freescan/)

![](images/Pasted%20image%2020221013165735.png)

### Penetration testing

The practice of attempting to break into a system or network to verify the systems in place.

## Privacy Policy

**Privacy policies** oversee the access and use of sensitive data.

  + Periodic audits of access logs.
  + It's a good practice to apply the principle of **least privilege** here, by not allowing access to this type of data by default.
  + Any access that doesn't have a corresponding request should be flagged as a **high-priority potential breach** that need to be investigated as soon as possible.
  + **Data-handling policies** should cover the details of how different data is classified.
  + Once different data classes are defined, you should create **guidelines** around how to handle these different types of data.

## Data Destruction

Data destruction makes data unreadable to an operating system or application. You should destroy data on devices no longer used by a company, unused or duplicated copies of data, or data that’s required to destroy. Data destruction methods include:

  + **Recycling**: erasing the data from a device for reuse
  + **Physical destruction**: destroying the device itself to prevent access to data
  + Outsourcing: using an external company specializing in data destruction to handle the process

For more information about disposing of electronics, please visit [Proper Disposal of Electronic Devices](https://www.cisa.gov/tips/st18-005), a resource from CISA.

# Users

## User Habits

You can build the world's best security systems, but they won't protect you if the users are going to be practicing **unsafe security**.

  + You should **never upload confidential information** onto a third-party service that hasn't been evaluated by your company.
  + It's important to **make sure employees use new and unique passwords**, and don't reuse them from other services.
  + A much greater risk in the workplace that users should be educated on is **credential theft** from phishing emails.
  + If someone entered their password into a phishing site, or even suspects they did, it's important to **change their password** asap.

![](images/Pasted%20image%2020221013172648.png)

## Third-Party Security

If they have subpar security, you're undermining your security defenses by potentially opening a new avenue of attack.

[Google Vendor Security Assessment Questionnaire](https://vsaq-demo.withgoogle.com/)

  + If you can, ask for a third-party security assessment report.

## Security Training

Helping others keep security in mind will help decrease the security burdens you'll have as an IT Support Specialist.

# Incident Handling

## Incident Reporting and Analysis

The very first step of handling an incident is to **detect it** in the first place.

The next step is to **analyze it** and **determine the effects** and scope of damage.

Once the scope of the incident is determined, the next step is **containment**.

  + If an account was compromised, change the password immediately. If the owner is unable to **change the password** right away, then **lock the account**.

![](images/Pasted%20image%2020221013184451.png)

Another part of incident analysis is determining **severity, impact, and recoverability** of the incident.

  + Severity includes factors like what and how many systems were compromised, and how the breach affects business functions.
  + The **impact** of an incident is also an important issue to consider.

### Data exfiltration

The unauthorized transfer of data from a computer.

### Recoverability

How complicated and time-consuming the recovery effort will be.

## Incident Response

Incident handling requires careful attention and documentation during an incident investigation's analysis and response phases.

  + Be familiar with what types of regulated data may be on your systems, and ensure proper procedures are in place to ensure your organization’s compliance.
  + DRM technologies can be beneficial for safeguarding business-critical documents or sensitive information and helping organizations comply with data protection regulations.
  + When incident analysis involves the collection of forensic evidence, you must thoroughly document the chain of custody.

## Incident Response and Recovery

Update firewall rules and ACLs if an exposure was discovered in the course of the investigation.

Create new definitions and rules for intrusion detection systems that can watch for the signs of the same attack again.

## Mobile Security and Privacy

+ Screen lock
+ Storage encryption
+ Apps permissions

## Bring Your Own Device (BYOD)

Organizations are taking advantage of the cost savings created by adopting “bring your own device” (BYOD) policies for employees. However, permitting employees to connect personal mobile devices to company networks introduces multiple security threats. There are a variety of security measures that IT departments can implement to protect organizations’ information systems:

  + Develop BYOD policies
  + Enforce BYOD policies with MDM software
  + Distribute MDS settings to multiple OSes through Enterprise Mobile Management (EMM) systems
  + Require MFA
  + Create acceptable use policies for company data and resources
  + Require employees to sign NDAs
  + Limit who can access data
  + Train employees on data security
  + Back up data regularly

[BYOD policy: An in-depth guide from an IT leader](https://www.dialpad.com/blog/byod-policy/)