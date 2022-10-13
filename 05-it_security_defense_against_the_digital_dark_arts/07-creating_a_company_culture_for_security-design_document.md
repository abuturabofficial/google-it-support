# Assignment

In this project, you’ll create a security infrastructure design document for a fictional organization. The security services and tools you describe in the document must be able to meet the needs of the organization. Your work will be evaluated according to how well you met the organization’s requirements.

## About the Organization

This fictional organization has a small, but growing, employee base, with 50 employees in one small office. The company is an online retailer of the world's finest artisanal, hand-crafted widgets. They've hired you on as a security consultant to help bring their operations into better shape.

## Organization Requirements

As the security consultant, the company needs you to add security measures to the following systems:

- [x] An external website permitting users to browse and purchase widgets
- [x] An internal intranet website for employees to use
- [x] Secure remote access for engineering employees
- [x] Reasonable, basic firewall rules
- [x] Wireless coverage in the office
- [x] Reasonably secure configurations for laptops

Since this is a retail company that will be handling customer payment data, the organization would like to be extra cautious about privacy. They don't want customer information falling into the hands of an attacker due to malware infections or lost devices.

Engineers will require access to internal websites, along with remote, command line access to their workstations.

## Security Plan

This plan will explain the steps required for improving the security of the organization's existing infrastructure, depending upon their needs and requirements.

## Centralized Access Management System

The company should deploy some directory services like OpenLDAP or Windows Active Directory service so:

  + Centralized management of permissions to company infrastructure
  + Group based permissions: Only software engineers should have access to the source code, only sales people should have access to the sales data etc.
  + To better manage passwords, and ability to centrally reset and change them when required.
  + Revoke Ex-employee's access to the company infrastructure.
  + Company network should be divided into Virtual Local Area Networks (VLANS), to containerized every department to their premise.

### External Website Security

To make the company's website secure from external threats:

  + Make sure admin pages are not exposed on the clearnet. You can robo.txt to tell Google Website Crawler to don't crawl them.
  + When a user, signs up for the website or enter any query in the website console, the standards, and methods for query sanitization and validation should be in place.
  + Make sure the website uses HTTPS to ensure encrypted communication across the servers.
  + Place firewall rules and IPS/IDS systems for threat detection and prevention.

As the company is involved in the online retail, make sure:

  + PCI DSS standards are met for secure debit and credit cards transactions.
  + Only those employees should have access to stored data, that explicitly need it.

## Internal Intranet Website

To make the company's internal website is secure:

  + Configure the website as such that it should only be accessible through the company's internal network.
  + To make sure the employees working away from the office have access to the internal website and other resources, use Virtual Private Networks (VPNs), or Reverse Proxy for secure tunnel.

## Remote Connections

To give remote access:

+ Use Secure Shell (SSH), Virtual Private Networks, or Reverse Proxies.

## Firewalls and IPS/IDS Solutions

+ Host based firewalls should be used on employees' laptops.
+ Network-based firewalls should be used to protect company's network.
+ Intrusion Detection and Intrusion Prevention Systems (IDS/IPS) should in-place.
+ There should be some kind of monitoring and alerting system, to tell you of the suspicious activity on your network.
+ Firewalls should only allow traffic explicitly mentioned in the rules list, instead of allowing every packet to enter the network.

## Wireless Security

To protect wireless traffic:

  + Use WPA2 security protocol which uses modern cipher technology AES for encryption which is a lot harder to crack than old WEP or WPA.
  + Install protection against IP Spoofing attacks and Rogue AP attacks.
  + Divide your network into vLANs, one for guests and one for employees.
  + Employees AP should use whitelisting MAC address to allow connection to the network.

## Employees Laptop Configuration

The laptops should equip with:

  + Full-disk encryption
  + Host-based firewalls with whitelisting rules for better security
  + Managing the accounts and passwords for laptop through AD.
  + The employees should not leave their laptops logged in and unlocked on their desks or café.

## The Company Security Culture

The humans are always the first line of defense for any system or organization, so educating them about the security is more necessary than anything else.

+ Organize seminar, record short videos, have small sessions occasionally to educate your employees about imminent security threats, and latest security techniques.
+ Educate them about phishing attacks to avoid any stolen data or credentials.
+ There should be small exercise including quizzes and real life examples of what not to do in security realm, how to react if you get phished or hacked after every possible cautionary step.