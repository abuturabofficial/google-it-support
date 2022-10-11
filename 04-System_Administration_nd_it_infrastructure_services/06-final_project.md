<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Scenario 1:](#scenario-1)
  - [The company overview:](#the-company-overview)
  - [Problem Statement](#problem-statement)
  - [The Improvements](#the-improvements)
  - [The Rationale Behind Improvements](#the-rationale-behind-improvements)
- [Scenario 2:](#scenario-2)
  - [The Company Overview](#the-company-overview)
  - [Problem Statement](#problem-statement-1)
  - [The Improvements](#the-improvements-1)
  - [The Rationale](#the-rationale)
- [Scenario 3:](#scenario-3)
  - [The Company Overview](#the-company-overview-1)
  - [Problem Statement](#problem-statement-2)
  - [The Improvements and Rationale](#the-improvements-and-rationale)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Scenario 1:

You’re doing systems administration work for Network Funtime Company. Evaluate their current IT infrastructure needs and limitations, then provide at least five process improvements and rationale behind those improvements. Write a 200-400 word process review for this consultation. Remember, there’s no right or wrong answer, but make sure to provide your reasoning.

## The company overview:

Network Funtime Company is a small company, that builds open-source software.

The Company is made up of 100 employees:

- [x] Software engineers

- [x] Designers

- [x] A Single HR Department

- [x] A Small Sales Team

## Problem Statement

- There is no technical support personnel.

- The HR, is responsible for buying hardware for new resources.

- Due to lack of funds company go for the cheapest hardware possible.

- Due to lack of funds, everyone in the company has different laptops models.

- There are no backups for hardware which creates additional wait time for new employees to start working.

- Due to missing standardized labeling convention, when a laptop or computer goes missing/stolen, there is no way to audit it.

- No Inventory system.

- HR manages System setups for engineers as well as answer their support queries through email.

- No standard way for login management, password management and recovery.

- The company use cloud applications like:

  + Email

  + Word Processor

  + Spreadsheets

  + Slack - Instant Communication

## The Improvements

The company should hire an IT Support specialist, who will take care of:

  + Buying new hardware, and disposing off the retired machines

  + According to company budget, selecting a hardware with similar specs.

  + Keep the inventory record, and labeling each and every machine before handing over to new employees.
    
  + Keeping few machines as a backup in the inventory.

  + Managing a ticking system for employees' **support question**.

  + Keeping the documentation of the fixes and issues.

  + Keeping a bootable USB of the OSs used in the company.

  + When the company hires a new resource, he/she sets up their machine for them.

The company should move to OpenLDAP or Active Directory for centralized passwords and permissions management and recovery.

The HR should be responsible for his/her tasks instead of providing IT Support, Hardware management, and Employees' software installation and setup.

## The Rationale Behind Improvements

Hiring an IT support specialist:

  + Will reduce the work of an HR

  + Keep the inventory record which will make auditing very easy.

  + Selecting a standardized hardware, will make troubleshooting and tracking issues and fixes much easier which in turn lessen the time spent in fixing and more in doing the work.

  + Keeping backups in the inventory, reduce time wastage for the new employees, they can start working asap.

  + Having a ticketing system or some centralized way of tracking issues and fixes, will create a documentation for future reference, and if the same issue arise again, it will be solved in no time.

  + Keeping bootable USB, saves in hunting down the software and makes the setup process easy, so reduces the overhead for new employees. And They can start working immediately.

Centralized management:

  + OpenLDAP/Active Directory, will make sure to centrally manage users and permissions, so everyone has only required access to the company's sensitive documents.

  + Password resets will become more easy, there be less time wastage.

# Scenario 2:

You’re doing systems administration work for W.D. Widgets. Evaluate their current IT infrastructure needs and limitations, then provide at least five process improvements and rationale behind those improvements. Please write a 200-400 word process review for this consultation. Remember, there’s no right or wrong answer, but make sure to provide your reasoning.

## The Company Overview

The company is in the business of selling widgets. There are mostly sales persons in the company.

The company size is 80-100 people.


## Problem Statement

- Sole IT person

- Manual installation of the software on new machines.

- Direct emails for IT support related issues.

- Almost every software is kept in house:

  + Email server

  + Local Machine Software

  + Instant messenger

- The Single file server for customers data.

  + No centralized management of the data.

  + No backups

  + Everyone has their copy with their unique data.

- The company growth is exponential. They expect to hire hundreds of new employees.

## The Improvements

The company should hire new talent for IT Support related stuff.

The automation for the following should be done:

  + Installation of software on the new machines.

  + Automated backups should be in place for critical data.

  + Storage server should be redundant.

A centralized management of the data is required:

  + To manage customers information in a single place

  + The company should move from one server to many redundant storage solutions.

  + Permissions and access to the data, should be limited to the role of the person.

To answer IT Support questions:

  + There should be a ticketing system in place.

  + There should be documentation of the common issues.

The company should move some of their services to the cloud like:

  + Email

  + Instant Chats

## The Rationale

Hiring new tech talent:

  + Will make sure you're ready for next big step of your expansion

  + Will distribute the work load, so fewer burnouts.

The automation will make sure:

  + There is no manual input, so fewer chances of errors.

  + No hours wasted on installing software, and configuring the new machines.

The cloud will make the company:

  + Less reliant on local servers, which require more maintenance, and security related complex configuration.

  + Will reduce the number of the people required for managing those servers.

  + There will be almost zero maintenance overhead for the cloud.

  + The data will be centrally available and backed up.

  + Email and chat servers are pretty complex to manage, and require a lot of security knowledge.

The centralized management:

  + Will make sure the right person has access to the right information

  + Removing the access of Ex-employees will become easy.

  + Role based access control, will make sure sensitive internal documents are exposed to wrong persons.

# Scenario 3:

You’re doing systems administration work for Dewgood. Evaluate their current IT infrastructure needs and limitations, then provide at least five process improvements and rationale behind those improvements. Please write a 200-400 word process review for this consultation. Remember, there’s no right or wrong answer, but make sure to provide your reasoning.

## The Company Overview

A small local non-profit of 50 employees.

- Sole IT person

## Problem Statement

- Computers are bought directly in a physical store on the day new talent is hired.

- Due to budget issue, they can't keep extra stock.

- The company has a single server with multiple services:

  + Email

  + File server

- Don't have internal chat system.

- AD is used, but Ex-employees are not disabled.

- Ticketing system is confusing and difficult to use so:

  + Many employees reach out to IT person, to know how to use it.

  + Employees are asking around always the questions of how to use it.

- IT person, takes backups on a personal Drive and takes it home.

- A website with single HTML page is hosted on internal server, and remain down many times, no one know why.

## The Improvements and Rationale

The computer should be purchased directly from vendors:

  + Vendors offer special discounts to businesses and non-profits, so it will save cost.

  + There should some standardization to which hardware to buy to avoid fix issues every time for new hardware type.

The company should move their email sever to the cloud:

  + The cloud solutions are cheap.

  + There's virtually no maintenance is involved.

  + Maintaining own email servers, requires a lot of complex configuration to make sure the security and redundancy, which isn't possible with Single IT Person.

Should use some cloud-based solution for internal instant chats:

  + The teams can keep track of each other progress.

  + The teams can discuss issues, plans and procedure without any hiccups.

To improve the customer ticketing system:

  + There should be proper documentation of to use it, so every time an employee doesn't have to go to the IT person for help.

  + The common issues and fixes should properly document and stored on the server, so employees can access them, and fix the common issues themselves to reduce time wastage.

For the backups:

  + There should be on-site and off-site backups for sensitive data for redundancy purposes.

  + The cloud backup solutions can also be used for a small company.

  + Self-hosted backups should be automatic, and redundant.

  + Backups tests and recovery should be done once every year or so, to make sure in the case of an emergency, your backups will prove reliable.
