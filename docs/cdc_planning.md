[Back to Index](https://github.com/zeditor01/cdc_setup/blob/main/index.md)

Last Update to this page: 4 September 2024

# CDC Planning

***Purpose of this Chapter***
This is the most important chapter in the whole repository !

CDC technology is a combination of three moving parts ( capture agent, apply agent, control tools ) that conform to a common repliction standard. All you need is a TCPIP network to connect up the moving parts, so that you define replication subscriptions and operate them. 

Simple huh ? 

Err, actually ***No!***.

Most enterprises will be organised into specialised teams to look after different parts of the IT landscape. You will may be surprised to realise how many different teams need to work together to make a heterogeneous data replication solution work. It's not just the three CDC components that you need to consider. When you arrive at the answer for your organisation, you will likely realise that the nature of this project beast is quite a large project plan in order to co-ordinate the teams that are needed to assemble the moving parts and automate an entire data replication lifecycle.

## Contents
1. CDC Implementation (Theory).
2. CDC Implementation (Real World).
3. Common Constraints that will make things difficult.
4. Production Hardening.

## 1. CDC Implementation (Theory)

CDC solutions, in theory, have a complex set of moving parts to co-ordinate, but are easy to manage with the centralised control plane. 
A simple architectecture diagram might look like this.

![cdc_in_theory](./images/cdc_in_theory.JPG)

## 2. CDC Implementation (Real World)

CDC in practice is rather more complicated to manage. The causes of the complexity lie the heterogeneous nature of the typical CDC solution.
And whilst all the technical integration points use standards-based patterns, it is the number of different teams that need to be co-ordinated
that will be the most demanding aspect of project management for a heterogeneous data replication project. 
Review the representations of the different teams (the green boxes) and map this example to your own organisational structures.

![cdc_in_practice](./images/cdc_in_practice.JPG)

## 3. Common Constraints that will make things difficult

Each deployment will enounter it's own unique set of challenges, based on the organisation, technology and technical standards applicable at that site.
The list below is a compilation of some the the challenges that occur most frequently across sites.

* for IMS, implications of increased logging and implementation of IMS exits
* for IMS, augmentation of DBDs to generate log record types needed for replication
* for VSAM (or IAM), implementation of z/OS logstreams to serve replication
* for Db2 z/OS, DDL break in difficulties (completely solved by recent Db2 V13 PTF)
* for Kafka, configuring CDC (a Kafka producer and consumer) to integrate with site-specific Kafka standards
* Schema management (whether RDBMS or Kafka)
* Choice of using a Windows client tool for production operations, or automation with scripting tools
* Change management procedures that span the breadth of the heterogeneous data replication solution
* Operations control

Each of these considerations is addressed directly in the deployment documents linked at the top of this document.

## 4. Production Hardening.



