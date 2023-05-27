# 1. SAA-C03 Notes

> These are my personal notes from Adrian Cantrill's (SAA-C03) course. Learning Aids from [aws-sa-associate-saac03](https://github.com/acantril/aws-sa-associate-saac03). There may be errors, so please purchase his course to get the original content and show support <https://learn.cantrill.io.>

**Table of Contents**

- [1.1. Cloud Computing Fundamentals](#11-cloud-computing-fundamentals)
  - [1.1.1. Cloud Computing - what is it really](#111-cloud-computing---what-is-it-really)
  - [1.1.2. Public vs Private vs Multi vs Hybrid Cloud](#112-public-vs-private-vs-multi-vs-hybrid-cloud)
  - [1.1.3. Cloud Service Models](#113-cloud-service-models)
- [1.2. Tech Fundamentals](#12-tech-fundamentals)
  - [1.2.1. YAML101 - YAML AINT MARKUP LANGUAGE](#121-yaml101---yaml-aint-markup-language)
  - [1.2.2. JSON101 - JavaScript Object Notation](#122-json101---javascript-object-notation)
  - [1.2.3. Encryption 101](#123-encryption-101)
  - [1.2.4. Network Starter Pack](#124-network-starter-pack)
    - [0 - INTRO](#0---intro)
    - [1 - PHYSICAL](#1---physical)
    - [2 - DATA LINK](#2---data-link)
    - [3 - NETWORK](#3---network)
    - [4 - TRANSPORT](#4---transport)
    - [6 - EXTRA](#6---extra)
- [1.3. AWS-Fundamentals](#13-aws-fundamentals)
  - [1.3.1. Public vs Private Services](#131-public-vs-private-services)
  - [1.3.2. AWS Global Infrastructure](#132-aws-global-infrastructure)
  - [1.3.3. Regions and AZs](#133-regions-and-azs)
  - [1.3.4. AWS Default VPC](#134-aws-default-vpc)
  - [1.3.5. Elastic Compute Cloud (EC2)](#135-elastic-compute-cloud-ec2)
  - [1.3.6. S3 (Default Storage Service)](#136-s3-default-storage-service)
  - [1.3.7. CloudFormation Basics](#137-cloudformation-basics)
  - [1.3.8. Resources](#138-resources)
  - [1.3.9. CloudWatch Basics](#139-cloudwatch-basics)
  - [1.3.10. Shared Responsibility Model](#1310-shared-responsibility-model)
  - [1.3.11. High Availability (HA), Fault-Tolerance (FT) and Disaster Recovery (DR)](#1311-high-availability-ha-fault-tolerance-ft-and-disaster-recovery-dr)
  - [1.3.12. Domain Name System (DNS)](#1312-domain-name-system-dns)
  - [1.3.13. Route53 Fundamentals](#1313-route53-fundamentals)
  - [1.3.14. DNS Record](#1314-dns-record)
- [1.4. IAM-Accounts-AWS-Organizations](#14-iam-accounts-aws-organizations)
  - [1.4.1. IAM Identity Policies](#141-iam-identity-policies)
  - [1.4.2. IAM Users](#142-iam-users)
  - [1.4.3. IAM Groups](#143-iam-groups)
  - [1.4.4. IAM Roles](#144-iam-roles)
  - [1.4.5. When to use IAM Roles](#145-when-to-use-iam-roles)
  - [1.4.6. Service-linked Roles & PassRole](#146-service-linked-roles--passrole)
  - [1.4.7. AWS Organizations](#147-aws-organizations)
  - [1.4.8. Service Control Policies](#148-service-control-policies)
  - [1.4.9. CloudWatch Logs](#149-cloudwatch-logs)
  - [1.4.10. CloudTrail Essentials](#1410-cloudtrail-essentials)
  - [1.4.11. AWS Control Tower](#1411-aws-control-tower)
- [1.5. Simple-Storage-Service-(S3)](#15-simple-storage-service-s3)
  - [1.5.1. S3 Security](#151-s3-security)
  - [1.5.2. S3 Static Hosting](#152-s3-static-hosting)
  - [1.5.3. Object Versioning and MFA Delete](#153-object-versioning-and-mfa-delete)
  - [1.5.4. S3 Performance Optimization](#154-s3-performance-optimization)
  - [1.5.5. Key Management Service (KMS)](#155-key-management-service-kms)
  - [1.5.6. KMS Key Demo](#156-kms-key-demo)
  - [1.5.7. Object Encryption](#157-object-encryption)
  - [1.5.8. S3 Object Storage Classes](#158-s3-object-storage-classes)
  - [1.5.9. S3 Lifecycle Configuration](#159-s3-lifecycle-configuration)
  - [1.5.10. S3 Replication](#1510-s3-replication)
  - [1.5.11. S3 Presigned URL](#1511-s3-presigned-url)
  - [1.5.12. S3 Select and Glacier Select](#1512-s3-select-and-glacier-select)
  - [1.5.13. S3 Event Notifications](#1513-s3-event-notifications)
  - [1.5.14. S3 Access Logs](#1514-s3-access-logs)
  - [1.5.15. S3 Object Lock](#1515-s3-object-lock)
  - [1.5.16. S3 Access Points](#1516-s3-access-points)
- [1.6. Virtual-Private-Cloud-VPC](#16-virtual-private-cloud-vpc)
  - [1.6.1. Networking Refresher](#161-networking-refresher)
  - [1.6.2. VPC Sizing and Structure](#162-vpc-sizing-and-structure)
  - [1.6.3. Custom VPC](#163-custom-vpc)
  - [1.6.4. VPC Subnets](#164-vpc-subnets)
  - [1.6.5. VPC Routing and Internet Gateway](#165-vpc-routing-and-internet-gateway)
  - [1.6.6. Network Access Control List (NACL)](#166-network-access-control-list-nacl)
  - [1.6.7. Security Groups](#167-security-groups)
  - [1.6.8. Network Address Translation (NAT) Gateway](#168-network-address-translation-nat-gateway)
---

## 1.1. Cloud Computing Fundamentals
### 1.1.1. Cloud Computing - what is it really?

Cloud computing provides
1. On-Demand Self-Service: Provision and terminate using a UI/CLI without
human interaction.
2. Broad Network Access: Access services over any networks on any devices using
standard protocols and methods.
3. Resource Pooling: Economies of scale, cheaper service.
4. Rapid Elasticity: Scale up and down automatically in response to system load.
5. Measured Service: Usage is measured. Pay only for what you consume.

### 1.1.2. Public vs Private vs Multi vs Hybrid Cloud

- Public Cloud: using 1 public cloud such as AWS, Azure, Google Cloud.
- Private Cloud: using on-premises real cloud. Must meet 5 requirements.
- Multi-Cloud: using more than 1 public cloud in one deployment.
- Hybrid Cloud: using public and private clouds in one environment
  - This is **NOT** using Public Cloud and Legacy on-premises hardware.

### 1.1.3. Cloud Service Models

The *Infrastructure Stack* or *Application Stack* contains multiple components
that make up the total service. There are parts that **you** manage as well
as portions the **vendor** manages. The portions the vendor manages and you
are charged for is the **unit of consumption**

![Stacks](../main/attachments/Clipboard_2022-08-20-22-35-47.png?raw=true "Optional Title")

1. On-Premises: 
    * The individual manages all components from data to facilities.
    * Provides the most flexibility, but also most IT intensive.
2. Data Center Hosting: 
    * Place equipment in a building managed by a vendor.
    * You pay for the facilities only.
3. Infrastructure as a Service (IaaS): 
    * Vendor manages facilities and everything else related to servers up to the OS. 
    * You pay per second or minute for the OS used to the vendor. 
    * Lose some flexibility, but big risk reductions.
4. Platform as a Service (PaaS):  
    * Good for running an application only. 
    *  The unit of consumption is the runtime environment. 
    * You manage the application and the data, but the vendor manges all else.
5. Software as a Service (SaaS): 
    * You consume the software as a service. (This can be Outlook or Netflix)
    * There are almost no risks or additional costs, but very little control.

There are additional services such as *Function as a Service*, *Container as a Service*, and *DataBase as a Service* which be explained later.

---

## 1.2. Tech Fundamentals
### 1.2.1. YAML101 - YAML AINT MARKUP LANGUAGE
![Stacks](../main/attachments/Clipboard_2022-08-20-22-49-10.png?raw=true "Optional Title")
* YAML = Human readable data serialization language
* Uses key value pair (key: value)
* Suports numbers (1 or 2...), floating point (1.234), boolean (true or false), and null value
* Uses lists with the following formats:
```
adrianscats: ["cat1","cat2","cat3"]
```
or 
```
adrianscats:
  - "cat1"
  - "cat2"
  - 'cat3'
  - cat4
```
* Same indentation = same list. You can nest lists in lists using indentation.

![Stacks](../main/attachments/Clipboard_2022-08-20-22-55-20.png?raw=true "Optional Title")
![Stacks](../main/attachments/Clipboard_2022-08-20-22-59-14.png?raw=true "Optional Title")
* YAML is commonly used for configuration and in CloudFormation within AWS

### 1.2.2. JSON101 - JavaScript Object Notation
![Stacks](../main/attachments/Clipboard_2022-08-20-23-03-30.png?raw=true "Optional Title")
* Also uses attribute value pairs and array data types
* Indentation is not necessary

```
# Example 1:
{
  "cats": ["cat1","cat2","cat3"].
  "colors": ["red","blue","orange"],
  "eyes": ["1","2","2"]
}

# Example 2:
{
  "Resource": {
    "s3bucket": {
      "Type": "AWS::S3::Bucket",
      "Properties": {
        "BucketName": "abc123catpics"
        "Number": ["1","2","2"] <-- Array
      }
    }
  }
}
```
### 1.2.3. Encryption 101
![Stacks](../main/attachments/Clipboard_2022-08-20-23-17-35.png?raw=true "Optional Title")
* Encryption At Rest
  * Data on your laptap uses a password to encrypt your data
* Encryption in Transit
  * Data is encrypted before leaving the users laptop and decrypted at the bank and vice versa

*Encryption is the process of taking **Plaintext**, using **Algorithm** + **Key** to create **Ciphertext***
1. Plain Text
2. Algorithm
3. Key 
4. Ciphertext

#### **Symmetric Encryption**
![Stacks](../main/attachments/Clipboard_2022-08-20-23-30-18.png?raw=true "Optional Title")
* Great for local encryption on laptop 
* Bad since it can't deliver encryption key safely to the other party (remote party)

#### **Asymmetric Encryption**
![Stacks](../main/attachments/Clipboard_2022-08-20-23-35-59.png?raw=true "Optional Title")
* Plubic and Private key pairs are created at the same time
* Public key is use to encrypt data
* Private key is use to decrypt data 
* Asymmetric is much more costly computationally than symmetric
* Use to exchange key first with asymmetric then use symmetric to furthur communicate

#### **Signing**
* Use make sure that the sender is who they are
* Use private key to sign the Ciphertext 
* Public key are use to verify the private sign is legit

![Stacks](../main/attachments/Clipboard_2022-08-21-09-30-22.png?raw=true "Optional Title")
#### **Steganography**
* People know that you are the one who encrypted the data
* The method of hiding something within something else
* Example: Hiding text within an image

### 1.2.4. Network Starter Pack 
#### 0 - INTRO
![Stacks](../main/attachments/Clipboard_2022-08-21-09-46-16.png?raw=true "Optional Title")
OSI 7-Layer Model
* Media Layers: 
    * How data is move between point A and point B.
* Host Layers: 
    * How data is chopped up reassembly for transport.
    * How data is formatted so both side of a network can understand.
#### 1 - PHYSICAL
1-1 Device communication
![Stacks](../main/attachments/Clipboard_2022-08-21-09-51-56.png?raw=true "Optional Title")
* Transfer data via voltage changing (1s and 0s) on **physical shared medium** (ex:copper[electricity], fibre[light], wifi[radio])
* Has standards for transmitting onto the medium
* Has standards for receiving from the medium
* The 1s and 0s has predefined things **(standard specification)** such as Voltage levels, timing, rates, distances,modulation and connectors

Layer 1 device HUB multiple device communication
![Stacks](../main/attachments/Clipboard_2022-08-21-09-57-01.png?raw=true "Optional Title")
* Anything received on any port, transmitted on every other port
    * Cause collision
    * No device to device communications
* No media access control (no method of controlling which device can transmit)
* No uniquely identified devices

#### 2 - DATA LINK
![Stacks](../main/attachments/Clipboard_2022-08-21-10-16-55.png?raw=true "Optional Title")
* Preamble: Know when a frame starts
* ET: Which layer 3 prototal is being use (ex: IP address protocal)
* Payload: Contains the data
* FCS: Allow destination to check if corruption has occured

![Stacks](../main/attachments/Clipboard_2022-08-21-10-52-28.png?raw=true "Optional Title")
* Carrier sense multiple access (CSMA): Allows Layer 2 to check carrier signal on the Layer 1 allowing <span style="color:red">***Media access control***</span>
* Collision detection: if detection does occur and detected (both transmitted at once) then both backoff for a random time 

Layer 2 device **"Switch"** for multiple device communication
![Stacks](../main/attachments/Clipboard_2022-08-21-11-02-10.png?raw=true "Optional Title")
* A switch has a mac address table which stores Mac address to the corresponding port
* Table starts out empty but learns which port is connected through which device
* Switches **STORE** and **FORWARD** so only valid frame are forwarded and collisions are isolated on the port they occurred

Conclusion for Layer 2:
* Allow identifiable devices
* Media access control (sharing)
* Collision detection
* Unicast: 1:1
* Broadcast: 1:All
* Switches are like Hub but better

#### Add-on - Decimal to Binary Conversion (IP Addressing)
Decimal => Binary
Decimal number: 133.33.33.7
Converting 133 to binary
|Position|1|2|3|4|5|6|7|8|
|-|-|-|-|-|-|-|-|-|
| Binary position value|128|64|32|16|8|4|2|1|
|Binary value|1|0|0|0|0|1|0|1|
1. Start from left to right
2. Comapre decimal number to Binary position value. If **SMALLER** write 0 then go to next position 
3. If **EQUAL** or **LARGER** - Subtract the binary position value with the decimal number and write 1
4. Move to next position with the new decimal value after subtracting and repeat from step 2

![Stacks](../main/attachments/Clipboard_2022-08-21-11-28-22.png?raw=true "Optional Title")
Binary => Deciaml 
* Start from left to right
* Compare the Binary value with Binary position value. If **Birary value** = 1 then add that Binary position value

#### 3 - Network
##### L2 => L3 - Building a Common L33 Network
![Stacks](../main/attachments/Clipboard_2022-08-21-11-35-38.png?raw=true "Optional Title")
* Not everything uses the same layer 2 protocal. Need to use the same protocal to communicate.
* L2 Ethernet protocal generally  use for local network. Long distance use different protocal (ex: PPP/MPLS/ATM)
* L3 has Internet protocal (IP) which adds cross network IP address and routing to move data between **Local Area Networks** without point to point links
* Routers (L3) devices, remove frame encapsulation and add new ones at each hop

![Stacks](../main/attachments/Clipboard_2022-08-21-11-46-56.png?raw=true "Optional Title")
* <Span style= "color:pink"> Protocal</span>: Stores L4 protocol data
    * TCP: value = 6
    * ICMP or ping: value = 1
    * UDP: value = 17
* <Span style= "color:orange"> Time To Live</span>: Tells how many hop it could take 

##### IP Addressing (v4) - IPv4
![Stacks](../main/attachments/Clipboard_2022-08-21-12-01-33.png?raw=true "Optional Title")
* Has 2 part
    * Network part: helps know if you are on the same local network or remote
    * Host part
##### Subnet Mask
![Stacks](../main/attachments/Clipboard_2022-08-21-12-06-22.png?raw=true "Optional Title")
* Allow devices to know if they need to communicate on local network or remote
* Works by over-laying the host IP Address and the subnet mask (255.255.0.0)
##### L3 - Route Tables & Routes
![Stacks](../main/attachments/Clipboard_2022-08-21-12-14-13.png?raw=true "Optional Title")
* Routers stores Desination and Next Hop. 
    * Route table are populated  Statically or 
    * Route table are populated thanks to Boreder Gateway Protocal which allows routers to communicate with each other
* Routers uses the Destination IP within a Packet to compare with destination in route table. The higher the prefix the better

##### Address Resolution Protocal (ARP)
![Stacks](../main/attachments/Clipboard_2022-08-21-12-25-01.png?raw=true "Optional Title")
* Dont know the initial destination mac address. ARP solve this
* ARP give the IP Address for the given Mac Address
##### Layer 3 - IP Routing
![Stacks](../main/attachments/Clipboard_2022-08-21-12-37-53.png?raw=true "Optional Title")

**LAYER 3 - NETWORK SUMMARY**
* IP Addresses (IPv4/v6) - cross network addressing
* ARP - Find the MAC address, for this IP
* Route - where to forward a packet
* Route Tables - Multiple Routes
* Router - Layer 3 device helps move packets from **Source** to **Destination** - **Encapsulating** in L2 on the way
* Allow Device <=> Device Communications over the internet...
* No method for channels of communications SRC IP <=> DST IP only. Different application on the same device communicating at the same time. (Solve in layer 4)
* Can be delivered out of order... (Solve in layer 4)

#### 4 - TRANSPORT
![Stacks](../main/attachments/Clipboard_2022-08-21-17-10-39.png?raw=true "Optional Title")
##### Layer 3 - problems
1. Each Packet is routed independently => <span style="color:red">***out of order arrival***</span> (L3 provide no ordering mechanism)
2. <span style="color:red">***Packet can go missing***</span>  due to lost of connection or time to live exceed
3. Per packet routing <span style="color:red">***can be delay***</span> due to routing
4.  Email/App/Watch video. <span style="color:red">***No communication channels.***</span> Can't differentiate packet between different channels
5. <span style="color:red">***No flow control***</span>. If source transmit is faster than destination can receive then cause packet loss 
##### TCP and UDP
![Stacks](../main/attachments/Clipboard_2022-08-21-17-18-41.png?raw=true "Optional Title")
TCP: 
* Slower/Reliable
UDP:
* Fast/Less Reliable
##### TCP Segments
![Stacks](../main/attachments/Clipboard_2022-08-21-17-34-16.png?raw=true "Optional Title")
1. Source Port **(Solve no communication channel)**
2. Destination Port **(Solve no communication channel)**
    * SRC Port + DES Port + SRC IP + DES IP combine to create a unquie value to identify a single conversation (a single communication channel) => Why SSH and HTTPS can exist on the same EC2 instance
3. Sequence number **(Solve out of order arrival)**
    * Uniquely identify a particular segment winthin a particular connection
4. Acknowledgement **(Solve out of order arrival+missing packet)**
5. Flag 'N' Things (*)
6. TCP WINDOW **(Solve No flow control)**
7. Checksum: Error checker and arrage retransmission of data 
8. Urgent pointer: help control traffic part to always takes priority within the communication 
##### Transmission Control Protocol (TCP)
![Stacks](../main/attachments/Clipboard_2022-08-21-17-39-55.png?raw=true "Optional Title")
* EPHEMERAL PORT (some high number TCP/23060)
* WELL KNOWN PORT (TCP/443)

Flag 'N' Things field
![Stacks](../main/attachments/Clipboard_2022-08-21-17-55-46.png?raw=true "Optional Title")
* URG: Urgent pointer is valid
* ACK: Acknowledgement is valid
* PSH: Request for push
* RST: Reset the connection
* SYN; Synchronizze sequence numbers
* FIN: Terminate the connection

1. Connection establishment phase 
![Stacks](../main/attachments/Clipboard_2022-08-21-17-56-41.png?raw=true "Optional Title")
    * HOST send a packet with SYN FLAG and Sequence number
    * Client ACK the SYN and send back a packet with its own Squence number as well as the ACK number and the Window number
    * HOST ACK the packet sent by sending another packet back with the ACK number of the client incremented by 1 as well as the new sequence number and its Window number
2. Data transfer phase
![Stacks](../main/attachments/Clipboard_2022-08-21-17-58-10.png?raw=true "Optional Title")
* Host start sending data to client with PSH FLAG and ACK FLAG 
* Client received the packet and send back a packet of ACK, the updated window size (Not yet computed by client), the new seq num and the new ack num
* Host send back an ACK saying that it has receive packet succesfully and also proceed the data so the window size is still the same.
3. Connection termination phase (full close)
![Stacks](../main/attachments/Clipboard_2022-08-21-17-59-05.png?raw=true "Optional Title")
4. Connection termination phase (half close)
![Stacks](../main/attachments/Clipboard_2022-08-21-18-00-15.png?raw=true "Optional Title")

##### Sessions & State
![Stacks](../main/attachments/Clipboard_2022-08-21-18-25-00.png?raw=true "Optional Title")
Stateless firewall: Does not understand the state of a connection (Network ACL)
* Would need 2 rule for it to work.
    * Outbound rule (host transfering data to client)
    * Inboud rule (host receiving data from client)
Statefull firewall: Once Outbound is established then inbound response is as well

<span style="color:red">**These is how AWS Security Group works**</span>

#### 6 - EXTRA
#### EXTRA - Network Address Translation
NAT Device is use to do the following: 
* Designed to overcome IPv4 shortage
* Provide some security benifits
* Translate IPv4 address to Public
* Type of NAT:
    * Static NAT - 1 private to 1 (fixed) public address (IGW)
    ![Stacks](../main/attachments/Clipboard_2022-08-21-18-36-01.png?raw=true "Optional Title")
    * Dynamic NAT - 1 private to 1st available public adress
    ![Stacks](../main/attachments/Clipboard_2022-08-23-22-47-38.png?raw=true "Optional Title")
    * Port Address Translation (PAT) - many private to 1 public (NATGW)
    ![Stacks](../main/attachments/Clipboard_2022-08-23-22-49-50.png?raw=true "Optional Title")
* IPv4 only since IPv6 has no shortage
#### EXTRA - Subnetting
![Stacks](../main/attachments/Clipboard_2022-08-23-22-58-45.png?raw=true "Optional Title")
* Dividing IP into smaller chucks
* Total 4,294,967,296 IPv4 Address
* Class A IP: Start 0.0.0.0 - End 127.255.255.255
    * Very big company
    * Early internet
* Class B IP: Start 128.0.0.0 - End 191.255.255.255
    * Regional authorities
* Class C IP: Start 192.0.0.0 - End 223.255.255.255
    * Small businesses

**Private IP**
* Class A IP: Start 10.0.0.0 - End 10.255.255.255 => (1 class A network and 16,777,216 IPv4 address)
* Class B IP: Start 172.16.0.0 - End 172.31.255.255 => (16 class B network and 16 * 65,536 IPv4 address)
* Class C IP: Start 192.168.0.0 - End 192.168.255.255 => (256 class C network and 256 * 256 IPv4 address)
##### IP Subnetting
* The larger the prefix the samller the network

![Stacks](../main/attachments/Clipboard_2022-08-23-23-10-46.png?raw=true "Optional Title")
![Stacks](../main/attachments/Clipboard_2022-08-23-23-11-24.png?raw=true "Optional Title")

##### SSL and TLS

![Stacks](../main/attachments/Clipboard_2022-08-23-23-22-34.png?raw=true "Optional Title")

##### Hash Functions & Hashing
* Data + Hash function = hash
* Same data turn to same hash
* Different data no matter how small will get new hash
* Hash can not be turn back into original data
* Downloaded Data can be verified by using hash
* Check by downloading the data and if the hash match then data is unaltered

##### Digital Signatures
![Stacks](../main/attachments/Clipboard_2022-08-23-23-43-03.png?raw=true "Optional Title")
* Verifies <span style="color:purple">INTEGRITY(WHAT)</span> & <span style="color:orange">AUTHENTICITY(WHO)</span> 
* <span style="color:purple">HASH</span> of the data is taken, original data remains unaltered <span style="color:purple">(INTEGRITY)</span>
* <span style="color:orange">Digital sign</span> the <span style="color:purple">HASH</span> (using private key). <span style="color:orange">Authenticates</span> the hash.
* Public key can be widely distributed and trusted
* Hash can not be changed as nobody else has the private key

---

## 1.3. AWS-Fundamentals

### AWS Support Plans

- Basic (free)
- Developer (one user, general guidance)
- Business (multiple users, personal guidance)
- Enterprise (Technical account manager)

### 1.3.1. Public vs Private Services


Refers to the networking only, not permissions.

- Public Internet: AWS is a public cloud platform and connected to the public
internet. It is not on the public internet, but is next to it.
- AWS Public Zone: Attached to the Public Internet.
S3 Bucket is hosted in the Public Zone, not all services are.
Just because you connect to a public service,
that does not mean you have permissions to access it.
- AWS Private Zone: No direct connectivity is allowed between the AWS Private
Zone and the public cloud unless this is configured for that service.
This is done by taking a part of the private service and projecting it into the
AWS public zone which allows public internet to make inbound or outbound
connections.

### 1.3.2. AWS Global Infrastructure

#### 1.3.2.1. Regions

AWS Region is an area of the world they have selected for a full deployment of
AWS infrastructure.

Areas such as countries or states

- Ohio
- California
- Singapore
- Beijing
- London
- Paris

AWS can only deploy regions as fast as their planning allows.
Regions are often not near their customers.

#### 1.3.2.2. AWS Edge Locations

Local distribution points. Useful for services such as Netflix so they can store
data closer to customers for low latency high speed transfers.

If a customer wants to access data stored in Brisbane, they will stream data
from the Sydney Region through an Edge Location hosted in Brisbane.

#### 1.3.2.3. AWS Management

Regions are connected together with high speed networking.
Some services such as EC2 need to be selected in a region.
Some services are global such as IAM

#### 1.3.2.4. Region's 3 Benefits

- Geographical Separation
  - Useful for natural disasters
  - Provide isolated fault domain
  - Regions are 100% isolated
- Geopolitical Separation
  - Different laws change how things are accessed
  - Stability from political events
- Location Control
  - Tune architecture for performance
  - Duplicate infrastructure at closer points to customers

### 1.3.3. Regions and AZs

Region Name: Asia Pacific (Sydney)
Region Code: ap-southeast-2

AWS will provide between 2 and 6 AZs per region.
AZs are isolated compute, storage, networking, power, and facilities.
Components are allowed to distribute load and resilience by using multiple zones.

AZs are connected to each other with high speed redundant networks.

#### 1.3.3.1. Service Resilience

1. Globally Resilient: IAM or Route 53. No way for them to go down. Data is
replicated throughout multiple regions.
2. Region Resilient: Operate as separate services in each region. Generally
replicate data to multiple AZs in that region.
3. AZ Resilient: Run from a single AZ. It is possible for hardware to fail in an
AZ and the service to keep running because of redundant equipment, but should
not be relied on.

### 1.3.4. AWS Default VPC

VPC is a virtual network inside of AWS.
A VPC is within 1 account and 1 region which makes it regionally resilient.
A VPC is private and isolated until decided otherwise.

One default VPC per region. Can have many custom VPCs which are all private
by default.

#### 1.3.4.1. Default VPC Facts

VPC CIDR - defines start and end ranges of the VPC.
IP CIDR of a default VPC is always: **172.31.0.0/16**

Configured to have one subnet in each AZ in the region by default.

Subnets are given one section of the IP ranges for the default service. 
They are configured to provide anything that is deployed inside those subnets with public IPv4 addresses. 

In general do not use the Default VPC in a region because it is not flexible.

Default VPC is large because it uses the /16 range.
A subnet is smaller such as /20
The higher the / number is, the smaller the grouping.

Two /17's will fit into a /16, sixteen /20 subnets can fit into one /16.

### 1.3.5. Elastic Compute Cloud (EC2)

Default compute service. Provides access to virtual machines called instances.

#### 1.3.5.1. Infrastructure as as Service (IaaS)

The unit of consumption is an instance.
An EC2 instance is configured to launch into a single VPC subnet.
Private service by default, public access must be configured.
The VPC needs to support public access. If you use a custom VPC then you must
handle the networking on your own.

EC2 deploys into one AZ. If it fails, the instance fails.

Different sizes and capabilities. All use On-Demand Billing - Per second.
Only pay for what you consume.

Local on-host storage or **Elastic Block Storage**

Pricing based on:

- CPU
- Memory
- Storage
- Networking

Extra cost for any commercial software the instance deploys with.

#### 1.3.5.2. Running State

Charged for all four categories.

- Running on a physical host using CPU.
- Using memory even with no processing.
- OS and its data are stored on disk, which is allocated to you.
- Networking is always ready to transfer information.

#### 1.3.5.3. Stopped State

Charged for EBS storage  only.

- No CPU resources are being consumed
- No memory is being used
- Networking is not running
- Storage is allocated to the instance for the OS together with any applications.

#### 1.3.5.4. Terminated State

No charges, deletes the disk and prevents all future charges.

#### 1.3.5.5. AMI (Server Image)

AMI can be used to create an instance or can be created from an instance.
AMIs in one region are not available from other regions.

Contains:

- Permissions: controls which accounts can and can't use the AMI.

  - Public - Anyone can launch it.

  - Owner - Implicit allow, only the owner can use it to spin up new instances

  - Explicit - Owner grants access to AMI for specific AWS accounts

- Root Volume: contains the **Boot Volume**

- Block Device Mapping: links the volumes that the AMI has and
how they're presented to the operating system. Determines which volume is a
boot volume and which volume is a data volume.


#### 1.3.5.6. Connecting to EC2

AMI Types:

- Amazon Quick Start AMIs
- AWS Marketplace AMIs
- Community AMIs
- Private AMIs

- Windows using RDP (Remote Desktop Protocol), Port 3389
- Linux SSH protocol, Port 22

Login to the instance using an SSH key pair.
Private Key - Stored on local machine to initiate connection.
Public Key - AWS places this key on the instance.

### 1.3.6. S3 (Default Storage Service)

Global Storage platform. Runs from all regions and is a public service.
Can be accessed anywhere from the internet with an unlimited amount of users.

This should be the default storage platform

S3 is an object storage, not file, or block storage.
You can't mount an S3 Bucket.

#### 1.3.6.1. Objects

Can be thought of a file. Two main components:

- Object Key: File name in a bucket
- Value: Data or contents of the object
  - Zero bytes to 5 TB

Other components:

- Version ID
- Metadata
- Access Control
- Sub resources

#### 1.3.6.2. Buckets

- Created in a specific AWS Region.
- Data has a primary home region. Will not leave this region unless told.
- Blast Radius = Region
- Unlimited number of Objects
- Name is globally unique
- All objects are stored within the bucket at the same level.

If the objects name starts with a slash such as `/old/Koala1.jpg` the UI will
present this as a folder. In actuality this is not true, there are no folders.

### 1.3.7. CloudFormation Basics

CloudFormation templates can be used to create, update, modify, and delete infrastructure.

They can be written in YAML or JSON. An example is provided below.

```YAML
## This is not mandatory unless a description is added
AWSTemplateFormatVersion: "version date"

## Give details as to what this template does.
## If you use this section, it MUST immediately follow the AWSTemplateFormatVersion.
Description:
  A sample template

## Can control the command line UI. The bigger your template, the more likely
## this section is needed
Metadata:
  template metadata

## Prompt the user for more data. Name of something, size of instance,
## data validation
Parameters:
  set of parameters

## Another optional section. Allows lookup tables, not used often
Mappings:
  set of mappings

## Decision making in the template. Things will only occur if a condition is met.
## Step 1: create condition
## Step 2: use the condition to do something else in the template
Conditions:
  set of conditions

Transform:
  set of transforms

## The only mandatory field of this section
Resources:
  set of resources

## Once the template is finished it can return data or information.
## Could return the admin or setup address of a word press blog.
Outputs:
  set of outputs
```

### 1.3.8. Resources

An example which creates an EC2 instance

```YAML
Resources:
  Instance: ## Logical Resource
    Type: 'AWS::EC2::Instance' ## This is what will be created
    Properties: ## Configure the resources in a particular way
      ImageId: !Ref LatestAmiId
      Instance Type: !Ref Instance Type
      KeyName: !Ref Keyname
```

Once a template is created, AWS will make a stack. This is a living and active
representation of a template. One template can create infinite amount of stacks.

For any **Logical Resources** in the stack,
CF will make a corresponding **Physical Resources** in your AWS account.

It is cloud formations job to keep the logical and physical resources in sync.

A template can be updated and then used to update the same stack.

### 1.3.9. CloudWatch Basics

Collects and manages operational data on your behalf.

Three products in one

- Metrics: data relating to AWS products, apps, on-prem solutions
- Logs: collection, monitoring
- Events: event hub
  - If an AWS service does something, CW events can perform another action
  - Generate an event to do something at a certain time of day or time of week.

#### 1.3.9.1. Namespace

Container for monitoring data.
Naming can be anything so long as it's not `AWS/service` such as `AWS/EC2`.
This is used for all metric data of that service

#### 1.3.9.2. Metric

Time ordered set of data points such as:

- CPU Usage
- Network IN/OUT
- Disk IO

This is not for a specific server. This could get things from different servers.

Anytime CPU Utilization is reported, the **datapoint** will report:

- Timestamp = 2019-12-03
- Value = 98.3

**Dimensions** could be used to get metrics for a specific instance or type of instance, among others. They separate data points for different **things** or
**perspectives** within the same metric.

#### 1.3.9.3. Alarms

Has two states `ok` or `alarm`. A notification could be sent to an SNS topic or an action could be performed based on an alarm state.
Third state can be insufficient data state. Not a problem, just wait.

### 1.3.10. Shared Responsibility Model

AWS: Responsible for security **OF** the cloud

Customer: Responsible for security **IN** the cloud

### 1.3.11. High Availability (HA), Fault-Tolerance (FT) and Disaster Recovery (DR)

#### 1.3.11.1. High Availability (HA)

- Aims to **ensure** an agreed level of operational **performance**, usually
**uptime**, for a **higher than normal period**
- Instead of diagnosing the issue, if you have a process ready to replace it, it can be fixed quickly and probably in an automated way.
- Spare infrastructure ready to switch customers over to in the event of a disaster to minimize downtime
- User disruption is not ideal, but is allowed
  - The user might have a small disruption or might need to log back in.
- Maximizing a system's uptime
  - 99.9% (Three 9's) = 8.7 hours downtime per year.
  - 99.999 (Five 9's) = 5.26 minutes downtime per year.

#### 1.3.11.2. Fault-Tolerance (FT)

- System can **continue operating properly**
in the event of the **failure of some** (one or more faults within) of its
**components**
- Fault tolerance is much more complicated than high availability and more
expensive. Outages must be minimized and the system needs levels of
redundancy.
- An airplane is an example of system that needs Fault Tolerance. It has
more engines than it needs so it can operate through failure.

Example:
A patient is waiting for a life saving surgery and is under anesthetic.
While being monitored, the life support system is dosing medicine.
This type of system cannot only be highly available, even a movement of
interruption is deadly.

#### 1.3.11.3. Disaster Recovery (DR)

- Set of policies, tools and procedures to **enable the recovery** or
**continuation** of **vital** technology infrastructure and systems
**following a natural or human-induced disaster**.
- DR can largely be automated to eliminate the time for recovery and errors.

This involves:

- Pre-planning
  - Ensure plans are in place for extra hardware
  - Do not store backups at the same site as the system
- DR Processes
  - Cloud machines ready when needed

This is designed to keep the crucial and non replaceable parts of the
system in place.

Used when HA and FT don't work.

### 1.3.12. Domain Name System (DNS)

DNS is a discovery service. Translates machines into humans and vice-versa.
It is a huge database and has to be distributed.

Parts of the DNS system

- DNS Client: Piece of software running on the OS for a device you're using.
- Resolver: Software on your device or server which queries DNS on your behalf.
- Zone: A part of the DNS database.
  - This would be amazon.com
  - What the data is, its substance
- Zone file: physical database for a zone
  - How physically that data is stored
- Nameserver: where zone files are hosted

Steps:

Find the Nameserver which hosts a particular zone file.
Query that Nameserver for a record that is in that zone file.
It then passes the information back to the DNS client.

#### 1.3.12.1. DNS Root

The starting point of DNS.
DNS names are read right to left with multiple parts separated by periods.

`www.netflix.com.`

The last period is assumed to be there in a browser when it's not present.
The DNS Root is hosted on DNS Root Servers (13). These are hosted
by 12 major companies.

**Root Hints** is a pointer to the DNS Root servers provided by the OS vendor

Process

1. DNS client asks DNS Resolver for IP address of a given DNS name.
2. Using the Root Hints file, the DNS Resolver communicates with one or
more of the root servers to access the root zone and begin the process
of finding the IP address.

The Root Zone is organized by IANA (Internet Assigned Numbers Authority).
Their job is to manage the contents of the root zone. IANA is in charge
of the DNS system because they control the root zone.

#### 1.3.12.2. DNS Hierarchy

Assuming a laptop is querying DNS directly for www.amazon.com and using
a root hints file to know how to access a root server and query the root zone.

- When something is trusted in DNS, it is an **authority**.
- One piece can be authoritative for root.
- One piece can be authoritative for amazon.com
- The root zone is the start and the only thing trusted in DNS.
- The root zone can delegate a part of itself to another zone or entity.
- That someone else then becomes authoritative for just the part that's delegated.
- The root zone is just a database of the top level domains.

The top level domains are the only thing immediately to the left of the root in a DNS name.

- `.com` or `.org` are generic top level domains (gTLD)
- `.uk` is a country code top level domain (ccTLD)

**Registry** maintains the zones for a TLD (e.g .ORG)
**Registrar** has relationships with the .org TLD zone manager
allowing domain registration

### 1.3.13. Route53 Fundamentals

- Registers domains
- Can host zone files on managed nameservers
- This is a global service, no need to pick a region
- Globally Resilience
  - Can operate with failure in one or more regions

#### 1.3.13.1. Register Domains

Has relationships with all major registries (registrar)

- Route 53 will check with the top level domain to see if the name is available
- Route 53 creates a zone file for the domain to be registered
- Allocates nameservers for that zone
  - Generally four of these for one individual zone
  - This is a hosted zone
  - The zone file will be put on these four managed nameservers
- Route 53 will communicate with the `.org` registry and add the nameserver records 
into the zone file for that top level domain.
  - This is done with a nameserver record (NS).

#### 1.3.13.2. Route53 Details

**Zone files** in AWS
Hosted on four managed name servers

- Can be **public** or **private** (linked to one or more VPCs)

### 1.3.14. DNS Record

- Nameserver (NS): Allows delegation to occur in the DNS.
- A and AAAA Records: Maps the host to a v4 or v6 host type respectively. Most of the time
you will make both types of record, A and AAAA.
- CNAME Record Type: Allows DNS shortcuts to reduce admin overhead.
CNAMES cannot point directly to an IP address, only another name.
- MX records: How emails are sent. They have two main parts:
  - Priority: Lower values for the priority field are higher priority.
  - Value
    - If it is just a host, it will not have a dot on the right. It is assumed
to be part of the same zone as the host.
    - If you include a dot on the right, it is a ***fully qualified domain name***
- TXT Record: Allows you to add arbitrary text to a domain.
One common usage is to prove domain ownership.

#### 1.3.14.1. TTL - Time To Live

This is a numeric setting on DNS records in seconds.
Allows the admin to specify how long the query can be stored
at the resolver server.
If you need to upgrade the records, it is smart to lower the TTL value first.

Getting the answer from an Authoritative Source is known as an
**Authoritative Answer**.

If another client queries the same thing, they will get back a
**Non-Authoritative** response.

---

## 1.4. IAM-Accounts-AWS-Organizations

### 1.4.1. IAM Identity Policies

Identity Policies are attached to AWS Identities which are:
* IAM users 
* IAM groups
* IAM roles 
 
![Stacks](../main/attachments/Clipboard_2022-08-25-22-46-55.png?raw=true "Optional Title")
These are **a set of security statements** that ALLOW or DENY access to AWS resources.

When an identity attempts to access AWS resources, that identity needs to prove who it is to AWS, using a process known as **Authentication**.
Once authenticated, that identity is known as an **authenticated identity**

#### 1.4.1.1. Statement Components

- Statement ID (SID): Optional field that should help describe
  - The resource you're interacting
  - The actions you're trying to perform
- Effect: is either `allow` or `deny`.
  - It is possible to be allowed and denied at the same time
- Action are formatted `service:operation`. There are three options:
  - specific individual action
  - wildcard as an action
  - list of multiple independent actions
- Resource: similar to action except for format `arn:aws:s3:::catgifs`

#### 1.4.1.2. Priority Level
![Stacks](../main/attachments/Clipboard_2022-08-25-22-58-25.png?raw=true "Optional Title")
- Explicit Deny: Denies access to a particular resource cannot be overruled.
- Explicit Allow: Allows access so long there is not an explicit deny.
- Default Deny (Implicit): IAM identities start off with no resource access.

#### 1.4.1.3. Inline Policies and Managed Policies
![Stacks](../main/attachments/Clipboard_2022-08-25-23-05-13.png?raw=true "Optional Title")
- Take in all statement and evaluates all at the same time
- Inline Policy: grants access and assigned on each accounts individually. (Use for exceptions)
- Managed Policy (best practice): one policy is applied to all users at once.
  - Reusable (large # of users, groups, and roles)
  - Low Management Overhead 

### 1.4.2. IAM Users

Identity used for anything requiring **long-term** AWS access

- Humans
- Applications
- Service Accounts

If you can name a thing to use the AWS account, this is an IAM user.

![Stacks](../main/attachments/Clipboard_2022-08-25-23-19-43.png?raw=true "Optional Title")

When a **principal** wants to **request** to perform an action, it will **authenticate** against an identity within IAM. An IAM user is an
identity which can be used in this way.

There are two ways to authenticate:

- Username and Password
- Access Keys (CLI)

Once the **Principal** has authenticated, it becomes an **authenticated identity**

#### 1.4.2.1. Amazon Resource Name (ARN)

Uniquely identify resources within any AWS accounts.

- This allows you to refer to a single or group of resources. 
- AS well as prevents individual resources from the same account or in different regions with similar characteristic from being confusing.

ARN generally follows the same format:

```bash
arn:partition:service:region:account-id:resource-id
arn:partition:service:region:account-id:resource-type/resource-id
arn:partition:service:region:account-id:resource-type:resource-id
```

- partition: almost always `aws` unless it is china `aws-cn`
- service: service such as S3, IAM, RDS...
- region: can be a double colon (::) if that doesn't matter or wildcard
- account-id: the account that owns the resource
  - EC2 needs this
  - S3 does not need account-id because its globally unique
- resource-type/id: changes based on the resource (can be the name or id of object)

An example that leads to confusion:

- arn:aws:s3:::catgifs
  - This references an actual bucket
- arn:aws:s3:::catgifs/*
  - This refers to objects in that bucket, but not the bucket itself.

![Stacks](../main/attachments/Screenshot_from_2023-03-23_10-35-51.png?raw=true "Optional Title")

These two ARNs do not overlap

#### 1.4.2.2. IAM FACTS

- 5,000 IAM users per account
- IAM user can be a member of 10 groups

### 1.4.3. IAM Groups

* Containers for users. **You cannot login to IAM groups** 
* They have no credentials of their own. 
* Used solely for management of IAM users.

![Stacks](../main/attachments/Clipboard_2022-08-28-18-29-03.png?raw=true "Optional Title")
Groups bring two benefits

1. Effective administrative style management of users based on the team
2. Groups can have Inline and Managed policies attached.

AWS merges all of the policies from all groups the user is in together.

- The 5000 IAM user limit applies to groups.
- There is **no all users** IAM group.
  - You can create a group and add all users into that group, but it needs to be
created and managed on your own.
- No Nesting: You cannot have groups within groups.
- 300 Group Limit per account. This can be fixed with a support ticket.

**Resource Policy** 
A bucket can have a policy associated with that bucket.
It does so by referencing the identity using an ARN (Amazon Reference Name).
A policy on a resource can reference IAM users and IAM roles by the ARN.
A bucket can give access to one or more users or one or more roles.

**GROUPS ARE NOT A TRUE IDENTITY**
**THEY CAN'T BE REFERENCED AS A PRINCIPAL IN A POLICY**

An S3 Resource cannot grant access to a group, it is not an identity.
Groups are used to allow permissions to be assigned to IAM users.

### 1.4.4. IAM Roles

A single thing that uses an identity is an IAM User.

IAM Roles are also identities that are used by large groups of individuals. Internally and externally.
If have more than 5000 principals, it could be a candidate for an IAM Role.

IAM Roles are **assumed** you become that role.

This can be used short term by other identities.

IAM Users can have inline or managed policies which control which permissions the identity gets within AWS

Permission policy: Policies which grant, allow or deny, permissions based on their associations.

![Stacks](../main/attachments/Clipboard_2022-08-28-19-23-13.png?raw=true "Optional Title")
IAM Roles have two types of policies can be attached.

- Trust Policy: Specifies which identities are allowed to assume the role.
- Permissions Policy: Specifies what the role is allowed to do.

If an identity is allowed on the **Trust Policy**, it is given a set of **Temporary Security Credentials**. Similar to access keys except they are time limited to expire. The identity will need to renew them by reassuming the role.

Every time the **Temporary Security Credentials** are used, the access is checked against the **Permissions Policy**. If you change the policy, the permissions of the temp credentials also change.

Roles are real identities and can be referenced within resource policies.

Secure Token Service (sts:AssumeRole) this is what generates the temporary security credentials (TSC).

### 1.4.5. When to use IAM Roles

![Stacks](../main/attachments/Clipboard_2022-08-28-19-36-53.png?raw=true "Optional Title")
Lambda Execution Role.
For a given lambda function, you cannot determine the number of principals which suggested a Role might be the ideal identity to use.

- Trust Policy: to trust the Lambda Service
- Permission Policy: to grant access to AWS services.

When this is run, it uses the sts:AssumeRole to generate keys to CloudWatch and S3.

It is better when possible to use an IAM Role versus attaching a policy.

#### 1.4.5.1. Emergency or out of the usual situations
![Stacks](../main/attachments/Clipboard_2022-08-28-19-40-36.png?raw=true "Optional Title")
Break Glass Situation - There is a key for something the team does not normally have access to. When you break the glass, you must have a reason
to do.
A role can have an Emergency Role which will allow further access if its really needed.

#### 1.4.5.2. Adding AWS into existing corp environment

You may have an existing identity provider you are trying to allow access to.
This may offer SSO (Single Sign On) or over 5000 identities.
This is useful to reuse your existing identities for AWS.
External accounts can't be used to access AWS directly.
To solve this, you allow an IAM role in the AWS account to be assumed
by one of the active directories.
**ID Federation** allowing an external service the ability to assume a role.

#### 1.4.5.3. Making an app with 1,000,000 users
![Stacks](../main/attachments/Clipboard_2022-08-28-19-46-51.png?raw=true "Optional Title")
**Web Identity Federation** uses IAM roles to allow broader access.
These allow you to use an existing web identity such as google, facebook, or twitter to grant access to the app.
We can trust these web identities and allow those identities to assume an IAM role to access web resources such as DynamoDB.
No AWS Credentials are stored on the application.
Can scale quickly and beyond.

#### 1.4.5.4. Cross Account Access
![Stacks](../main/attachments/Clipboard_2022-08-28-19-50-25.png?raw=true "Optional Title")
You can use a role in the partner account and use that to upload objects to AWS resources.

### 1.4.6. Service-linked Roles & PassRole

A service-linked role is a unique type of IAM role that is linked directly to an AWS service. Service-linked roles are predefined by the service and include all the permissions that the service requires to call other AWS services on your behalf. The linked service also defines how you create, modify, and delete a service-linked role. A service might automatically create or delete the role. It might allow you to create, modify, or delete the role as part of a wizard or process in the service. Or it might require that you use IAM to create or delete the role.

Service-linked roles:
* IAM role linked to a specific AWS service
* Predefined by a service
* Prodviding permissions that a service needs to interact with other AWS services on your behalf
* Service might create/delete the role...
* or allow you to during the setup or within IAM
* Can't delete the role until it's no longer required

Role separation is where you might give one group of people the ability to create roles, and another group of people the ability to use them.

PassRole is a method inside AWS which gives you the ability to implement role separation, and it's something which you can also use with service-linked roles.

![Stacks](../main/attachments/Service-linked-Roles-&-PassRole_learn.cantrill.io-et-3-pages-de-plus-Personnel–Microsoft​-Edge-25_03_2023-10_42_48.png?raw=true "Optional Title")

### 1.4.7. AWS Organizations

Without an organization, each AWS account needs it's own set of IAM users as well as individual payment methods.
If you have more than 5 to 10 accounts, you would want to use an org.

Take a single AWS account **standard AWS account** and create an org.
The standard AWS account then becomes the **master account**.
The master account can invite other existing standard AWS accounts. They will need to approve their joining to the org.

When standard AWS accounts become part of the org, they become **member accounts**.
Organizations can only have one **master accounts** and zero or more **member accounts**

#### 1.4.7.1. Organization Root
![Stacks](../main/attachments/Clipboard_2022-08-29-23-47-42.png?raw=true "Optional Title")
This is a container that can hold AWS member accounts or the master account.
It could also contain **organizational units** which can contain other units or member accounts.

#### 1.4.7.2. Consolidated billing
![Stacks](../main/attachments/Clipboard_2022-08-29-23-51-30.png?raw=true "Optional Title")
The individual billing for the member accounts is removed and they pass their billing to the master account.
Inside an AWS organization, you get a single monthly bill for the master account which covers all the billing for each users.
Can offer a discount with consolidation of reservations and volume discounts

#### 1.4.7.3. Create new accounts in an org
![Stacks](../main/attachments/Clipboard_2022-08-29-23-57-25.png?raw=true "Optional Title")
Adding accounts in an organization is easy with only an email needed.

No need for IAM Users within every single AWS account.
Login to other account can be done with IAM Roles using ID Federation (external) or Role switch.

It is **BEST** to have a single AWS account only used for login.
Some enterprises may use a separated AWS account, 1 master and 1 login, while smaller ones may use the master account.

#### 1.4.7.4. Role Switching

Allows you to switch between accounts from the command line

### 1.4.8. Service Control Policies

Can be used to restrict what member accounts in an org can do.

JSON policy document that can be attached:
![Stacks](../main/attachments/Clipboard_2022-08-30-23-41-24.png?raw=true "Optional Title")
- To the org as a whole by attaching to the root container.
- A specific Organizational Unit
- A specific member only.

The master account cannot be restricted by SCPs which means this should not be used because it is a security risk.

SCPs are **account permissions boundaries** and they limit what the account, **including root** can do inside that account.
They don't grant permissions themselves, just act as a barrier.

#### 1.4.8.1. Allow List vs Deny List

Deny list is the default.

When you enable SCP on your org, AWS applies `FullAWSAccess`. This means SCPs have no effect because nothing is restricted. It has zero influence by themselves.

```json
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": "*",
    "Resource": "*"
  }
}
```

SCPs by themselves don't grant permissions. When SCPs are enabled, there is an implicit deny.

You must then add any services you want to Deny such as `DenyS3`

```json
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Deny",
    "Action": "s3:*",
    "Resource": "*"
  }
}
```

**Deny List** is a good default because it allows for the use of growing services offered by AWS. A lot less admin overhead.

**Allow List** allows you to be conscience of your costs.

- To begin, you must remove the `FullAWSAccess` list
- Then, specify which services need to be allowed access.
- Example `AllowS3EC2` is below

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
        "Effect": "Allow",
        "Action": [
            "s3:*",
            "ec2:*"
        ],
    "Resource": "*"
    }
  ]
}
```

### 1.4.9. CloudWatch Logs

This is a public service, this can be used from AWS VPC or on premise environment.

This allows to **store**, **monitor** and **access** logging data.

- This is a piece of information data and a timestamp
- Can be more fields, but at least these two

Comes with some AWS Integrations.
Security is provided with IAM roles or Service roles.
Can generate metrics based on logs **metric filter**

#### 1.4.9.1. Architecture of CloudWatch Logs
![Stacks](../main/attachments/Clipboard_2022-09-01-12-15-58.png?raw=true "Optional Title")
* It is a regional service `us-east-1`
* Need logging sources such as external APIs or databases. 
* This sends information as **log events**. 
* These are stored in **log streams**. This is a sequence of log events from the same source.

* **Log Groups** are containers for multiple logs streams of the same type of logging. This also stores configuration settings such as
retention settings and permissions.

* Once the settings are defined on a log group, they apply to all log streams in that log group. 
* Metric filters are also applied on the log groups.

### 1.4.10. CloudTrail Essentials

Concerned with who did what.

Logs API calls or activities as **CloudTrail Event**

Stores the last 90 days of events in the **Event History**. This is enabled by default at no additional cost.

To customize the service you need to create a new **trail**.
Two types of events. Default logs is Management Events

- Management Events:
Provide information about management operations performed on resources
in the AWS account. Create an EC2 instance or terminating one.

- Data Events:
Objects being uploaded to S3 or a Lambda function being invoked. This is not enabled by default and must be enabled for that trail.

#### 1.4.10.1. CloudTrail Trail

Logs events for the AWS region it is created in. It is a regional service.

Once created, it can operate in two ways

- One region trail
- All region trail
  - Collection of trails in all regions
  - When new regions are added, they will be added to this trail automatically

Most services log events in the region they occur. The trail then must be a one region trail in that region or an all region trail to log that event.

A small number of services log events globally to one region. 
Global services such as IAM or STS or CloudFront always log their events to `us-east-1` this is called a global service events.
A trail must have this enabled to have this logged.

AWS services are largely split into regional services or global services.

When the services log, they log in the region they are created or to `us-east-1` if they are a global service.

A trail can store events in an S3 bucket as a compressed JSON file. It can also use CloudWatch Logs to output the data.

CloudTrail products can create an organizational trail. This allows a single management point for all the APIs and management events for that org.

#### 1.4.10.2. CloudTrail Exam PowerUp

- It is enabled by default for 90 days without S3
- Trails are how you configure S3 and CWLogs
- Management events are only saved by default
- IAM, STS, CloudFront are Global Service events and log to `us-east-1`
  - Trail must be enabled to do this
- NOT REALTIME - There is a delay. Approximately 15 minute delay

#### 1.4.10.3. CloudTrail Pricing

<https://aws.amazon.com/cloudtrail/pricing/>

### 1.4.11. AWS Control Tower

* Quick & Easy setup of multi-account environment
* Orchestrates other AWS services to provide this functionality
  * Oranizations, IAM Identity Center (SSO), CloudFormation, Congfig and more....
* Landing Zone - multi-account environment
  * SSO/ID Federation, Centralised Logging & Auditing
* Guard Rails - Detect/Mandate rules/standards across all acounts
* Account Factory - Automates & Standardises new account creation
* Dashboard - single page oversight of the entire environment

#### 1.4.11.1. Control Tower Structure
![Stacks](../main/attachments/Clipboard_2022-09-02-17-30-31.png?raw=true "Optional Title")
* Management account contain:
  * Control Tower
  * SSO (IAM Identity Center)
    * Use Federation ID or Internal ID to access Landing Zone that has access to
  * AWS Organizations
    * Control tower create 2 OU
      1. Foundational OU
      2. Custom OU
* Foundational OU:
  * Audit Account: Location for 3rd party tools to audit account -> SNS Cloud Watch
  * Log Archive Account: Users who need all log info -> AWS Config or Cloud Trail
* Account Factory can auto create, mod, delete AWS account as needed.
* Use CloudFormation to do this
* Use AWS Congif + Custom OU (Service control policy) to implement account guardrails => Prevent mishave

#### 1.4.11.2. Landing Zone
* Well Architected multi-account env - Home Region
  * Built with AWS Organizations, AWS Config, CloudFormation
* Security OU - Log Archive & Audit Account (CloudTrail & Config Logs)
* Sandbox OU - Test/less rigid security
* You can create other OU's and Accounts
* IAM Identity Center (AWS SSO) - SSO, multiple-accounts, ID Federation
* Monitoring and Notifications - CloudWatch and SNS
* End User account provisioning via Service Catalog

#### 1.4.11.3. Guard Rails
* Guardrails are rules - multi-account governance
* Mandatory, Strongly Recommended or Elective
* Preventive - Stop you doing things (AWS ORG SCP)
  * enforced or  not enabled
  * allow or deny regions or disallow bucket policy changes
* Detective - compliance checks (AWS CONFIG Rules)
  * clear, in violation or not enabled
  * detect Cloud Trail enabled or EC2 Public IPv4 

#### 1.4.11.4. Guard Rails
* Automated Account Provisioning
* cloud admins or end users (with appropriate permissions)
* Guardrails - automatically added
* Account admin given to a named user (IAM Identity Center)
* Account & network standard configuration
* Account can be closed or repurposed
* Can be fully integrated with a businesses Software Development Life Cycle (SDLC)
---

## 1.5. Simple-Storage-Service-(S3)

### 1.5.1. S3 Security

- **S3 is private by default!** 
- The only identity which has any initial access to an S3 bucket is the account root user of the account which owns that bucket.

#### 1.5.1.1. S3 Bucket Policy

![Stacks](../main/attachments/Clipboard_2022-09-09-16-23-28.png?raw=true "Optional Title")
This is a **resource policy**
- controls who has access to that resource
- can allow or deny access from different accounts
- can allow or deny anonymous principals
  - this is explicitly declared in the bucket policy itself.

Different from an **identity policy**

- controls what that identity can access
- can only be attached to identities in your own account
  - no way of giving an identity in another account access to a bucket.

Each bucket can only have one policy, but it can have multiple statements.

#### 1.5.1.2. ACLs Access control lists (Legacy)

A way to apply a subresource to objects and buckets.
These are legacy and AWS does not recommend their use.
They are inflexible and allow simple permissions.

#### 1.5.1.3. Block Plublic Acess

- Public access: read only to any objects defined in a resource policy on a bucket.
- Block public access: apply no matter what the bucket policy say but just the public access  
- Act as a final fail safe

#### 1.5.1.4. S3 Exam PowerUp

When to use Identity Policy or Bucket Policy:

Identity

- Controlling high mix of different resources.
  - Not every service supports resource policies.
- Want to manage permissions all in one place, use IAM.
- Must have access to all accounts accessing the information.

Bucket

- Managing permissions on a specific product.
- If you need anonymous or cross account access.

ACLs: NEVER - unless you must.

### 1.5.2. S3 Static Hosting

Normal access is via AWS APIs.
This allows access via HTTP using a web browser.

When you enable static website hosting you need two HTML files:

- index document
  - default page returned from a website
  - entry point for most websites
- error document
  - similar to index, but only when something goes wrong

Static website hosting creates a **website endpoint**.

This is influenced by the bucket name and region it is in. This cannot be changed.

You can use a custom domain for a bucket, but then the bucket name matters.
The name of the bucket must match the domain.

#### 1.5.2.1. Offloading

Instead of using EC2 to host an entire website, the compute service can generate a HTML file which points to the resources hosted on a static bucket. This ensures the media is retrieved from S3 and not EC2.

#### 1.5.2.2. Out-of-band pages

This may be an error page to display maintenance if the server goes offline.
We could then change our DNS and move customers to a backup website on S3.

![Stacks](../main/attachments/Screenshot-from-2023-03-27-15-08-56.png?raw=true "Optional Title")

#### 1.5.2.3. S3 Pricing

- Cost to store data, per GB / month fee
  - Prorated for less than a GB or month.
- Data transfer fee
  - Data in is always free
  - Data out is a per GB charge
- Each operation has a cost per 1000 operations.
  - Can add up for static website hosting with many requests.

### 1.5.3. Object Versioning and MFA Delete
![Stacks](../main/attachments/Clipboard_2022-09-10-16-32-16.png?raw=true "Optional Title")
Without Versioning:

- Each object is identified solely by the object key, it's name.
- If you modify an object, the original of that object is replaced.
- The attribute, **ID of object**, is set to **null**.

Versioning

- This is off by default.
- Once it is turned on, it cannot be turned off.
- Versioning can be suspended and enabled again.
- This allows for multiple versions of objects within a bucket.
- Objects which would modify objects **generate a new version** instead.

The latest or current version is always returned when an object version is not requested.

When an object is deleted, AWS puts a **delete marker** on the object and hides all previous versions. You could delete this marker to enable the item.

To delete an object, you must delete all the versions of that object using their version marker.

#### 1.5.3.1. MFA Delete

Enabled within version configuration in a bucket.
This means MFA is required to change bucket versioning state.
MFA is required to delete versions of an object.

In order to change a version state or delete a particular version of an object, you need to provide the serial number of your MFA token as well as the code it generates. These are concatenated and passed with any API calls.

### 1.5.4. S3 Performance Optimization

Single PUT Upload

- Objects uploaded to S3 are sent as a single stream by default.
- If the stream fails, the upload fails and requires a restart of the transfer.
- Speed and reliability = limit of 1 stream
- Single PUT upload up to 5GB

Multipart Upload

- Data is broken up into smaller parts.
- The minimum data size is 100 MB.
- Upload can be split into maximum of 10,000 parts.
  - Each part can range between 5MB and 5GB.
  - Last leftover part can be smaller than 5MB if needed.
- Parts can fail in isolation and restart in isolation.
- The risk of uploading large amounts of data is reduced.
- Improves transfer rate to be the speed of all parts.

S3 Accelerated Transfer
![Stacks](../main/attachments/Clipboard_2022-09-11-16-10-03.png?raw=true "Optional Title")

- The S3 bucket needs to be enabled for transfer acceleration.
- S3 AT is switched off by default.
- Uses the network of AWS edge locations to speed up transfer.
- Restrictions for enable the S3 AT:
  - The bucket name can not contain periods.
  - the bucket needs to be DNS compatible in its naming.
- Benefits improve the larger the location and distance.
  - The worse the start (distance), the better the performance benefits.

### 1.5.5. Key Management Service (KMS)

- Regional service
  - Every region is isolated when using KMS.
- Public service
  - Occupies the AWS public zone and can be connected to from anywhere.
- Create, store, and manage keys.
  - Can handle both symmetric and asymmetric keys.
- KMS can perform cryptographic operations itself.
- Keys never leave KMS.
- Keys use **Federal Information Processing Standard (FIPS) 140-2 (L2)** security standard.
  - Some features are compliant with Level 3.
  - All features are compliant with Level 2.

#### 1.5.5.1. KMS Keys
![Stacks](../main/attachments/Clipboard_2022-09-11-16-41-32.png?raw=true "Optional Title")
- Used to be called Customer Master Keys but now called KMS Keys
- Managed by KMS and used within cryptographic operations.
- AWS services, applications, and the user can all use them.
- It is logical and contains
  - Key ID: unique identifier for the key
  - Creation Date
  - Key Policy: a type of resource policy
  - Description
  - State of the Key: active or not
- Think of them as a container for the actual physical master keys.
- These are all backed by **physical** key material.
- You can generate or import the key material.
- KMS can be used for up to **4KB of data**.

#### 1.5.5.2. Data Encryption Key (DEK)
- Generated by KMS using the KMS Key and `GenerateDataKey` operation.
- Used to encrypt data larger than 4KB in size.
- Linked to a specific KMS Key so KMS can tell that a specific DEK was
generated with a specific KMS Key.

KMS does not store the DEK, once provided to a user or service, it is discarded. KMS doesn't actually perform the encryption or decryption of data using the DEK or anything past generating them.

When the DEK is generated, KMS provides two version.

- Plaintext Version - This can be used immediately.
- Ciphertext Version - Encrypted version of the DEK.
  - This is encrypted by the KMS Key that generated it.
  - In the future it can be decrypted by KMS using the KMS Key assuming
  you have the permissions.

Architecture
![Stacks](../main/attachments/Clipboard_2022-09-11-16-47-12.png?raw=true "Optional Title")
1. DEK is generated right before something is encrypted.
2. The data is encrypted with the plaintext version of the DEK.
3. Discard the plaintext data version of the DEK.
4. The encrypted DEK is stored next to the ciphertext generated earlier.

#### 1.5.5.3. KMS Key Concepts

- KMS keys are isolated to a region.
  - Never leave the region or KMS.
  - Cannot extract a KMS Key.
- AWS managed KMSs
  - Created automatically by AWS when using a service such as S3 which uses KMS for encryption.
- Customer managed KMS Key
  - Created explicitly by the customer.
  - Much more configurable, for example the key policy can be edited.
  - Can allow other AWS accounts access to KMS Key

All KMS Keys support key rotation.

- AWS automatically rotates the keys every year
- Customer managed keys rotate every year is optional but enabled by default.

KMS Keys itself contains:

- Current backing key, physical material used to encrypt and decrypt
- Previous backing keys created from rotation

KMS can create an alias which is a shortcut to a particular KMS Keys.
Aliases are also per region. 
You can create a `MyApp1` alias in all regions but they would be separate aliases, and in each region it would be pointing potentially at a different KMS Keys. 
Neither aliases or keys are global by default.

#### 1.5.5.4. Key Policy and Security(resource policy)
![Stacks](../main/attachments/Clipboard_2022-09-11-17-05-48.png?raw=true "Optional Title")
- Every Key has one (Key policies).
- Customer managed CMKs can adjust the policy.
- Unlike other policies, KMS has to be explicitly told that keys trust the AWS account that they're in.
- The trust isn't automatic so be careful when adjusting key policies.
- You always need a key policy in place so the key trusts the account and so that the account can manage it by applying IAM permission policies to IAM users in that account.
- In order for IAM to work, IAM is trusted by the account, and the account needs to be trusted by the key.
- It sets up this chain of trust from the key to the account to IAM and then to an IAM user, if they're granted any identity permissions.

### 1.5.6. KMS Key Demo

Linux/macOS commands

```bash
echo "find all the doggos, distract them with the yumz" > battleplans.txt
```

```bash
aws kms encrypt \
    --key-id alias/catrobot \
    --plaintext fileb://battleplans.txt \
    --output text \
    --query CiphertextBlob \
    --profile iamadmin-general | base64 \
    --decode > not_battleplans.enc
```

```bash
aws kms decrypt \
    --ciphertext-blob fileb://not_battleplans.enc \
    --output text \
    --profile iamadmin-general \
    --query Plaintext | base64 --decode > decryptedplans.txt
```

### 1.5.7. Object Encryption

Buckets aren't encrypted, **objects are**.
Multiple objects in a bucket can use a different encryption methods.

S3 is capable of supporting two main methods of encryption.
Both types are encryption at rest. Data sent from a user to S3 is automatically encrypted in transit outside of these methods.
![Stacks](../main/attachments/Clipboard_2022-09-12-22-26-51.png?raw=true "Optional Title")
Client-Side encryption

- Objects being encrypted by the client before they leave.
- Data being sent the whole time it is sent as cypher text.
- AWS has no way to see into the data.
- The encryption burden is on the customer and not AWS.

Server-Side encryption

- Data is encrypted in transit using HTTPS
- Data inside the tunnel is still in its original unencrypted form.
- Data reaches S3 server in plain text form.
- After S3 sees the data, it is then encrypted.
- AWS will handle some or all of these processes.

#### 1.5.7.1. SSE-C (Server-side encryption with customer provided keys)
![Stacks](../main/attachments/Clipboard_2022-09-12-22-32-07.png?raw=true "Optional Title")
- Customer is responsible for the keys themselves.
- S3 services manages the actual encryption and decryption
  - Offloads CPU requirements for encryption.
- Customer still needs to generate and manage the key.
- S3 will see the unencrypted object throughout this process.

SSE-C Encryption Steps

1. When placing an object in S3, you provide encryption key and plaintext object
2. Once the key and object arrive, it is encrypted.
3. A hash of the key is taken and attached to the object.
The hash can identify if the specific key was used to encrypt the object.
4. The key is then discarded after the hash is taken.
5. The encrypted and one-way hash are stored persistently on storage.

To decrypt the object, you must tell S3 which object to decrypt and provide it with the key used to encrypt it. If the key that you supply is correct, compare by the proper hash, S3 will decrypt the object, discard the key, and return the plaintext version of the object.

#### 1.5.7.2. SSE-S3 AES256 (Server-side encryption w/ Amazon S3 managed keys)
![Stacks](../main/attachments/Clipboard_2022-09-12-23-00-48.png?raw=true "Optional Title")
AWS handles both the encryption and decryption process as well as the key generation and management. This provides very little control over how the keys are used, but has little admin overhead.

SSE-S3 Encryption Steps

1. When putting data into S3, only need to provide plaintext.
2. S3 generates fully managed and rotated **master key** automatically.
3. Object generates a key specific for each object that is uploaded.
4. The master key is used to encrypt the specific object key, and the
unencrypted version of that key is discarded.
5. The encrypted file and encrypted key are stored side by side in S3.

Three Problems with this method:

- Not good for regulatory environment where keys and access must be controlled.
- No way to control key material rotation.
- No role separation. A full S3 admin can decrypt data and open objects.

#### 1.5.8.3. SSE-KMS
(Server-side encryption w/ customer master keys stored in AWS KMS)
![Stacks](../main/attachments/Clipboard_2022-09-12-23-04-21.png?raw=true "Optional Title")
Much like SSE-S3, where AWS handles both the keys and encryption process.
KMS handles the master key and not S3. The first time an object is uploaded, S3 works with KMS to create an AWS managed KMS key. This is the default key which gets used in the future.

Every time an object is uploaded, S3 uses a dedicated key to encrypt that object and that key is a data encryption key which KMS generates using the KMS key.
The KMS key does not need to be managed by AWS and can be a customer managed KMS key.

SSE-KMS Encryption Steps

1. S3 is provided a plaintext version of the data encryption key as well as an encrypted version.
2. The data is encrypted with the plaintext key and the key discarded.
3. The encrypted key is stored alongside the encrypted object.

When uploading an object, you can create and use a customer managed key (KMS key). This allows the user to control the permissions and the usage of the key material. In regulated industries, this is reason enough to use SSE-KMS. You can also add logging and see any calls against this key from CloudTrail.

The best benefit is the role separation. To decrypt any object, you need access to the CMK that was used to generate the unique key that encrypted them. The CMK is used to decrypt the data encryption key for that object. That decrypted data encryption key is used to decrypt the object itself. If you don't have access to KMS, you don't have access to the object.

#### 1.5.8.4. Summary

With client side encryption, you handle both the key management and the encryption processes. So use this method. If you absolutely need to control both of these or you don't trust AWS and their regular audits. It uses more resources to manage keys and actually perform the encryption processes at scale but it's definitely the method that gives you the most control.

With SSE-C you manage the keys. You can use the same key for everything which is insecure or you could use individual keys. The choice is yours, but you manage the Keys and S3 handles the overhead for encryption and decryption.

With SSE-S3, this uses AES256. I mention this because it's often the way exam questions test your knowledge. So AES256 is the encryption algorithm and S3 handles the Keys and the encryption processes when you utilize SSE-S3. It probably should be your default if you want encryption but you don't have any real control over keys, their Permissions or their rotation.

SSE-KMS uses KMS and KMS keys. You can control key rotation. You can control key permissions. It's otherwise similar to SSE-S3 but it allows role separation. So use this if your business has fairly rigid groups of people and compartmentalized sets of security. You can have S3 for administrators who don't have any access to decrypt and access data.

![Stacks](../main/attachments/Object-Encryption-PART1_learn.cantrill.io-29_03_2023-21_01_15.png?raw=true "Optional Title")

#### 1.5.8.5. Default bucket encryption

When you're uploading objects to S3 you're actually utilizing the put object operation. As part of this operation, you can specify a specific Header which is x-amz-server-side-encryption.

If you do specify this header if you use AES256, then this utilizes SSE-S3. If you specify AWS:KMS, then SSE-KMS is utilized.

So let's say that we set the Default to be AES256 then SSE-S3 would be used when you don't set something at an object level.

This is the key thing. The bucket Default is just that, a default. It applies only when you don't specify anything explicitly on an object. If you do, that takes priority.

![Stacks](../main/attachments/Object-Encryption-PART1_learn.cantrill.io-29_03_2023-21_10_54.png?raw=true "Optional Title")

#### 1.5.8.6. S3 Bucket Keys

![Stacks](../main/attachments/Screenshot-from-2023-04-29-22-28-40.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-29-22-29-40.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-29-22-31-50.png?raw=true "Optional Title")

### 1.5.8. S3 Object Storage Classes

Picking a storage class can be done while uploading a specific object.
The default is S3 standard. Once an object is uploaded to a specific class, it can be easily changed as long as some conditions are met.

Objects in S3 are stored in a specific region.

#### 1.5.8.1. S3 Standard
![Stacks](../main/attachments/Clipboard_2022-09-13-22-18-47.png?raw=true "Optional Title")
- Default AWS storage class that's used in S3, should be user default as well.
- S3 Standard is region resilient, and can tolerate the failure of an AZ.
- Objects are replicated to at least 3+ AZs when they are uploaded.
- 99.999999999% durability
- 99.99% availability
- Offers low latency and high throughput.
- No minimums, delays, or penalties.
- Billing is storage fee, data transfer fee, and request based charge.
- Good for frequent access and import/non replaceable data

All of the other storage classes trade some of these compromises for another.

#### 1.5.8.2. S3 Standard-IA (infrequent access)
![Stacks](../main/attachments/Clipboard_2022-09-13-22-30-11.png?raw=true "Optional Title")
- Designed for less frequent rapid access when it is needed.
- Cheaper rate to store data you will rarely need, but if you do need it, you need it quickly.
- ~50% cheaper than S3 standard.
- Retrieval fee for every GB of data retrieved from this class.
- 99.9% availability, slightly lower than standard S3.
- Minimum 128KB charge for each object.
  - Cost benefits might be negated for smaller objects.
- 30 days minimum duration charge per object.

Designed for data that isn't accessed often (once a month), long term storage, backups, disaster recovery files. The requirement for data to be safe is most important.

#### 1.5.8.3. One Zone-IA
![Stacks](../main/attachments/Clipboard_2022-09-13-22-33-37.png?raw=true "Optional Title")
- Designed for data that is accessed less frequently but needed quickly.
- 80% of the base cost of Standard-IA.
- Same minimum size and duration fee as Standard-IA
- Data is only stored in a single AZ, no 3+ AZ replication.
- 99.5% availability, lower than Standard-IA

Great choice for secondary copies of primary data or backup copies.

If data is easily creatable from a primary data set, this would be a great place to store the output from another data set.

#### 1.5.8.4. S3 Glacier Instant
![Stacks](../main/attachments/Clipboard_2022-09-13-22-41-36.png?raw=true "Optional Title")
- Similar to S3 IA
- Cheaper storage higher retrieval fee
- Still instant retrieval
- min 90 days duration charge (can be stored for less but billed for 90 days)
- Still 99.999999999% durability/ 3-AZ

Use for long live data with infrequent access (once a quarter)

#### 1.5.8.5. S3 Glacier Flexible
![Stacks](../main/attachments/Clipboard_2022-09-13-22-51-29.png?raw=true "Optional Title")
- 1/6 of the base cost of S3 standard
- No immediate access to objects, retrieval in minutes or hours.
- Not publicly accessible, need retrieval process for data access.
- Make a request to access objects then after a duration, you get access.
  - Retrieval time anywhere from 1 min - 12 hrs
- Secure, durable, and low cost storage for archival data.
- 99999999999% durability
- 99.99% availability
- 3+ AZ replication
- 40KB minimum object capacity charge
- 90 days minimum storage duration charge.

Retrieval methods:
- Expedited: 1 - 5 minutes, but is the most expensive
- Standard: 3 - 5 hours to restore.
- Bulk: 5 - 12 hours. Has the lowest cost and is good for a large set of data.
- First byte latency = minutes of hours

Use for Archival data where frequent/realtime access isn't needed (yearly access)

#### 1.5.8.6. S3 Glacier Deep Archive
![Stacks](../main/attachments/Clipboard_2022-09-13-22-55-53.png?raw=true "Optional Title")
- Designed for long term backups and.
- 4.3% of the base cost of S3 standard
- 180 days minimum storage duration charge.
- Standard retrieval within 12 hours, bulk retrieval in 48 hours.
- Cannot use to make data public or download normally.

#### 1.5.8.7. S3 Intelligent-Tiering
![Stacks](../main/attachments/Clipboard_2022-09-13-23-04-41.png?raw=true "Optional Title")
- Combination of all of S3 type
- Uses automation to remove overhead of moving objects.
- Additional fee of $0.0025 per 1,000 objects automation cost.
- If an object is not accessed for 30 days, it will move into Standard-IA.
- Move to Glacier instant after 90 days.
- After 90 days/180 days moved to Glacier flex/deep archive
  - Application need to support these 2 tiers
  - Retrieving need specific API call
- If object is access then will be move back to requent access

This is good for long lived data with charging or unknown access pattern.

### 1.5.9. S3 Lifecycle Configuration

A lifecycle configuration is a set of **rules** that consists of **actions** on a **Bucket** or **groups of obejects**.

#### 1.5.9.1. Transition Actions
![Stacks](../main/attachments/Clipboard_2022-09-13-23-37-14.png?raw=true "Optional Title")
Change the storage class over time such as:

- Move an object from S3 Standard to IA after min 30 days (1 single rule)
- Move an object from Standard-IA to glacier class need to wait another 30 days if it is from the same rule. 
  - Can by pass the 30 days if using 2 rules.
- Smaller objects can cost more due to the minumum size of each class.
- Objects must flow downwards, they can't flow in the reverse direction.

#### 1.5.9.2. Expiration Actions

Once an object has been uploaded and changed, you can purge older versions
after 90 days to keep costs down.

### 1.5.10. S3 Replication

There are two types of S3 replication available.

- Cross-Region Replication (CRR)
  - Allows the replication of objects from a source bucket to a destination bucket in **different** AWS regions.
- Same-Region Replication (SRR)
  - Allows the replication of objects from a source bucket to a destination bucket in the **same** AWS region.

Architecture for both is similar, only difference is if both buckets are in the same account or different accounts.

![Stacks](../main/attachments/Clipboard_2022-09-15-22-36-24.png?raw=true "Optional Title")
1. Same account
- The replication configuration is applied to the source bucket and configures S3 to replicate from this source bucket to a destination bucket. 
- It also configures the IAM role to use for the replication process. The role is configured to allow the S3 service to assume it based on its trust policy. 
- The role's permission policy allows it to read objects on the source bucket and replicate them to the destination bucket.
2. Different account
- When different accounts are used, the role is not by default trusted by the destination account. 
- If configuring between accounts, you must add a bucket policy on the destination account to allow the IAM role from the source account access to the bucket.

#### 1.5.10.1. S3 Replication Options

- Which objects are replicated.
  - Default is all source objects, but can select a smaller subset of objects (by prefix or tag).
- Select which storage class the destination bucket will use.
  - Default is the same type of storage, but this can be changed.
- Define the ownership of the objects.
  - The default is they will be owned by the same account as the source bucket.
  - If the buckets are in different accounts, the objects in the destination could be owned by the source account and not allowed access.
- Replication Time Control (RTC)
  - Adds a guaranteed level of SLA within 15 minutes for extra cost.
  - This is useful for buckets that must be in sync the whole time.

#### 1.5.10.2. Important Replication Tips

- Replication is not retroactive.
  - If you enable replication on a bucket that already has objects, the old
  objects will not be replicated.
- Both buckets must have versioning enabled.
- It is a one way replication process only.
- Replication by default can handle objects that are unencrypted or SSE-S3.
  - With configuration it can handle SSE-KMS, but KMS requires more
configuration to work.
  - It cannot replicate objects with SSE-C because AWS does not have the keys necessary.
- Source bucket owner needs permissions to objects. If you grant cross-account
access to a bucket. It is possible the source bucket account will not own
some of those objects.
- Will not replicate system events, glacier, or glacier deep archive.
- No deletes are replicated.

#### 1.5.10.3. Why use replication

SRR - Log Aggregation
SRR - Sync production and test accounts
SRR - Resilience with strict sovereignty requirements
CRR - Global resilience improvements
CRR - Latency reduction

### 1.5.11. S3 Presigned URL
![Stacks](../main/attachments/Clipboard_2022-09-18-20-49-42.png?raw=true "Optional Title")
A way to give another person or application access to a object inside an S3 bucket using your credentials in a safe way.

IAM admin can make a request to S3 to generate a presigned URL by providing:

- security credentials
- bucket name
- object key
- expiry date and time
- indicate how the object or bucket will be accessed

S3 will create a presigned URL and return it. This URL will have encoded insideit the details that IAM admin provided. It will be configured to expire at a certain date and time as requested by the IAM admin user.

#### 1.5.11.1. S3 Presigned URL Exam PowerUp

- You can create a presigned URL for an object you have no access to.
The object will not allow access because your user does not have access.
- When using the URL the permission that you have access to, match the identity that generated it at the moment the item is being accessed.
- If you get an access deny it means the ID never had access, or lost it.
- Don't generate presigned URLs with an IAM role.
  - The role will likely expire before the URL does.

### 1.5.12. S3 Select and Glacier Select
![Stacks](../main/attachments/Clipboard_2022-09-18-21-34-27.png?raw=true "Optional Title")
This provides a ways to retrieve parts of objects and not the entire object.

If you retrieve a 5TB object, it takes time and consumes 5TB of data.

Filtering at the client side doesn't reduce this cost.

S3 and Glacier select lets you use SQL-like statements to select part of the object which is returned in a filtered way.
The filtering happens at the S3 service itself saving time and data.

### 1.5.13. S3 Event Notifications
![Stacks](../main/attachments/Clipboard_2022-09-18-21-43-15.png?raw=true "Optional Title")
- Notification generated when events occur in a bucket.
- Can be delivered to SNS, SQS and Lambda Functions.
- Object Created
- Object Delete
- Object Restore
- Replication

S3 Event is old and can only interact with alimited number of AWS services.
EventBridge is a **better alternative**.

### 1.5.14. S3 Access Logs
![Stacks](../main/attachments/Clipboard_2022-09-18-21-50-42.png?raw=true "Optional Title")
- Use to know which type of access are occurring to the source bucket.
- Target bucket is where the log will go.
- Use Console UI or CLI/API.
- Managed by s3 log delivery group .
  - Best efforts process (can take a few hours)
  - Need access to bucket
- Useful for security and access audit.
- Need to manage life cycle (delete,movement...)

### 1.5.15. S3 Object Lock
![Stacks](../main/attachments/Clipboard_2022-09-18-22-10-21.png?raw=true "Optional Title")
- Enable for **new** bucket(Sup Req for Exist Bucket)
- Enable versioning as well. - Individual versions are locked.
- Can't suppend object lock or version if enabled.
- Write-once-Read-many(WORM) - No Delete, No Overwrite.
- 1 - Retention Period
- 2 - Legal Hold
- Both, One or the other, or none
- A bucket can have default Object Lock Setting

#### 1.5.15.1. S3 Object Lock Retention
- Specify Days & Years - A Retention Period
- ***COMPLICANCE MODE*** - Can't be adjusted, deleted, overwritten. (Not even the root user until retention expires)
- ***GOVERNANCE MODE*** - special permissions can be granted allowing lock settings to be adjusted.
- s3:BypassGovernanceRetention
- x-amzz-bypass-governance-retention:true(console default)

#### 1.5.15.2. S3 Object Lock Legal Hold
- Set on an object version - ON or OFF
- No retention
- **NO Deletes** or **Changes** until removed
- s3:PutObjectLegalHold is required to add or remove feature.
- Prevent accidental deletion of critical object versions

### 1.5.15. S3 Access Points

- S3 Access Points simplify the process of managing access to S3 Buckets and Objects.
- Rather than 1 bucket w/ 1 Bucket Policy; Create many access points; Each with different policies; Each with different network access controls for example vpc and the internet.
- Each access point has it own endpoint address for access an object within a bucket or the whole bucket but with certain restrictions.
- Create an access point via console or cli using **aws s3control create-access-point --name secretcats --accountid 1234567890 --bucket catpics**

![Stacks](../main/attachments/S3-Access-Points_learn.cantrill.io-01_04_2023-20_25_28.png?raw=true "Optional Title")

---

## 1.6. Virtual-Private-Cloud-VPC

### 1.6.1. Networking Refresher

#### 1.6.1.1. IPv4 - RFC 791 (1981)

Dotted decimal notation for human readability.

- 4 numbers from 0 to 255 separated by a period.
- Octet are the numbers between the period.

There are just over 4 billion addresses. This was not very flexible because it was either too small or large for some corporations. Some IP addresses was always left unused.

#### 1.6.1.2. Classful Addressing

- Class A range
  - Starts at `0.0.0.0` and ends at `127.255.255.255`.
  - Split into 128 class A networks
  - Handed out to large companies
- Class B Range
  - Half the range of class A.
  - Starts at `128.0.0.0` and ends at `191.255.255.255`.
- Class C Range
  - Half of range class B
  - Starts at `192.0.0.0` and ends at `223.255.255.255`.

#### 1.6.1.3. Internet / Private IPs - RFC1918

These can't communicate over the internet and are used internally only

- One class A network: `10.0.0.0` - `10.255.255.255`
- 16 Class B networks: `172.16.0.0` - `172.31.255.255`
- 256 Class C networks: `192.168.0.0` - `192.168.255.255`

#### 1.6.1.4. Classless inter-domain routing (CIDR)

CIDR networks are represented by the starting IP address of the network
called the network address and the prefix.

CIDR Example: `10.0.0.0/16`

- `10.0.0.0` is the first address on the network
- /16 is the size of the network called the prefix.
  - The bigger the prefix, the smaller the network
  - The smaller the prefix, the bigger the network.
- /16 provides 65,536 addresses.
- `10.0.0.0/17` and `10.0.128.0/17` are each half of the original example.
  - This is called **subnetting**

#### 1.6.1.5. IP address notations to remember

- `0.0.0.0/0` means all IP addresses
- `10.0.0.0/8` means 10.ANYTHING - Class A
- `10.0.0.0/16` means 10.0.ANYTHING - Class B
- `10.0.0.0/24` means 10.0.0.ANYTHING - Class C
- `10.0.0.0/32` means only 1 IP address

`10.0.0.0/16` is the equivalent of `1234` as a password. You should consider
other ranges that people might use to ensure it does not overlap.

#### 1.6.1.6. Packets

Contains:

- source IP address
- destination IP address
- data the source IP wants to communicate with the destination IP.

TCP and UDP are protocols built on top of IP.

- TCPIP means TCP running with IP
- UDPIP means UDP running with IP

TCP/UDP Segment has a source and destination port number.
This allows devices to have multiple conversations at the same time.
In AWS when data goes through network devices, filters can be set based on
IP addresses and port numbers.

#### 1.6.1.7. IPv6 - RFC 8200 (2017)

`2001:0db8:28ac:0000:0000:82ae:3910:7334`

The value is hex and there are two octets per spacing or one hextet.
The redundant zeros can be removed to create:

`2001:0db8:28ac:0:0:82ae:3910:7334`

or you can remove them all entirely once per address

`2001:0db8:28ac::82ae:3910:7334`

Each address is 128 bits long. They are addressed by the start of the network
and the prefix.
Since each grouping is 16 values, we can multiple the groups by this to achieve
the prefix.

`2001:0db8:28ac::/48` really means the network starts at
`2001:0db8:28ac:0000:0000:0000:0000:0000` and finishes at
`2001:0db8:28ac:ffff:ffff:ffff:ffff:ffff`

`::/0` represents all IPv6 addresses

### 1.6.2. VPC Sizing and Structure

VPC Consideration

- What size should the VPC be. This will limit the use.
- Are there any networks we can't use?
- Be mindful of ranges other VPCs use or are used in other cloud environments
- Try to predict the future uses.
- VPC structure with tiers (App/web/database) and resilience (availability) zones 

Example: Global Architecture 
![Stacks](../main/attachments/Clipboard_2022-09-21-23-21-14.png?raw=true "Optional Title")
- Avoid existing ip range
- Ask the business for know which ip range to avoid
![Stacks](../main/attachments/Clipboard_2022-09-21-23-24-41.png?raw=true "Optional Title")

More Considerations
- VPC min /28 network (16 IP)
- VPC max /16 (65456 IP)
- Avoid common range 10.0 or 10.1, include up to 10.10
  - Suggest starting of 10.16 for a nice clean base 2 number.

Reserve 2+ network ranges per region being used per account.
Think of the highest region you will operate in and add extra as a buffer.

An example using 4 AWS accounts.

- Regions with 2 ranges in each Region
  - 3 regions in US
  - 1 region in Europe
  - 1 region in AUS
- Total of 40 ranges, 10 ranges for each account.

#### 1.6.2.1. How to size VPC
![Stacks](../main/attachments/Clipboard_2022-09-21-23-42-28.png?raw=true "Optional Title")
A subnet is located in one availability zone.
Try to split each subnet into tiers (web, application, db, spare).
Since each Region has at least 3 AZ's, it is a good practice to start splitting the network into 4 different AZs.
This allows for at least one subnet in each AZ, and one spare.
Taking a /16 subnet and splitting it 16 ways will make each a /20.

### 1.6.3. Custom VPC
![Stacks](../main/attachments/Clipboard_2022-09-23-19-40-45.png?raw=true "Optional Title")
- Regional Isolated and Resilient Service.
  - Operates from all AZs in that region
- Allows isolated networks inside AWS.
- Nothing IN or OUT of a VPC without explicit configuration.
  - Isolated blast radius. Any problems are limited to that VPC or anything
  connected to it.
- Flexible configuration
- Hybrid networking to allow connection to other cloud or on-prem networking.
- Default or Dedicated Tenancy. This refers to how the hardware is configured.
  - Default allows on a per resource decision later on.
  - Dedicated locks any resourced created in that VPC to be on dedicated hardware which comes at a cost premium.

#### 1.6.3.1. Custom VPC Facts

IPv4 private and public IPs

- Allocated 1 mandatory private IPv4 CIDR blocks
  - Min /28 prefix (16 IP)
  - Max /16 prefix (65,536 IP)
- Can add secondary IPv4 Blocks after creation.
  - Max of 5, can be increased with a support ticket
  - When thinking of VPC, it has a pool of private IPv4 addresses and can
  use public addresses when needed.

Single assigned IPv6 /56 CIDR block

- Still being matured, not everything works the same as IPv4.
- With increasing use of IPv6, this should be added as a default
- Range is either allocated by AWS as in you have no choice on which range
to use, or you can select to use your own IPv6 addresses which you own.
- IPv6 does not have private addresses, they are all routed as public by
default.

#### 1.6.3.2. DNS provided by R53
- Provided by R53
- Available on the base IP address of the VPC + 2.
- If the VPC is `10.0.0.0` then the DNS IP will be `10.0.0.2`

Two options that manage how DNS works in a VPC:

- Edit DNS hostnames
  - If true, instances with public IPs in a VPC are given public DNS hostnames.
  - If false, this is not available.

- Edit DNS resolution
  - If true, instances in the VPC can use the DNS IP address.
  - If false, this is not available.

### 1.6.4. VPC Subnets

- AZ Resilient subnetwork of a VPC.
  - If the AZ fails, the subnet and services also fail.
  - High availability needs multiple components into different AZs.
- 1 subnet can only have 1 AZ.
- 1 AZ can have zero or many subnets.
- IPv4 CIDR is a subset of the VPC CIDR block.
  - Cannot overlap with any other subnets in that VPC
- Subnet can optionally be allocated IPv6 CIDR block.
  - (256 /64 subnets can fit in the /56 VPC)
- Subnets can communicate with other subnets in the VPC by default.

#### 1.6.4.1. Reserved IP addresses

There are five IP addresses within every VPC subnet that you cannot use.
Whatever size of the subnet, the IP addresses are five less than you expect.

If using `10.16.16.0/20` (`10.16.16.0` - `10.16.31.255`)

- Network address: `10.16.16.0`
- Network + 1: `10.16.16.1` - VPC Router
- Network + 2: `10.16.16.2` - Reserved for DNS
- Network + 3: `10.16.16.3` - Reserved for future AWS use
- Broadcast Address: `10.16.31.255` (Last IP in subnet)

#### 1.6.4.2. DHCP Options Set 
Dynamic host configuration protocol.
This is how computing devices receive IP addresses automatically. There is one options set applied to a VPC at one time and this configuration flows through to subnets.

- This can be changed, can create new ones, but you cannot edit one.
- If you want to change the settings
  - You can create a new one
  - Change the VPC allocation to the new one
  - Delete the old one

#### 1.6.4.3. IP allocation Options

- Auto Assign public IPv4 address
  - This will create a public IP address in addition to their private subnet.
  - This is needed to make a subnet public.
- Auto Assign IPv6 address
  - For this to work, the subnet and VPC need an allocation of addresses.

### 1.6.5. VPC Routing and Internet Gateway

- VPC Router is a highly available device available in every VPC which moves traffic from somewhere to somewhere else.
- Router has a network interface in every subnet in the VPC.
- Routes traffic between subnets.
- Controlled by 'route tables' each subnet has one.
  - Route tables defines what the VPC router will do with traffic when data leaves that subnet.
- A VPC is created with a **main route** table. If you don't associate a custom route table with a subnet, it uses the main route table of the VPC.
- If you do associate a custom route table you create with a subnet, then the main route table is disassociated. 
- A subnet can only have one route table associated at a time, but a route table can be associated by many subnets.

#### 1.6.5.1. Route Tables
![Stacks](../main/attachments/Clipboard_2022-09-27-18-53-52.png?raw=true "Optional Title")
When traffic leaves the subnet that this route table is associated with, the VPC router reviews the IP packets looking for the destination address.
The traffic will try to match the route against the route table. 
If there are more than one routes found as a match, the prefix is used as a priority.
The higher the prefix, the more specific the route, thus higher priority.
If the target says local, that means the destination is in the VPC itself.
Local route can never be updated, they're always present and the local route always takes priority. This is the exception to the prefix rule.

#### 1.6.5.2. Internet Gateway

A managed service that allows gateway traffic between the VPC and the internet or AWS Public Zones (S3, SQS, SNS, etc.)

- Regional resilient gateway attached to a VPC.
- One IGW will cover all AZ's in a region the VPC is using.
- A VPC can have either:
  - No IGW and be entirely private.
  - One IGW
- IGW can be created and attached to no VPC.
- Runs from within the AWS public zone.

#### 1.6.5.3. Using IGW
![Stacks](../main/attachments/Clipboard_2022-09-27-19-08-08.png?raw=true "Optional Title")
In this example, an EC2 instance has:

- Private IP address of 10.16.16.20
- Public address of 43.250.192.20

The public address is not public and connected to the EC2 instance itself.
Instead, the IGW creates a record that links the instance's private IP to the public IP. This is why when an EC2 instance is created it only sees the private IP address. This is IMPORTANT. For IPv4 it is not configured in the OS with the public address.

When the linux instance wants to communicate with the linux update service, it makes a packet of data.
The packet has a source address of the EC2 instance and a destination address of the linux update server. At this point the packet is not configured with any public addressing and could not reach the linux update server.

The packet arrives at the internet gateway.

The IGW sees this is from the EC2 instance and analyzes the source IP address.
It changes the packet source IP address from the linux EC2 server and puts on the public IP address that is routed from that instance. The IGW then pushes that packet on the public internet.
![Stacks](../main/attachments/Clipboard_2022-09-27-19-09-13.png?raw=true "Optional Title")
On the return, the inverse happens. As far as it is concerned, it does not know about the private address and instead uses the instance's public IP address.

If the instance uses an IPv6 address, that public address is good to go. The IGW does not translate the packet and only pushes it to a gateway.

#### 1.6.5.4. Bastion Host / Jumpbox

It is an instance in a public subnet inside a VPC.
These are used to allow incoming management connections.
Once connected, you can then go on to access internal only VPC resources.
Used as a management point or as an entry point for a private only VPC.

This is an inbound management point. Can be configured to only allow specific IP addresses or to authenticate with SSH. It can also integrate with your on premise identification service.

### 1.6.6. Network Access Control List (NACL)

![Stacks](../main/attachments/Screenshot-from-2023-04-04-15-28-03.png?raw=true "Optional Title")
![Stacks](../main/attachments/Screenshot-from-2023-04-04-15-27-25.png?raw=true "Optional Title")
![Stacks](../main/attachments/Clipboard_2022-09-27-20-42-32.png?raw=true "Optional Title")
![Stacks](../main/attachments/Clipboard_2022-09-27-20-43-07.png?raw=true "Optional Title")
Network Access Control Lists (NACLs) are a type of security filter
(like firewalls) which can filter traffic as it enters or leaves a subnet.
![Stacks](../main/attachments/Clipboard_2022-09-29-21-30-30.png?raw=true "Optional Title")
All VPCs have a default NACL, this is associated with all subnets of that VPC by default.
NACLs are used when traffic enters or leaves a subnet.
Since they are attached to a subnet and not a resource, they only filter data as it crosses in or out.
If two EC2 instances in a VPC communicate, the NACL does nothing because it is not involved.

NACLs have an inbound and outbound sets of rules.

When a specific rule set has been called, the one with the lowest rule number first.
As soon as one rule is matched, the processing stops for that particular piece of traffic.

The action can be for the traffic to **allow** or **deny** the traffic.

Each rule has the following fields related to traffic

- type
- protocol: tcp, udp, or icmp
- port range
- Inbound rule: Source - who traffic is from
- Outbound rule: Destination - who traffic is destined to

Examples:

- ssh: tcp port 22
- http: tcp port 80
- https: tcp port 443
- ping traffic: icmp

If all of those fields match, then the first rule will either allow or deny.

The rule at the bottom with `*` is the **implicit deny**. 
This cannot be edited and is defaulted on each rule list.
If no other rules match the traffic being evaluated, it will be denied.

#### 1.6.6.1. NACLs example below
![Stacks](../main/attachments/Clipboard_2022-09-29-21-39-22.png?raw=true "Optional Title")
- Bob wants to view a blog using https(tcp/443)
- We need a NACL rule to allow TCP on port 443.
- All IP communication has two parts
  - Request
  - Response
- Bob is requesting a connection to the server to ask for a webpage.
- Server will respond with an **Ephemeral** port.
- Bob talks to the webserver connecting to a port on that server (tcp/443).
  - This is a well known port number
- Bob's PC tells the server it can talk to back to Bob on a specific port.
  - Wide range from port 1024, 65535.
  - That response is outbound traffic.
- When using NACLs, you must add an outbound port for the response traffic
as well as the inbound port. This is the ephemeral port.
- If the webserver is not managing the apps server, it may communicate
back on a different port.
- This back and forth communication can be hard to configure for.

#### 1.6.6.2. NACL Exam PowerUp

- NACLs are stateless
  - Request and response traffic are separate streams requiring two rules.
- NACLs are attached to subnets and only filter data as it crosses the subnet boundary. Two EC2 instances in the same subnet will not check against
the NACLs when moving data.
- Can explicitly allow and deny traffic. If you need to block one particular thing, you need to use NACLs.
- They only see IPs, ports, protocols, and other network connections.
No logical resources can be changed with them.
- NACLs cannot be assigned to specific AWS resources.
- NACLs can be used with security groups to add explicit deny (Bad IPs/nets)
- One subnet can only be assigned to one NACL at a time.

NACLs are processed in order starting at the lowest rule number until it gets to the catch all. A rule with a lower rule number will be processed before another rule with a higher rule number.

### 1.6.7. Security Groups

- SGs are boundaries which can filter traffic.
- SGs have two sets of rules like NACLs.
- SGs are stateful.
  - Only one inbound rule is needed.
  - They see traffic and response as the same thing.
- SG cannot explicit deny anything.
  - NACLs are used in conjunction with SGs to do explicit denys.
- Understand AWS logical resources so they're not limit to IP traffic only.
  - Can have a source and destination referencing the instance and not the IP.
- Default SG is created in a VPC to allow all traffic.
  - Does so by referencing itself. Anything this SG is attached to is matched by this rule.
- Attached to a ENI's (network interface) and not instances.
- SGs have a hidden implicit **Deny**.
  - Anything that is not allowed in the rule set for the SG is implicitly denied.
#### 1.6.7.1. SG Logical References
![Stacks](../main/attachments/Clipboard_2022-09-29-22-05-54.png?raw=true "Optional Title")
- Source can reference SG.
- SG references applies to anything which has the SG attached.
#### 1.6.7.2. SG Self References
![Stacks](../main/attachments/Clipboard_2022-09-29-22-09-03.png?raw=true "Optional Title")
- IP changes are automatically handled
- Within a SG a "SG source" is the same as "anything with the SG attached". 
- Using a "self reference" means "anything with this SG attached"
- Scales with ADDS and REMOVES from the SG
#### 1.6.7.3. SGs vs NACL
- NACLs are used when products cannot use SGs, e.g. NAT Gateways.
- NACLs are used when adding explicit deny, such as bad IPs or bad actors.
- SGs is the default almost everywhere because they are stateful.
- NACLs are associated with a subnet and only filter traffic that crosses that boundary. If the resource is in the same subnet, it will not do anything.

### 1.6.8. Network Address Translation (NAT) Gateway
![Stacks](../main/attachments/Clipboard_2022-10-05-21-51-36.png?raw=true "Optional Title")
Set of different processes that can address IP packets by changing their source or destination addresses.

**IP masquerading**, hides CIDR block behind one IP. This allows many IPv4 addresses to use one public IP for **outgoing** internet access.
Incoming connections don't work. Outgoing connections can get a response returned.

- Must run from a public subnet to allow for public IP address.
  - Internet Gateway subnets configure to allocate public IPv4 addresses
  and default routes for those subnets pointing at the IGW.
- Uses Elastic IPs (Static IPv4 Public)
  - Don't change
  - Allocated to your account
- AZ resilient service , but HA in that AZ.
  - If that AZ fails, there is no recovery.
- For a fully region resilient service, you must deploy one NATGW in each AZ
with a Route Table in each AZ with NATGW as target.
- That means if you choose to make an instance in private subnet that have a default IPv6 route to IG, it'll become public instance.
- Managed service, scales up to 45 Gbps. Can deploy multiple NATGW to increase
bandwidth.
- AWS charges on usage per hour and data volume processed.
![Stacks](../main/attachments/Clipboard_2022-10-05-22-02-02.png?raw=true "Optional Title")
- NAT instance is limited by capabilities of the instance it is running on and that instance is also general purpose, so won't offer the same level of custom design performance as NAT Gateway.
- You can connect to NAT instance just like any other instance, you can use them as Bastion host or can use them for port forwarding.
- NAT instance is single instance running in single AZ it'll fail if EC2 hardware fails, network fails, storage fails or AZ itself fails.
- NAT Gateway has benefit over NAT instance, inside one AZ it is highly available.
- With NAT Gateway it is not possible, it is managed service. NAT Gateway cannot be used as Bastion host and it cannot do port forwarding.
- You cannot use Security Group with NAT instance, you can only use NACLs.
- NAT is not required for IPv6. Inside AWS all IPv6 addresses are publicly routable. IG works with all IPv6 addresses directly.
- NATGW does not work with IPv6
- ::/0 Route + IGW for bi-directional connectivity
- ::/0 Route + Egress-Only IGW-Outbound only

NATGW cannot do port forwarding or be a bastion server. In that case it might be necessary to run a NAT EC2 instance instead.

---

## 1.7. ELASTIC COMPUTE CLOUD (EC2) BASICS

### 1.7.1. Virtualization 101

EC2 provides Infrastructure as a Service (IAAS Product)

Servers are configured in three sections without virtualization

- CPU hardware
- Kernel
  - Operating system
  - Runs in Privileged mode and can interact with the hardware directly
- User Mode
  - Runs applications
  - Can make a **system call** to the Kernel to interact with the hardware
  - If an app tries to interact with the hardware without a system call, it
  will cause a system error and can crash the server or at minimum the app

#### 1.7.1.1. Emulated Virtualization - Software Virtualization

A host OS operated on the hardware, and it included a hypervisor
The software ran in privileged mode and had full access to the hardware on the
server.

Guest operating systems were wrapped in a virtual machine and had devices
mapped into their OS to emulate real hardware. Drivers such as graphics cards
were all software emulated to allow the process to run properly.

The guest OS still believed they were running on real hardware and tried
to take control of the hardware. The areas were not real and only allocated
space to them for the moment.

The hypervisor performs **binary translation**. Any calls attempted to make
are intercepted and translated in software on the way. The guest OS needs no
modification, but it slows the guest OS down a lot.

#### 1.7.1.2. Para-Virtualization

Guest OS are still running in containers, except they do not use slow
binary translation. This only works on a small subset of OS that can be
modified. The OS is modified to change the **system calls** to **user calls**.
Instead of calling on the hardware, they call on the hypervisor called
hyper-calls. Areas of the OS call the HV instead of the hardware. They need
to be modified for the particular vendor reforming the para-virtualization.

The OS becomes virtualization aware and got faster, but this was still a
software trick.

#### 1.7.1.3. Hardware Assisted Virtualization

The physical hardware itself is virtualization aware. The CPU has specific
functions so the hypervisor can come in and support. When guest OS try to run
privileged instructions, they are trapped by the CPU and do not halt
the process. They are redirected to the hypervisor from the hardware.

What matters for a virtual machine is the input and output operations such
as network transfer and disk IO. The problem is multiple OS try to access
the same piece of hardware, but they get caught up on sharing.

#### 1.7.1.4. SR-IOV (Singe Route IO virtualization)

Allows a network or any addon card to present itself as many mini cards.
As far as the hardware is concerned, they are real dedicated cards for their
use. No translation needs to be done by the hypervisor. The physical card
handles their own process internally. In EC2 this feature is called
**enhanced networking**. This means less CPU usage for the guest.

### 1.7.2. EC2 Architecture and Resilience

![Stacks](../main/attachments/Screenshot-from-2023-04-06-10-32-14.png?raw=true "Optional Title")

- EC2 instances are virtual machines (OS+Resources)
- Run on EC2 hosts
- Shared hosts or dedicated hosts
  - Every customer is isolated even on the same shared hardware
  - Dedicated hosts pay for entire host, don't pay for instances
- AZ resilient service. They run within only one AZ system.

Example AZ with an EC2 host

- Run within single AZ
- Local hardware such as CPU and memory
- Also have instance store
  - Temporary
  - If instance moves hosts, the storage is lost
- Networking
  - Storage networking
  - Data networking

When instances are provisioned within a specific subnet within a VPC
A primary elastic network interface is provisioned in a subnet which
maps to the physical hardware on the EC2 host. Subnets are also within
one specific AZ. Instances can have multiple network interfaces, even within
different subnets so long as they're within the same AZ.

EC2 can make use of remote storage, Elastic Block Store (EBS).

EBS also runs within a specific AZ. You can't access them cross zone.

EBS allows you to allocate volumes of persistent storage to instances
within the same AZ.

An instance runs on a specific host. If you restart the instance
it will stay on that host.

Instances stay on the host until either

- The host fails or is taken down by AWS
- The instance is stopped and then started, different than restarted.

The instance will be relocated to another host in the same AZ. Instances
cannot move to different AZs. Everything about their hardware is locked within
one specific AZ.

A migration is taking a copy of an instance and moving it to a different AZ.

In general instances of the same type and generation will occupy the same host.
The only difference will generally be their size.

#### 1.7.2.1. EC2 Strengths

Traditional OS+Application compute need. A specific OS with a specific hardware
setup.

Long-running compute needs. Many other AWS services have run time limits.

Server style applications

- things waiting for network response
- burst or stead-load
- monolithic application stack
  - middle ware or specific run time components
- migrating application workloads or disaster recovery
  - existing applications running on a server and a backup system to intervene

### 1.7.3. EC2 Instance Types

Raw CPU, memory, local storage capacity, and type
Resource ratios: Some might have more CPU while others have more storage.
Storage and Data network Bandwidth

Influences the architecture and vendor.
AMD CPU vs Intel CPU

Influences features and capabilities with that instance

#### 1.7.2.1. EC2 Categories

General Purpose - default steady state workloads with even resources
Compute Optimized - Media processing, scientific modeling and gaming
Memory Optimized - Processing large in-memory datasets
Accelerated Computing - Hardware GPU, FPGAs
Storage Optimized - Large amounts of super fast local storage. Massive amounts
of IO per second. Elastic search and analytic workloads.

#### 1.7.2.1. Naming Scheme

![Stacks](../main/attachments/Screenshot-from-2023-04-06-11-47-44.png?raw=true "Optional Title")

R5dn.8xlarge - whole thing is the instance type. When in doubt give the
full instance type

- 1st char: Instance family. No expectation to remember all the details
- 2nd char: Instance generation. Generally always select the newest generation.
- char after period: Instance size. Memory and CPU considerations.
  - often easier to scale system with a larger number of smaller instance sizes
- 3rd char - before period: additional capabilities
  - a: amd cpu
  - d: nvme storage
  - n: network optimized
  - e: extra capacity for ram or storage

![Stacks](../main/attachments/Screenshot-from-2023-04-06-12-03-58.png?raw=true "Optional Title")

### 1.7.3. Storage Refresher

**Direct** local attached storage - these are physical disks on EC2

**Network** attached storage - volumes delivered over the network (EBS)

**Ephemeral** storage - temporary storage. Instant store attached to EC2 host

**Persistent** storage - permanent storage that lives on past the lifetime
of the instance. EBS is persistent storage.

#### 1.7.3.1. Three types of storage

![Stacks](../main/attachments/Screenshot-from-2023-04-06-13-57-05.png?raw=true "Optional Title")

Block Storage - volume presented to the OS as a collection of blocks. No
structure beyond that. These are mountable and bootable. The OS will
create a file system on top of this, NTFS or EXT3, and then it mounts
it as a drive or a root volume on Linux. Spinning hard disks or SSD. This
could also be delivered by a physical volume. Has no built-in structure.
You can mount an EBS volume or boot off an EBS volume.

File Storage - Presented as a file share with a structure. You access the
files by traversing the storage. You cannot boot from storage, but you
can mount it.

Object Storage - It is a flat collection of objects. An object can be anything
with or without attached metadata. To retrieve the object, you need to provide
the key and then the value will be returned. This is not mountable or
bootable. It scales very well and can have simultaneous access.

#### 1.7.3.2. Storage Performance

![Stacks](../main/attachments/Screenshot-from-2023-04-06-14-03-52.png?raw=true "Optional Title")

IO Block Size - size of the wheels. This determines how to split up the data.
IOPS - speed of an engine rev (RPM). How many reads or writes a storage
system can accommodate in a second.
Throughput - end speed of the race car. This can be influenced by the network
speed for network storage. Expressed in MB/s (megabyte per second).

Block Size * IOPS = Throughput

This isn't the only part of the chain, but it is a simplification.

A system might have a throughput cap. The IOPS might decrease as the block
size increases.

### 1.7.4. Elastic Block Store (EBS)

Allocate block storage **volumes** to instances.
Volumes are isolated to one AZ.

- The data is highly available and resilient for that AZ.
- All the data is replicated within that AZ. The entire AZ must have
a major fault to go down.
- Attached to one EC2 instance (or other service) over a storage network.
- Detached and reattached, not lifecycle linked to on instance.
- Snapshot (backup) into S3. Create volume from snapshot (migrate between AZs).
- Different physical storage types available (SSD/HDD)
- Varying level of performance (IOPS, T-put)
- Billed as GB/month.
  - If you provision a 1TB for an entire month, you're billed as such.
  - If you have half of the data, you are billed for half of the month.

![Stacks](../main/attachments/Screenshot-from-2023-04-06-14-56-10.png?raw=true "Optional Title")

Each volume has a dominant performance attribute

SSD based focus on maximum IOPS such as a database
HDD based focus on throughput for logs or media storage.

#### 1.7.4.1. General Purpose SSD (gp2)

Uses a performance bucket architecture based on the iops it can deliver.

The GP2 starts with 5,400,000 IOPS allocated. It is available instantly.

You can consume the capacity quickly or slowly over the life of the volume.

The capacity is filled back based upon the volume size.

Min of 100 iops added back to the bucket per second.
Above that, there are 3 IOPS/GiB of volume size. The max is 16,000 IOPS.

This is the **baseline performance**

This should be the default for boot volumes and some data volumes.

Can only be attached to one volume at a time.

![Stacks](../main/attachments/Screenshot-from-2023-04-06-15-25-36.png?raw=true "Optional Title")

#### 1.7.4.2. General Purpose SSD (gp3)

![Stacks](../main/attachments/Screenshot-from-2023-04-06-15-28-51.png?raw=true "Optional Title")

GP3 is also SSD based, but it removes the credit bucket architecture of GP2 for something much simpler.
Every GP3 volume regardless of size starts with the standard 3,000 IOPS.
So 3,016 KB operations per second and it can transfer 125 MB per second.
That's standard regardless of volume size, and just like GP2, volumes can range from one GB through to 16 TB.
Now the base price for GP3 at the time of creating this lesson is 20% cheaper than GP2.
So if you only intend to use up to 3,000 IOPS then it's a no-brainer.
You should pick GP3, rather than GP2. If you need more performance then you can pay for up to 16,000 IOPS and up to 1,000 MB per second of throughput.
And even with those extras, generally it works out to be more economical than GP2.
GP3 offers a higher max throughput as well so you can get up to 1,000 MB per second versus the 250 MB per second maximum of GP2. 
So GP3 is just simpler to understand for most people versus GP2.
And I think over time, it's going to be the default.
For now though, at the time of creating this lesson GP2 is still the default. 
In summary, GP3 is like GP2 and IO1 which I'll cover soon had a baby.
You get some of the benefits of both in a new type of general purpose SSD storage.
Now the usage scenarios for GP3 are also much the same as GP2.
So virtual desktops, medium-sized databases, low-latency applications,dev and testing environments and boot volumes.
You can safely swap GP2 to GP3 at any point, but just be aware that for anything above 3,000 IOPS, the performance doesn't get added automatically like with GP2, which scales on size.
With GP3 you would need to add these extra IOPS which come at an extra cost. And that's the same with any additional throughput.
Beyond the 125 MB per second standard, it's an additional extra, but still even including those extras for most things this storage type is more economical than GP2.

#### 1.7.4.3. Provisioned IOPS SSD (io1)

![Stacks](../main/attachments/Screenshot-from-2023-04-06-20-45-45.png?raw=true "Optional Title")

When dealing with these types of volumes, it is important to keep in mind the per-instance performance, which is the maximum performance that can be achieved between the EBS service and a single EC2 instance. These maximums are influenced by the type of volumes, type of instance, and size of the instance. The most modern and largest instances support the highest levels of performance, and multiple volumes are needed to saturate the per-instance performance level.

#### 1.7.4.4. HDD Volume Types

st1 - Throughput Optimized HDD
sc1 - Cold HDD

![Stacks](../main/attachments/Screenshot-from-2023-04-06-23-53-38.png?raw=true "Optional Title")

##### 1.7.4.5. st1

So think about st1 as the fast hard drive, not very agile, but pretty fast, and think about sc1 as cold.

st1 is cheap. It's less expensive than the SSD volumes, which makes it ideal for any larger volumes of data.

sc1 is even cheaper, but it comes with some significant trade-offs.

Now st1 is designed for data, which is sequentially accessed.

Because it's HDD based, it's not great at random access.

It's more designed for data which needs to be written or read in a fairly sequential way.

Applications with throughput and economy is more important than IOPS or extreme levels of performance.

st1 volumes range from 125 GB to 16 TB in size, and you have a maximum of 500 IOPS, but, and this is important, IO on HDD-based volumes is measured as 1MB blocks.

So 500 IOPS means 500 MB per second. Now their maximums. 

HDD-based storage works in a similar way to how gp2 volumes work with a credit bucket, only with HDD based volumes, it's done around MB per second rather than IOPS.

So with st1, you have a baseline performance of 40 MB per second for every 1TB of volume size, and you can burst to a maximum of 250 MB per second for every TB of volume size.

Obviously, up to the maximum of 500 IOPS and 500 MB per second. st1 one is designed for when cost is a concern, but you need frequent access storage for throughput intensive sequential workloads.

So things like big data, data warehouses and log processing.

##### 1.7.4.6. sc1

sc1 on the other hand is designed for in frequent workloads.

It's geared towards a maximum economy when you just want to store lots of data and don't care about performance.

So it offers a maximum of 250 IOPS. Again, this is with a 1MB IO size, so this means a maximum of 250 MB per second of throughput, and just like with st1, this is based on the same credit pool architecture, so it has a baseline of 12 MB per TB of volume size and a burst of 80 MB per second per TB of volume size.

So you can see that this offers significantly less performance than st1, but it's also significantly cheaper. 

And just like with st1, volumes can range from 125 GB to 16 TB in size.

This storage type is the lowest cost EBS storage available.

It's designed for less frequently accessed workloads.

So if you have colder data, archives, or anything which requires less than a few loads or scans per day, then this is the type of storage volume to pick.

And that's it for HDD-based storage. Both of these are lower costs and lower performance versus SSD designed for when you need a economy of data storage.

Picking between them is simple. If you can tolerate the trade-offs of sc1, then use that.

It's super cheap and for anything which isn't day-to-day accessed, it's perfect, otherwise, choose st1.

And if you have a requirement for anything IOPS based, then avoid both of these and look at SSD based storage.

### 1.7.5. EC2 Instance Store

![Stacks](../main/attachments/Screenshot-from-2023-04-07-10-29-56.png?raw=true "Optional Title")

Local physical storage that instances can utilize attached to an instance.

**block storage** devices. They're just like EBS but they're local.

The volumes are physically connected to one EC2 host. They are isolated to
that one specific host.

Instances on that host can access them.

Highest storage performance in AWS.

They are included in instance price, use it or lose it.

They can be attached ONLY at launch. Cannot be attached later.

Architecturally, each instance has a collection of ephemeral volumes that are
locked to that specific host. Even though an instance is being allocated a
specific number of volumes, the data is locked to the host.

Instances can move between hosts for many reasons:

- If an instance is stopped and started, that migrates hosts.
- If a host undergoes AWS maintenance, it will be wiped.
- If you change the type of instance, these will be lost.
- If a physical hardware fails, then the data is gone.

The number, size, and performance of instance store volumes vary based on the
type of instance used. Some instances do not have any instance store volumes
at all.

#### 1.7.5.1. Instance Store Performance

This is much higher than EBS can provide. These volumes
perform at much higher volumes than EBS.

![Stacks](../main/attachments/Screenshot-from-2023-04-07-10-29-43.png?raw=true "Optional Title")

#### 1.7.5.2. Exam Powerup

- Instance store volumes are local to EC2 host.
- Can only be added at launch time. Cannot be added later.
- Any data on instance store data is lost if it gets moved, or resized.
- Highest data performance in all of AWS.
- You pay for it anyway, it's included in the price.
- TEMPORARY

### 1.7.6. EBS vs Instance Store

![Stacks](../main/attachments/Screenshot-from-2023-04-07-11-07-54.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-07-11-12-35.png?raw=true "Optional Title")

If the read/write can be handled by EBS, that should be default.

When to use EBS

- Highly available and reliable in an AZ. Can self correct against HW issues.
- Persist independently of EC2 instances.
  - Can be removed or reattached.
  - You can terminate instance and keep the data.
- Multi-attach feature of **io1**
  - Can create a multi shared volume.
- Region resilient backups.
- Require up to 64,000 IOPS and 1,000 MiB/s per volume
- Require up to 80,000 IOPS and 2,375 MB/s per instance

When to use Instance Store

- Great value, they're included in the cost of an instance.
- More than 80,000 IOPS and 2,375 MB/s
- If you need temporary storage, or can handle volatility.
- Stateless services, where the server holds nothing of value.
- Rigid lifecycle link between storage and the instance.
  - This ensures the data is erased when the instance goes down.

### 1.7.7. Snapshots, restore, and fast snapshot restore

![Stacks](../main/attachments/Screenshot-from-2023-04-08-11-24-32.png?raw=true "Optional Title")

EBS Snapshots

Efficient way to back up EBS volumes to S3. Protect data against AZ issues.
Can be used to migrate data between hosts.

The data becomes region resilient.

Snapshots are incremental volume copies to S3.

The first is a **full copy** of `data` on the volume. This can take some time.

EBS won't be impacted, but will take time in the background.

Future snaps are incremental, consume less space and are quicker to perform.

If you delete an incremental snapshot, it moves data to ensure subsequent
snapshots will work properly.

Volumes can be created (restored) from snapshots. Snapshots can be used to
move EBS volumes between AZs. Snapshots can be used to migrate data between
volumes.

#### 1.7.7.1. Snapshot and volume performance

When creating a new EBS volume without a snapshot, the performance is
available immediately.

If you restore a snapshot, it does it lazily.

If you restore a volume, it will transfer it slowly in the background.

If you attempt to read data that hasn't been restored yet, it will
pull it from S3, but this will achieve lower levels of performance than reading
from EBS directly.

You can force a read of all data immediately. This is something you would do
right when using a volume.

You could also use Fast Snapshot Restore (FSR) - Immediate restore

You can have up to 50 snaps per region. This is set on the snap and AZ.

FSR is not free and can get expensive with lost of different snapshots.

You can force the same response by reading every block manually using DD or
another tool in the OS.

#### 1.7.7.2. Snapshot Consumption and Billing

![Stacks](../main/attachments/Screenshot-from-2023-04-08-11-32-16.png?raw=true "Optional Title")

They are billed using a GB/month metric.

20 GB stored for half a month, represents 10 GB-month.

This is used data, not allocated data. If you have a 40 GB volume but only
use 10 GB, you will only be charged for the allocated data. This is not true
for EBS itself.

The data is incrementally stored which means doing a snapshot every 5 minutes
will not necessarily increase the charge as opposed to doing one every hour.

#### 1.7.7.3. EBS Encryption

![Stacks](../main/attachments/Screenshot-from-2023-04-08-14-46-13.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-08-14-46-24.png?raw=true "Optional Title")

Provides at rest encryption for block volumes and snapshots.

When you don't have EBS encryption, the volume is not encrypted.
The physical hardware itself may be performing at rest encryption, but
that is a separate thing.

When you set up an EBS volume initially, EBS uses KMS and a customer master key.
This can be the ebs default (CMK) which is referred to as `aws/ebs` or it
could be a customer managed CMK which you manage yourself.

That key is used by EBS when an encrypted volume is created. The CMK
generates an encrypted data encryption key which is stored with the volume with
on the physical disk. This key can only be encrypted by KMS when a role with
the proper permissions makes the request.

When the volume is first used, EBS asks CMS to decrypt the key and stores
the decrypted key in memory on the EC2 host while it's being used. At all
other times it's stored on the volume in encrypted form.

When the EC2 instance is using the encrypted volume, it can use the
decrypted data encryption key to move data on and off the volume. It is used
for all cryptographic operations when data is being used to and from the
volume.

When data is stored at rest, it is stored as **Ciphertext**.

If the EBS volume is ever moved, the key is discarded.

If a snapshot is made of an encrypted EBS volume, the same data encryption
key is used for that snapshot. Anything made from this snapshot is also
encrypted in the same way.

Everytime you create a new EBS volume from scratch, it creates a new
data encryption key.

##### 1.7.7.4. EBS Exam Power Up

AWS accounts can be set to encrypt EBS volumes by default.
It will use the default CMK unless a different one is chosen.
Each volume uses 1 unique DEK (data encryption key)
Snapshots and future volume use the same DEK
Can't change a volume to NOT be encrypted. You could mount an unencrypted
volume and copy things over, but you can't change the original volume.
The OS isn't aware of the encryption, there is no performance loss. The data
uses AES256
If an exam question does not use AES256, or it suggests you need an OS to
encrypt or hold the keys, then you need to perform full disk encryption
at the operating system level.
You can perform full disk encryption on an unencrypted or encrypted EBS
volume.

### 1.7.8. EC2 Network Interfaces, Instance IPs and DNS

![Stacks](../main/attachments/Screenshot-from-2023-04-08-20-18-16.png?raw=true "Optional Title")

An EC2 instance starts with at least one ENI - elastic network interface.

An instance may have ENIs in separate subnets, but everything must be
within one AZ.

When you launch an instance with Security Groups, they are on the
network interface and not the instance.

#### 1.7.8.1. Elastic Network Interface

![Stacks](../main/attachments/Screenshot-from-2023-04-08-20-42-39.png?raw=true "Optional Title")

Has these properties

- MAC address
- Primary IPv4 private address
  - From the range of the subnet the ENI is within.
  - 10.16.0.10 will be static and not change for the lifetime of the instance
  - Given a DNS name that is associated with the address
    - ip-10-16-0-10.ec2.internal
    - only resolvable inside the VPC and always points to private IP address
- 0 or more secondary private IP addresses

- 0 or 1 public IPv4 address given two ways
  - Instance must manually be set to receive an IPv4 addr
  - Default settings into a subnet which automatically allocates an IPv4
  - Dynamic IP that is not fixed
  - If you stop an instance the address is deallocated.
  - When you start up again, it is given a brand new IPv4 address
  - Restarting the instance will not change the IP address
  - Changing between EC2 hosts will change the address
  - They are allocated a public DNS name.
  - Public DNS name will resolve to the primary
  private IPv4 address of the instance
  - Outside the VPC, the DNS will resolve to the public IP address.
  - Allows one single DNS name for an instance, and allows traffic to resolve
  to an internal address inside the VPC and the public will resolve to a public
  IP address.

- 1 elastic IP per private IPv4 address
  - Can have 1 public elastic interface per private IP address on this interface
  - Allocated to your AWS account
  - Can associate with a private IP on the primary interface or
  on the secondary interface.
  - If you are using a public IPv4 and assign an elastic IP, the original IPv4
  address will be lost. There is no way to recover the original address.

- 0 or more IPv6 address on the interface
  - These are by default public addresses
- Security groups
  - applied to network interfaces
  - will impact all IP addresses on that interface
  - if you need different IP addresses impacted by different security
  groups, then you need to make multiple interfaces and apply different
  security groups to those interfaces
- Source / destination checks
  - if traffic is on the interface, it will be discarded if it is not
  from going to or coming from one of the IP addresses

Secondary interfaces function in all the same ways as primary interfaces except
you can detach interfaces and move them to other EC2 instances.

#### 1.7.8.2. Exam Power Ups

Legacy software is licensed using a mac address.
If you provision a secondary ENI to a specific license, you can move
around the license to different EC2 instances.

Multi homed (subnets) management and data.

Different security groups are attached to different interfaces.

The OS doesn't see the IPv4 public address.

You always configure the private IPv4 private address on the interface.

Never configure an OS with a public IPv4 address.

IPv4 Public IPs are Dynamic, starting and stopping will kill it

Public DNS for a given instance will resolve to the primary private IP
address in a VPC. If you have instance to instance communication within
the VPC, it will never leave the VPC. It does not need to touch the internet
gateway.

### 1.7.9. Amazon Machine Image (AMI)

Images of EC2.

AMI's can be used to launch EC2 instance.

- When you launch an EC2 instance, you are using an Amazon provided AMI.
- Can be Amazon or community provided
- Marketplace (can include commercial software)
  - Will charge you for the instance cost and an extra cost for the AMI
- Regional, unique ID
  - ami-`random set of chars`
- Controls permissions
  - Default only your account can use it
  - Can be set to be public
  - Can have specific AWS accounts on the AMI
- Can create an AMI from an existing EC2 instance to capture the current config

#### 1.7.9.1. AMI Lifecycle

![Stacks](../main/attachments/Screenshot-from-2023-04-08-22-38-42.png?raw=true "Optional Title")

Launch

EBS volumes are attached to EC2 devices using block IDs

- BOOT /dev/xvda
- DATA /dev/xvdf

Configure

- Can customize the instance from applications or volume sizes

Create Image

- Once it has been customized, an AMI can be created from that
- AMI contains:
  - Permissions: who can use it
  - EBS snapshots are created from attached volumes
    - Block device mapping links the snapshot IDs and a device ID for
    each snapshot.

Launch

When launching an instance, the snapshots are used to create new EBS
volumes in the availability zone of the EC2 instance and contain the same
block device mapping.

#### 1.7.9.2. Exam Powerups

AMI can only be used in one region
AMI Baking: creating an AMI from a configuration instance.
An AMI cannot be edited. If you need to update an AMI, launch an instance,
make changes, then make new AMI
Can be copied between regions
Remember permissions by default are your account only
Billing is for the storage capacity for the EBS snapshots the AMI references

### 1.7.10. EC2 Pricing Models

#### 1.7.10.1. On-Demand Instances

![Stacks](../main/attachments/Screenshot-from-2023-04-09-13-07-39.png?raw=true "Optional Title")

- Hourly rate based on OS, size, options, etc
- Billed in seconds (60s min) or hourly
  - Depends on the OS
- Default pricing model
- No long-term commitments or upfront payments
- New or uncertain application requirements
- Short-term, spiky, or unpredictable workloads which can't tolerate
any disruption.

#### 1.7.10.2. Spot Instances

![Stacks](../main/attachments/Screenshot-from-2023-04-09-13-14-09.png?raw=true "Optional Title")

Up to 90% off on-demand
Depends on the spare capacity
You can set a maximum hourly rate in a certain AZ in a certain region.
If the max size you set is above the spot price, you pay for the instance.
As the spot price increases, you'll keep paying until the price increases.
Once this price increases too much, it will terminate the instance.
Great for data analytics when the process can occur later.

#### 1.7.10.3. Reserved Instance

![Stacks](../main/attachments/Screenshot-from-2023-04-09-13-26-13.png?raw=true "Optional Title")

Up to 75% off on-demand
The trade-off is commitment.
You're buying capacity in advance for 1 or 3 years.
Flexibility on how to pay

- All up front
- Partial upfront
- No upfront

Best discounts are for 3 years all up front
Reserved in region, or AZ with capacity reservation
Reserved takes priority for AZ capacity.
Can perform scheduled reservation when you can commit to specific time windows.

If you have a known stead state usage, email usage, domain server.
Cheapest option with no tolerance for distribution.

#### 1.7.10.4. Dedicated Hosts

![Stacks](../main/attachments/Screenshot-from-2023-04-09-13-33-18.png?raw=true "Optional Title")

#### 1.7.10.5. Dedicated Instances

![Stacks](../main/attachments/Screenshot-from-2023-04-09-13-35-51.png?raw=true "Optional Title")

#### 1.7.10.6. Scheduled Reserved Instances

![Stacks](../main/attachments/Screenshot-from-2023-04-09-14-39-09.png?raw=true "Optional Title")

#### 1.7.10.7. Capacity Reservations

![Stacks](../main/attachments/Screenshot-from-2023-04-09-14-52-13.png?raw=true "Optional Title")

#### 1.7.10.8. EC2 Savings Plan

![Stacks](../main/attachments/Screenshot-from-2023-04-09-14-55-25.png?raw=true "Optional Title")

### 1.7.11. Instance Status Checks and Auto-recovery

![Stacks](../main/attachments/Screenshot-from-2023-04-09-15-51-52.png?raw=true "Optional Title")

Every instance has two high level status checks

#### 1.7.11.1. System Status Checks

Failure of this check could indicate software or hardware problems of the EC2
service or the host.

#### 1.7.11.2. Instance Status Checks

This is specific to the file system or has a corrupted Kernel

Assuming you haven't launched an instance, this is a problem and needs to be
fixed.

#### 1.7.11.3. Create Status Check Alarm

This feature has four options

- Recover this instance: can be a number of steps depending on the failure
- Stop this instance
- Terminate this instance: useful in a cluster
- Reboot this instance:

### 1.7.12. Horizontal and Vertical Scaling

#### 1.7.12.1. Vertical Scaling

As customer load increases, the server may need to grow to handle more data.
The server can increase in capacity, but this will require a reboot.
Often times vertical scaling can only occur during planned outages.
Larger instances also carry a $ premium compared to smaller instances.
There is an upper cap on performance - instance size.
No application modification is needed.
Works for all applications, even monoliths (all code in one app)

#### 1.7.12.2. Horizontal Scaling

As the customer load increases, this adds additional capacity.
Instead of one running copy of an application, you can have multiple versions
running on each server.
This requires a load balancer.
When customers try to access an application, the load balancer ensures the
servers get equal parts of the load.

Sessions are everything.
With horizontal scaling you can shift between instances equally.
This requires either application support or off-host sessions.
This means the servers are **stateless**, the app stores session data elsewhere.

No distribution while scaling up or down.

No real limits to scaling.

Uses smaller instances so you pay less, allows for better granularity.

### 1.7.13. Instance Metadata

EC2 service provides data to instances
Accessible inside all instances

Memorize **<http://169.254.169.254/latest/meta-data/>

Meta-data contains:

- environment the instance is in
- networking is the big reason why
- authentication information
  - instances can be used to gain access on other services
- user-data
- NO AUTHENTICATION or ENCRYPTED
  - Anyone who can gain access, and it can and will get exposed
  - Can be restricted by local firewall

## 1.8. Containers & ECS

### 1.8.1. Intro to Containers

Virtualisation Problems

AWS EC2 Host : base
AWS Hypervisor (Nitro)

If you run a virtual machine with 4 GB ram and 40 GB disk,
the OS can comsume 60-70% of the disk and little available
memory.

If all of the OS use the same or similar resources, they are
duplicates. Every restart must manipulate the entire OS.

What you want to do is run applications in their own
isolated enviroments for their applications to run.

Containers have isolated OS from each other.

#### 1.8.1.1. Image Anatomy

Container is a running image of docker image.

These are stacks of layers and not a monolithic disk image.

Each line of a docker image creates a new filesystem layer.

Images are created from scratch or a base image.

Images contain read only layers, images are layer onto images.

Docker container is the same as a docker image, except it
has an additional READ/WRITE layer of the container.

If you have lots of containers with very similar base
structures, they will share the parts that overlap.

The other layers are reused between containers.

#### 1.8.1.2. Container Registry

Registry or hub of container images.

Dockerfile can create a container image where it gets stored
in the container registry.

Docker hosts can run many containers between one or more images.

#### 1.8.1.3. Container Key Concepts

Dockerfiles are used to build images

Portable and always run as expected. Anywhere there is a compatable host,
it will run exactly as you intended.

Containers are super lightweight, use the host OS for the
heavy lifting, but otherwise are light. File system layers
are shared when possible.

Containers only run the application and enviroment it needs.

Ports need to be **exposed** to allow outside access from
the host and beyond.

Application stacks can be multi container

### 1.8.2. Elastic Container Service (ECS) Concepts

Accepts containers and instructions you provide.

ECS allows you to create a cluster. Clusters are where containers run from.

Container images will be located on a registry.
AWS provides ECR (elastic container registry).

Container definition tells ECS where the container image is.

Task definition represents the application as a whole and stores whatever
information is needed to run the application.

Container is just a pointer to where the container is stored and what port is
exposed. The rest is defined at the task definition.

Task definitions store the resources and networking used by the task. It stores
the compatability of how the container runs. It also stores **task role**, an
IAM role that allows the task complete its task. This is the best practice
way to give containers the access needed for other AWS resources.

A lot of tasks will only have one container definition, but a task could
include one or more containers.

Task is not by itself highly available.

ECS service - Service Definition. This defines how many copies of the task
is allowed to run to load balance. You can use a service to provide scalability
and high availability.

Tasks or services get deployed to an ECS cluster.

**Container definition** the image and the ports that will be used.

**Task definition** the task role and security is defined. This is an IAM
role that is assumed. The temporary credentials allow access to AWS products
and services.

**Task role** IAM role which the task assumes.

**Service** how many copies of a task you want to run for scaling and
high availability.

### 1.8.3. ECS Cluster Types

ECS Cluster manages

- Scheduling and Orchestration
- Cluster manager
- Placement engine

#### 1.8.3.1. EC2 mode

![Stacks](../main/attachments/Screenshot-from-2023-04-09-23-31-51.png?raw=true "Optional Title")

ECS cluster is created within a VPC. It benefits from the multiple AZs that
are within that VPC.

You specify an initial size which will drive an **auto scaling group**

ECS using EC2 mode is not a serverless solution, you need to worry about
capacity for your cluster.

The container instances are not delivered as a managed service, they
are managed as normal EC2 instances.

This is good because you can use spot pricing or prepaid EC2 servers.

#### 1.8.3.2. Fargate mode

![Stacks](../main/attachments/Screenshot-from-2023-04-09-23-35-26.png?raw=true "Optional Title")

Removes more of the management overhead from ECS, no need to manage EC2.

There is a **fargate shared infrastructure** which allows all customers
to access from the same pool of resources.

Fargate deployment still uses a cluster with a VPC where AZs are specified.

For ECS tasks, they are injected into the VPC. Each task is given an
elastic network interface which has an IP address within the VPC. They then
run like an VPC resource.

You only pay for the container resources you use.

#### 1.8.3.3. EC2 vs ECS(EC2) vs Fargate

If you already are using containers, use **ECS**

**EC2 mode** is good for a large workload with price conscious. This allows for
spot pricing and prepayment.

Large workload but overhead conscious **Fargate**

Small or burst style workloads **Fargate** makes sense

Batch or periodic workloads **Fargate**

#### 1.8.3.4. Elastic Container Registry (ECR)

![Stacks](../main/attachments/Screenshot-from-2023-04-10-00-08-20.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-10-00-10-01.png?raw=true "Optional Title")

#### 1.8.3.5. Kubernetes 101

![Stacks](../main/attachments/Screenshot-from-2023-04-10-00-13-40.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-10-00-18-23.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-10-00-22-04.png?raw=true "Optional Title")

#### 1.8.3.6. Elastic Kubernetes Service 101 (EKS)

![Stacks](../main/attachments/Screenshot-from-2023-04-10-00-28-48.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-10-00-30-11.png?raw=true "Optional Title")


## 1.9. Advanced EC2

### 1.9.1. Bootstrapping EC2 using User Data

Bootstrapping is a process where scripts or other config steps can be run when
an instance is first launched. This allows an instance to be brough to service
in a particular configured state.

In systems automation, bootstrapping allows the system to self configure
or perform some self configuration steps. In AWS this is
**EC2 Build Automation**.

This could perform some software installs and post install configs.

Bootstrapping is done using user data - accessed via the meta-deta IP

<http://169.254.169.254/latest/user-data>

Anything you pass in is executed by the instance OS. It is excecuted
only once on launch!

EC2 doesn't validate the user data. You can tell EC2 to pass in trash data
and the data will be passed. The OS needs to understand the user data.

#### 1.9.1.1. Bootstrapping Architecture

![Stacks](../main/attachments/Screenshot-from-2023-04-11-22-58-47.png?raw=true "Optional Title")

An AMI is used to launch an EC2 instance in the usual way to create
an EBS volume that is attached to the EC2 instance. This is based on the
block mapping inside the AMI.

Now the EC2 service provides some userdata through to the EC2 instance.
There is software within the OS running which is designed to look at the
metadata IP for any user data. If it sees any user data, it executes
this on launch of that instance.

This is treated like any other script the OS runs. At the end of running
the script, the instance will be in:

- Running state and ready for service
- Bad config but still likely running
  - The instance will probably still pass its checks
  - It will not be configured as you excpected

#### 1.9.1.2. User Data Key Points

EC2 doesn't know what the user data contains, it's just a block of data.

The user data is not secure, anyone can see what gets passed in. For this
reason it is important not to pass passwords or long term credentials.

User data is limited to 16 KB in size. Anything larger than this will
need to pass a script to download the larger set of data.

User data can be modified if you stop the instance, change the user
data, then restart the instance.

The contents are only excecuted once at launch.

#### 1.9.1.3. Boot-Time-To-Service-Time

![Stacks](../main/attachments/Screenshot-from-2023-04-11-23-02-42.png?raw=true "Optional Title")

How quickly after you launch an instance is it ready for service. This
includes the time for EC2 to configure the instance and any software
downloads that are needed for the user.

When looking at an AMI, this can be measured in minutes.

AMI baking will front load the time needed.

The optimal way is to use AMI baking

### 1.9.2. AWS::CloudFormation::Init

**cfn-init** is a helper script installed on EC2 OS.

This is a simple configuration management system.

Procedural (user Data) vs Desired State (cfn-init)

Packages, groups, users, sources, files, commands, services, and ownerships.

This is executed as any other command by passing into the instance with
the user-data.

This is provided with directives via Metadata and AWS::CloudFormation::Init on
a CFN resource

#### 1.9.2.1. cfn-init explained

![Stacks](../main/attachments/photo_5888707064455347918_w.jpg?raw=true "Optional Title")

Starts off with a **cloud formation template**
This has a logical resource within it which is to create an EC2 instance.

This has a specific section called `Metadata:`

This then passes in the information passed in as `UserData`

cfn-init gets variables passed into the userdata by cloud formation

It knows the desired state desired by the user and can work towards a
final stated configuration

This can monitor the userdata and change things as the EC2 data changes.

#### 1.9.2.2. CreationPolicy and Signals

![Stacks](../main/attachments/photo_5888707064455347919_w.jpg?raw=true "Optional Title")

The template has a specific part designated signals

A creation policy is added to a logical resource. It is provided a
timeout value. The resource itself will trigger a signal that cloud formation
can continue

### 1.9.3. EC2 Instance Roles

![Stacks](../main/attachments/photo_5888707064455347934_w.jpg?raw=true "Optional Title")

IAM roles are the best practice ways for services to be granted permissions.

Roles that an instance can assume to grant permissions for resources within.

Starts with an IAM role with a permissions policy.

EC2 instance role allows the EC2 service to assume that role.

The **instance profile** is the item that allows the permissions inside
the instance.

When IAM roles are assumed, you are provided temporary roles based on the
permission assigned to that role. These credentials are passed through
instance **meta-data**.

EC2 and the secure token service ensure the credentials never expire.

Key facts

- Credentials are inside meta-data
- iam/security-credentials/role-name
- automatically rotated - always valid
- the resources need to check the meta-data periodically
- should always use roles compared to storing long term credentials
- CLI tools use role credentials automatically

### 1.9.4. AWS System Manager Parameter Store

![Stacks](../main/attachments/photo_5888707064455347935_w.jpg?raw=true "Optional Title")

Passing secrets into an EC2 instance is bad practice because anyone
who has access to the meta-data has access to the secrets.

Parameter store allows for storage of **configuration** and **secrets**

- Strings
- StringList
- SecureString

You can store license codes, database strings, and full configs and passwords.

Parameter store allows for hierarchies and versioning.

It can store plaintext and ciphertext. This integrates with **kms** to
encrypt passwords.

Allows for public parameters such as the latest AMI parameter to be stored
and referenced for EC2 creating.

This is a public service so any services needs access to the public sphere or
to be an AWS service.

Applications, EC2 instances, lambda functions can all request access to
parameter store.

This is tied closely to IAM and could use long term credentials such
as access keys, or short term use of IAM roles.

Allows for simple or complex sets of parameters.

### 1.9.5. System and Application Logging on EC2

![Stacks](../main/attachments/Screenshot-from-2023-04-12-23-02-38.png?raw=true "Optional Title")

Cloudwatch monitors the outside metrics of an instance
Cloudwatch logs is for logging

Neither natively capture data inside an instance.

CloudWatch Agent is required for OS visible data. It sends this data into CW

For CW to function, it needs configuration and permissions in addition
to having to install the cloud watch agent.

The cloudwatch agent needs to know what information to inject
into cloud watch and cloud watch logs.

The agent needs some permissions to interact with AWS. This is done with an
IAM role as best practice. The IAM role has permissions to interact
with CW logs. The IAM role is attached to the instance which provides
the instance and anything running on the instance, permissions to manage
CW logs.

The data requested is then injected in CW logs.

There is one log group for each individual log we want to capture

There is one log stream for each group for each instance that needs
management.

We can use parameter store to store the configuration for the CW agent.

### 1.9.6. EC2 Placement Groups

#### 1.9.6.1. Cluster Placement Group - Pack instances close together

![Stacks](../main/attachments/photo_5890958864269032594_w.jpg?raw=true "Optional Title")

Achieves the highest level of performance available with EC2.

Best practice is to launch all of the instances within that group at the
same time.

If you launch with 9 instances and AWS places you in a place with capacity
for 12, you are now limited in how many you can add.

Cluser placements need to be part of the same AZ. The idea with cluster
placement groups are generally the same rack, but they can even be the same
EC2 host.

All members have direct connections to each other. They can achieve
10 Gbps single stream vs 5 Gbps normally. They also have the lowest
latency and max PPS possible in AWS.

If the hardware fails, the entire cluster will fail.

##### 1.9.6.1.1. Cluster Exams

Clusters can't span AZs. The first AZ used will lock down the cluster.

They can span VPC peers.

Requires a supported instance type.

Best practice to use the same type of instance and launch all at once.

This is the only way to achieve **10Gbps SINGLE stream**, other data metrics
assume multiple streams.

#### 1.9.6.2. Spread - Keep instances seperated

![Stacks](../main/attachments/photo_5890958864269032595_w.jpg?raw=true "Optional Title")

This provides the best resillience and availability.

Spread groups can span multiple AZs. Information will be put on distinct
racks with their own network or power supply. There is a limit of 7 instances
per AZ. The more AZs in a region, the more instances inside a spread placement
group.

##### 1.9.6.2.1. Spread Exams

Provides the highest level of availability and resillience. Each instance
by default runs from a different rack.

7 instances per AZ is a hard limit.

Not supported for dedicated instances or hosts.

Use case: small number of critical instances that need to be kept seperated
from each other. Several mirrors of an application

#### 1.9.6.3. Partition - groups of instances spread apart

![Stacks](../main/attachments/photo_5890958864269032595_w.jpg?raw=true "Optional Title")

Spread placement groups are handled by default natively by AWS.

If a problem occurs with one rack's networking or power, it will
at most take out one instance.

The main difference is you can launch as many instances in each partition
as you desire.

When you launch a partition group, you can allow AWS decide or you can
specifically decide.

##### 1.9.6.3.1. Parition Exams

7 paritions maximum for each AZ

Instances can be placed into a specific parition, or AWS can pick.

This is not supported on dedicated hosts.

Great for HDFS, HBase, and Cassandra

### 1.9.7. EC2 Dedicated Hosts

EC2 host allocated to you in its entirety.

Pay for the host itself which is designed for a family of instances.

No instance charges.

You can pay for a host on-demand or reservation with 1 or 3 year terms.

The host hardware has physical sockets and cores. This dictates to how
many instances can be run.

Hosts are designed for a specific size and family. If you purchase one host, you
configure what type of instances you want to run on it. With the older
system you cannot mix and match. The new nitro system allows for mixing and
matching host size.

![Stacks](../main/attachments/Screenshot-from-2023-04-13-20-46-43.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-13-20-48-33.png?raw=true "Optional Title")

#### 1.9.7.1. Dedicated Hosts Limitations

AMI Limits, some versions can't be used

Amazon RDS instances are not supported

Placement groups are not supported for dedicated hosts.

Hosts can be shared with other organization accounts using **RAM**

This is mostly used for licensing problems related to ports.

### 1.9.8. Enchanced Networking

Enchanced networking uses SR-IOV - The physical network interface is aware
of the virtualization. Each instance is given exclusive access to one part
of a physical network interface card.

There is no charge for this and is available on most EC2 types.

It allows for higher IO and lower host CPU usage

This provides more bandwidth and higher packet per seconds.

In general this provides lower latency.

#### 1.9.8.1. EBS Optimized

Historically network was shared, data and EBS.

EBS optimized there has been dedicated capacity for EBS. Most instances support
andh ave this enabled by default.

Some support, but enabling costs extra. This is generally enabled and comes
with standard instances.

## 1.10. Route 53

### 1.10.1. Public Hosted Zones

![Stacks](../main/attachments/Screenshot-from-2023-04-14-20-29-52.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-14-20-31-39.png?raw=true "Optional Title")

A DNS database for a specific domain.

Public = hosted on R53 provided **public DNS servers**

AWS provides at least 4 hosted name servers

This is globally resilient (Multiple DNS servers)

This is created with domain registration via R53, can be created seperately.

There is a monthly fee for non R53 hosted zones.

Host DNS records.

Hosted Zones are what the DNS system refererences, it becomes Authoritative
for a domain and visible to the public internet.

![Stacks](../main/attachments/Screenshot-from-2023-04-14-20-34-08.png?raw=true "Optional Title")

### 1.10.2. R53 Private Hosted Zones

![Stacks](../main/attachments/Screenshot-from-2023-04-14-20-46-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-14-20-48-48.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-14-20-51-51.png?raw=true "Optional Title")

### 1.10.3. CNAME vs R53 Alias

![Stacks](../main/attachments/Screenshot-from-2023-04-14-20-59-05.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-14-21-01-52.png?raw=true "Optional Title")

### 1.10.4. Simple routing

- Simple : Route traffic to a single resource. Client queries the resolver
which has one record. It will respond with 3 values and these get forwarded
back to the client. The client then picks one of the three at random.
This is a single record only. No health checks.

![Stacks](../main/attachments/Screenshot-from-2023-04-15-00-03-13.png?raw=true "Optional Title")

### 1.10.5. Route 53 Health Checks

Route checks will allow for periodic health checks on the servers.
If one of the servers has a bug, this will be removed from the list.

If the bug gets fixed, the health check will pass and the server will be
added back into a healthy state.

These are seperate from, but used by records on Route 53.

These are performed by a fleet of global health checkers. If you think
they are bots and block them, this could cause alarms.

Checks occur every 30 seconds by default. This can be increased to 10 seconds
for additional costs. These checks are per health checker. Since there are many
you will automatically get one every few seconds. The 10 second option will
complete multiple checks per second.

There could be one of three checks

- TCP checks: R53 tries to establish TCP with end point within 10 seconds
- HTTP/HTTPS: Same as TCP but within 4 seconds. The end point must respond
with a 200 or 300 status code within 3 seconds of checking.
- String matching: Same as above, the body must have a string within the first
5120 bytes. This is chosen by the user.

It will be deemed healthy or unhealthy.

There are three types of checks.

- Endpoint checks
- Cloudwatch alarms
- Checks of checks

![Stacks](../main/attachments/Screenshot-from-2023-04-15-00-21-04.png?raw=true "Optional Title")

### 1.10.6. Failover Routing

- Failover : Create two records of the same name and the same type. One
is set to be the primary and the other is the secondary. This is the same
as the simple policy except for the response. Route 53 knows the health of
both instances. As long as the primary is healthy, it will respond with
this one. If the health check with the primary fails, the backup will be
returned instead. This is set to impliment active - passive failover.

![Stacks](../main/attachments/Screenshot-from-2023-04-15-00-33-59.png?raw=true "Optional Title")

### 1.10.7. Multi Value Routing

- Multi-value : One record with one name and multiple values in this record.
These will be health checked and the unhealthy responses will automatically
be removed.

![Stacks](../main/attachments/Screenshot-from-2023-04-15-20-48-00.png?raw=true "Optional Title")

### 1.10.8. Weighted Routing

- Weighted : Create multiple records of the same name within the hosted zone.
For each of those records, you provide a weighted value. The total weight
is the same as the weight of all the records of the same name. If all of the
parts of the same name are healthy, it will distribute the load based
on the weight. If one of them fails its health check, it will be skipped over
and over again until a good one gets hit. This can be used for migration
to seperate servers.

![Stacks](../main/attachments/Screenshot-from-2023-04-15-20-59-13.png?raw=true "Optional Title")

### 1.10.9. Latency Routing

- Latency-based : Multiple records in a hosted zone can be created with
the same name and same type. When a client request arrives, it knows which
region the request comes from. It knows the lowest latency and will respond
with the lowest latency.

![Stacks](../main/attachments/Screenshot-from-2023-04-15-21-11-00.png?raw=true "Optional Title")

### 1.10.10. Geolocation Routing

- Geolocation : Focused to delivering results matching the query of your
customers. The record will first be matched based on the country if possible.
If this does not happen, the record will be checked based on the continent.
Finally, if nothing matches again it will respond with the default response.
This can be used for licensing rights. If overlapping regions,
the priority will always go to the most specific or smallest region. The US
will be chosen over the North America record.

![Stacks](../main/attachments/Screenshot-from-2023-04-15-22-41-26.png?raw=true "Optional Title")

### 1.10.11. Geoproximity

![Stacks](../main/attachments/Screenshot-from-2023-04-15-22-50-35.png?raw=true "Optional Title")

### 1.10.12. R53 Interoperability

![Stacks](../main/attachments/Screenshot-from-2023-04-15-22-57-29.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-15-23-00-44.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-15-23-02-16.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-15-23-46-44.png?raw=true "Optional Title")


### 1.10.13. DNSSEC using Route53

![Stacks](../main/attachments/Screenshot-from-2023-04-15-23-54-04.png?raw=true "Optional Title")


## 1.11. RDS

### 1.11.1. Database Refresher

Systems to store and manage data.

#### 1.11.1.1. Relational (SQL)

Structured Query Language (SQL) is a feature of most relational database servers
Structure in and between tables of data. There is a rigid **schema**. This is
defined in advance.

There is a fixed relationship between tables. This is defined before data
is entered into the database.

Every row in a table must have a value for the **primary key**

There will be multiple tables, but each one needs a primary key. For every
table, there must be a value stored for every attribute in the table.

There is a join table with a **composite key**. The key must be unique in its
entirety.

Table relationships use keys

The Table Scehmas and relationships must be defined in advance.

![Stacks](../main/attachments/Screenshot-from-2023-04-16-21-01-16.png?raw=true "Optional Title")

#### 1.11.1.2. Non-Relational (NoSQL)

Not a single thing, and is a catch all for everything else. There is generally
a weak or no schema.

![Stacks](../main/attachments/Screenshot-from-2023-04-16-21-01-16.png?raw=true "Optional Title")

##### 1.11.1.2.1. Key-Value databases

The key stores the time and the Value shows the data that wants to be recorded.
So long as every key is unique, there is no real schema or structure.

These are really fast and highly scalable.

This is also used for **in memory caching**

![Stacks](../main/attachments/Screenshot-from-2023-04-17-20-38-56.png?raw=true "Optional Title")

##### 1.11.1.2.2. Wide Column Store

DynamoDB is one type of database.

Parition key - The search key  
Other Key - sort or range key

Each needs to have one key or more keys.

Every item in a table can also have attributes, but they don't have to be
the same between values. The only requirements is the key needs to be unique.

It can be **single key** or **composite key**. Either case, it must be unique.

![Stacks](../main/attachments/Screenshot-from-2023-04-17-20-42-46.png?raw=true "Optional Title")

##### 1.11.1.2.3. Document

Documents are generally formated using JSON or XML.

This is an extension of a key-value store.

Good for orders or contacts. This is good for whole documents or deep attribute
interations.

![Stacks](../main/attachments/Screenshot-from-2023-04-17-20-44-45.png?raw=true "Optional Title")

##### 1.11.1.2.4. Column

Row Store (MySQL) - If you needed to read the price of one item you need that
row first. If you wanted to query all of the sizes of every order, you will
need to check for each row. Often called Online Transactional Processing (OLTP).

Column Store (Redshift) - Columns are stored together. Bad for sales style
but good for reporting or when all values for a specific size are required.

![Stacks](../main/attachments/Screenshot-from-2023-04-17-20-48-12.png?raw=true "Optional Title")

##### 1.11.1.2.5. Graph

Relationships between things are formally defined and stored along in the
database itself with the data. These are great for relationship driven data.

Nodes are objects inside a graph database. They can have properties.

Edges are relationships between the nodes. They have a direction.

Relationships can also have values associated with them and they are also
stored inside the database.

Relationships are fast because interactions can be queried.

![Stacks](../main/attachments/Screenshot-from-2023-04-17-20-50-42.png?raw=true "Optional Title")

##### 1.11.1.2.6. Acid vs Base

![Stacks](../main/attachments/Screenshot-from-2023-04-18-13-31-45.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-18-14-00-30.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-18-14-03-59.png?raw=true "Optional Title")

### 1.11.2. Databases on EC2

It is always a bad idea to do this. Splitting an instance over different
AZs adds a small cost to moving the data between AZs if it happens.

#### 1.11.2.1. Reasons EC2 Database might make sense

You might need access to the OS of the Database. You should question
if a client requests this, it rarely is needed.

Advanced DB Option tuning (DBROOT) AWS provides options against this.

This is typically a vendor that demands this.

DB or DB version that AWS doesn't provide.

You might need a specific version of an OS and DB that AWS doesn't provide.

#### 1.11.2.2. Reasons why you really shouldn't run a database on EC2

**Admin overhead** is intense to manage EC2 and DBHost compatible

Backup and Disaster Management adds complexity.

EC2 is running in a single AZ. If the zone fails, access to the database fails.

Will miss out on features from AWS DB products.

EC2 is ON or OFF, there is no way to scale easily.

**Replication** the skills and setup time to monitor this

Performance will be slower than AWS options.

### 1.11.3. Relational Database Service (RDS)

Database-as-a-service (DBaaS) - not entirely true more of
DatabaseServer-as-a-service. Managed Database Instance for one or more databases

Multiple engines are MySQL, MariaDB, PostgreSQL, Oracle, Microsoft SQL

Amazon Aurora. This is so different from normal RDS, it is a seperate product.

#### 1.11.3.1. RDS Database Instance

Runs one of a few types of database engines and can contain multiple
user created databases. Create one when you provision the instance, but
multiple can be created after.

Database connects with a CNAME. RDS uses standard database engines.

The database can be optimized for:

- db.m5 general
- db.r5 memory
- db.t3 burst

There is an associated size and AZ selected.

When you provision an instance, you provision storage that is dedicated
to that instance. This is EBS storage located in the same AZ. RDS is vulnerable
to failures in that AZ.

The storage can be allocated with SSD or magnetic.

io1 - high IO  
gp2 - same burst pool  
magnetic - compatibility

Billing is per instance and hourly rate for that compute. You are billed
for storage allocated.

![Stacks](../main/attachments/Screenshot-from-2023-04-18-21-21-32.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-18-21-23-56.png?raw=true "Optional Title")

### 1.11.4. RDS Multi AZ (High-Availability)

RDS Access ONLY via database CNAME. The CNAME will point at the primary
instance. You cannot access the standby replica for any reason via RDS.

The standby replica cannot be used for extra capacity.

**Syncronous Replication** is a keyword:

1. Database writes happen
2. Primary database instance commits changes
3. Same time as the write is happening, standby replication is happening
4. Standby replica commits writes.

If any error occurs with the primary database, AWS detects this and will
failover within 60 to 120 seconds to change to the new database.

This does not provide fault tolerance - there will be some impact during change

Exam Powerups

- Multi-AZ feature is not free tier, extra infrastructure for standby. Generally
two times the price.
- The standby replica cannot be accesed directly unless a fail occurs.
- Faillover is highly available, not fault tolerant.
- Same region only (others AZ in the VPC).
- Backups taken from standby (removes performance impacts).
- AZ outage, primary failure, manual failover, instance type change, and
software patching

![Stacks](../main/attachments/Screenshot-from-2023-04-20-20-46-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-20-20-56-58.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-20-21-00-48.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-20-21-03-36.png?raw=true "Optional Title")

### 1.11.5. RDS Backup and Restores

RPO - Recovery Point Objective

- Time between the last backup and when the failure occured
- Amount of maximum data loss
- Influences technical solution and cost
- Buisness usually provides an RPO value

RTO - Recovery Time Objective

- Time between the DR event and full recovery
- Influenced by process, staff, tech and documentation

**RDS Backups**

First snap is FULL size of consumed data. If you are you using single AZ

Manual snapshots will remain in your AWS account even after the life of
the snapshot. These need to be deleted manually.

**Automatic Snapshots**

Every 5 minutes translation logs are saved to S3. A database can then be
restored to a 5 min snapshot in time.

Automatic cleanups can be anywhere from 0 to 35 days. This will use
both the snapshots and the translation logs.

When you delete the database, they can be retained but they will expire
based on their retention period.

![Stacks](../main/attachments/Screenshot-from-2023-04-20-21-17-28.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-21-20-56-49.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-21-20-59-17.png?raw=true "Optional Title")

#### 1.11.5.1. RDS Exam Powerups

When performing a restore, RDS creates a new RDS with a new endpoint address.

When restoring a manual snapshot, you are setting it to a single point
in time. This influences the RPO value.

Automated backups are different, any 5 minute point in time.

Backups are restored and transaction logs are replayed to bring DB to
desired point in time.

Restores aren't fast, think about RTO.

### 1.11.6. RDS Read-Replicas

![Stacks](../main/attachments/Screenshot-from-2023-04-21-20-54-57.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-20-21-18-33.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-20-21-20-06.png?raw=true "Optional Title")

Kept in sync using **asyncronous replication**

It is written fully to the primary instance. Once its stored on disk, it
is then pushed to the replica. This means there could be a small lag.
These can be created in the same region or a different region. This is a
**cross region replication**

#### 1.11.6.1. Why do these matter

READ performance

- 5 direct read-replicas per DB instance
- Each of these provides an additional instance of read performance
- This allows you to scale out read operations for an instance
- Read-replicas can chain, but lag will become a problem
- Can provide global performance improvements

Availability Improvements

- Snapshots and backups improve RPO
- These don't help RTOs
- These offer near 0 RPO
- If the primary instance fails, you can promote a read-replica to take over
- Once it is promoted, it allows for read and write
- Only works for failures, these can replicate data corruption, default back
to snapshots and backups
- Promotion cannot be reversed
- Global availability improvements provides global resilience

### 1.11.7. RDS Data Security

![Stacks](../main/attachments/Screenshot-from-2023-04-22-12-24-45.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-12-26-04.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-12-28-01.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-12-30-51.png?raw=true "Optional Title")

### 1.11.8. RDS Custom

![Stacks](../main/attachments/Screenshot-from-2023-04-22-13-09-28.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-13-11-34.png?raw=true "Optional Title")

### 1.11.9. Amazon Aurora

Aurora architecture is VERY different from RDS. At it's heart it uses a
**cluster**

- A single primary instance and 0 or more replicas
- The replicas within Aurora can be used for reads during normal operation
  - Provides benefits of RDS multi-AZ and read-replicas
- Aurora doesn't use local storage for the compute instances. An Aurora
cluster has a shared cluster volume. Provides faster provisioning.

Aurora cluster functions across different availability zones.

There is a primary instance and a number of replicas. The read applications from
applications can use the replicas.

There is a shared storage of **max 64 TiB, 6 Replicas, AZs**

All instances have access to all of these storage nodes. This replication
happens at the storage level. No extra resources are consumed during
replication.

By default the primary instance is the only one who can write. The replicas
will have read access.

Aurora automatically detect hardware failures on the shared storage. If there
is a failure, it immedietly repairs that area of disk. It automatically
recreates that data with no corruption.

With Aurora you can have up to 15 replicas and any of them
can be a failover target. The failover operation will be quicker because
it doesn't have to make any storage modifications. 

Cluster shared volume is based on SSD storage by default so high IOPS and low
latency.

Aurora cluster does not specify the amount of storage needed. This is based on
what is consumed.

High water mark - billed for the most used. Storage which is freed up can
be re-used.

Replicas can be added and removed without requiring storage provisioning.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-13-29-56.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-13-36-47.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-13-39-04.png?raw=true "Optional Title")

#### 1.11.9.1. Endpoints

Cluster endpoint - points at the primary instance

Reader endpoint - will load balance over the available replicas

As additional replicas are used for reads, this is load balanced over
replicas.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-13-40-27.png?raw=true "Optional Title")

#### 1.11.9.2. Costs

- No free-tier option
- Aurora doesn't support micro instances
- Beyond RDS singleAZ (micro) Aurora provides best value.
- Storage - GB-Month consumed, IO cost per request
- 100% DB size in backups are included

![Stacks](../main/attachments/Screenshot-from-2023-04-22-13-42-09.png?raw=true "Optional Title")

#### 1.11.9.3. Aurora Restore, Clone and Backtrack

Backups in Aurora work in the same way as RDS

Restores create a new cluster.

Backtrack allows for you to roll back to a previous point in time. You can roll
back in place to a point before that corruption.

Enabled on a per cluster basis and can adjust the window backtrack can perform.

Fast clones make a new database much faster than copying all the data. It
references the original storage and only write the differences between
those two. It only copies the difference and only store changes
between the source data and the clone.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-14-02-24.png?raw=true "Optional Title")


### 1.11.10. Aurora Serverless

Provides a version of Aurora without worrying about the resources. 
It uses ACU - Aurora Capacity Units

For a cluster, you can set a min and max ACU based on the load

Can go to 0 and be paused.

Consumption billing per-second basis

Same resilience as Aurora (6 copies across AZs)

ACUs are stateless and shared across many AWS customers and have no local
storage.

They have access to cluster storage in the same way.

There is a shared proxy fleet. When a customer interacts with the data
they are actually communicating with the proxy fleet. The proxy fleet
brokers an application with the ACU and ensures you can scale in and out
without worrying about usage.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-21-21-31.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-21-25-33.png?raw=true "Optional Title")

#### 1.11.10.1. Aurora Serverless - Use Cases

Infrequently used applications. You only pay for resources as you consume
them on a per second basis.

New applications

Great for variable workloads. It can scale in and out based on demand

It is good for applications with unpredictable workloads.

It can be used for development and test databases because it can scale back
when not needed.

Great for multi-tenant applications. If your incoming load is directly
tied to more people, that's fine.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-21-30-10.png?raw=true "Optional Title")

### 1.11.11. Aurora Global Database

Replication from primary cluster volume to secondary replicas for read
operations.

Great for cross region disaster recovery and buisness continuity.

Global read scaling - low latency performance improvements for international
customers.

The application can perform read operations against the read database.

There is ~1s or less replication between regions. It is one way replication.

No additional CPU usage is needed, it happens on the storage layer.

Secondary regions can have 16 replicas.

All can be promoted to Read or Write with diasters.

There is currently max of 5 secondary regions.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-21-42-42.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-21-45-31.png?raw=true "Optional Title")

### 1.11.12.  Aurora Multi-Master Writes

Allows an aurora cluster to have multiple instances with multiple writers.

The default aurora mode is single-master.

- This is one R/W and zero or more read only replicas.
- Cluster endpoint is normally used to write, read endpoint is used for load
balancing.

Aurora Multi-master has no endpoint or load balancing. An application
can connect with one or both of the instances inside a multi-master
cluster.

When one of the R/W nodes, it proposes all data be commited to all storage
of the clusters. They each confirm or deny if this change is allowed.

The writing instance is looking for a bunch of nodes to agree. If the group
rejects it, it cancels the write in error. If it commits, it will replicate
on all storage nodes.

In a Multi-master cluster, it will then copy into other masters.

This ensures storage is updated on in-memory cache's

If a writer goes down in a multi-master cluster, the application will shift
all future load over to the new writter with little to no downtime.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-10-39.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-13-26.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-16-45.png?raw=true "Optional Title")

### 1.11.13. RDS Proxy

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-29-10.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-32-28.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-34-29.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-36-35.png?raw=true "Optional Title")

### 1.11.14. Database Migration Service (DMS)

A managed database migration service. This runs using a replication instance.

Need to define the source and destination endpoints. These point at the
physical source and target databases.

One endpoint MUST be on AWS.

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-55-10.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-22-58-54.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-23-02-24.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-22-23-04-15.png?raw=true "Optional Title")


## 1.12. Network Storage

### 1.12.1. EFS Architecture

EFS moves the instances closer to a stateless.

EFS is an implementation of NFSv4

EFS Filesystems can be mounted in Linux.

Using Amazon EFS with Microsoft Windows–based Amazon EC2 instances is not supported.

Media can be shared between many EC2 instances.

This is a private service, access is via mount targets inside a VPC.

You can access from on-premises with VPN or DX so long as access is configured.

#### 1.12.1.1. Elastic File System Explained

EFS runs inside a VPC.
EFS includes POSIX permissions. These are made available via mount targets.

For a fully highly available system you need a mount target for each AZ the
system runs in.

You can use hybrid networking to connect to the same mount targets.

#### 1.12.1.2. EFS Exam Powerup

EFS is Linux Only

Two performance modes, general purpose and max I/O performance mode.

General purpose = default for 99.9% of uses

Bursting and provisioned throughput modes.

Two storage classes available, standard and infrequent access.

Lifecycle policies can move data between EFS

### 1.12.1. AWS Backup

![Stacks](../main/attachments/Screenshot-from-2023-04-29-22-50-43.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-29-23-16-42.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-29-23-34-44.png?raw=true "Optional Title")

## 1.13. HA and Scaling

### 1.13.1. Regional and Global AWS Architecture

![Stacks](../main/attachments/Screenshot-from-2023-04-30-11-56-35.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-11-59-16.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-12-07-30.png?raw=true "Optional Title")

### 1.13.2. Load Balancing Fundamentals

Without load balancing, it is difficult to scale.

The user connects to a load balancer that is set to listens on port 80 and 443

Within AWS, the ports the load balancer will listen to is called
the **listener**.

The user is connected to the load balancer and not the actual server.

Behind the load balancer, there is an application server. At a high
level when Bob connects to the load balancer, it distributes that to
servers on the application server.

As long as 1+ servers are available, the LB is operational. Clients
shouldn't see errors.

#### 1.13.2.1. ELB Architecture

![Stacks](../main/attachments/Screenshot-from-2023-04-30-12-19-09.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-16-31-33.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-17-11-06.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-17-58-44.png?raw=true "Optional Title")

#### 1.13.2.2. LB Exam Powerup

Clients connect to the **listener** of the load balancer

The load balancer connects to one or more **targets** or servers

Listener connection - one connection between the client and listener
Backend connection - one connection between load balancer and backend instance

Client is abstracted away from individual servers

Used for high availability, fault tolerance, and scaling

### 1.13.3.Application Load balancing (ALB) vs Network Load Balancing (NLB)

![Stacks](../main/attachments/Screenshot-from-2023-04-30-21-05-40.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-21-09-54.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-21-17-24.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-21-20-45.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-21-24-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-04-30-21-25-38.png?raw=true "Optional Title")

#### 1.13.3.1. Cross zone load balancing

Each node that is part of the load balancer is able to distribute load
even if its not in the same AZ. It is the reason we can achieve a balanced
distribution of connections behind a load balancer.

It can also provide health checks on the target servers.

If all instances are shown as healthy, it can distribute evenly.

ALB can support a wide array of targets. An individual target can be a
member of multiple groups.

![Stacks](../main/attachments/Screenshot-from-2023-04-30-17-21-28.png?raw=true "Optional Title")

#### 1.13.3.2. ALB Exam Powerup

**Targets** are lambda functions or EC2 instances that are directed towards.

Rules are path based or host based.

Support EC2, EKS, Lambda, HTTPS, HTTP/2 and websockets

ALB can use SNI for multiple SSL certs - host based rules

AWS does not suggest using Classic Load Balancer (CLB), these are legacy.

### 1.13.4. Launch Configuration and Templates

LC and LT key concepts. They are documents which allow you to config an EC2
instance in advance. You can configure userdata and IAM role along with
networking and security groups.

Launch templates
- Provide T2/T3 Unlimited, placement groups with more.  
- Newer and recommended to use over launch configurations, they include the latest features and improvements.
- Supports versioning of templates.
- Can be used to save time when provisioning EC2 instances from the console UI / CLI.

If you need to adjust a configuration, you must make a new one and launch it.

![Stacks](../main/attachments/Screenshot-from-2023-05-02-10-25-11.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-10-26-18.png?raw=true "Optional Title")

### 1.13.5. Auto Scaling Groups

Automatic scaling and self-healing for EC2

They make use of Launch Templates to know what to provision.

They use one version or one configuration they're assigned with.

Minimum, Desired, and Maximum Size.

Provision or Terminate instances to keep at the desired level

Scaling Policies automate based on metrics or a schedule

Auto Scaling Groups will try to keep the AZs equal with the number of EC2
instances.

![Stacks](../main/attachments/Screenshot-from-2023-05-02-11-42-45.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-11-44-16.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-11-45-11.png?raw=true "Optional Title")

#### 1.13.5.1. Scaling Policies

Manual Scaling - manually adjust the desired capacity

Scheduled Scaling - time based adjustments

Dynamic Scaling

- Simple : If CPU is above 50%, add one to capacity
- Stepped : If CPU usage is above 50%, add one, if above 80% add three
- Target : Desired aggregate CPU = 40%, ASG will achieve this

Cooldown Period - How long to wait at the end of a scaling action before scaling again.

Always use cool downs to avoid rapid scaling.

AGS can use the load balancer health checks rather than EC2.

Autoscaling Groups are free  

Think about more, smaller instances to allow granularity

You should use ALB with autoscaling groups.

ASG defines when and where, Launch Template defines what.

![Stacks](../main/attachments/Screenshot-from-2023-05-02-11-53-33.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-13-50-49.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-13-52-37.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-14-10-45.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-14-52-29.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-15-04-56.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-15-08-27.png?raw=true "Optional Title")


#### 1.13.5.2.  ASG Scaling Hooks

![Stacks](../main/attachments/Screenshot-from-2023-05-02-21-59-31.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-02-22-05-55.png?raw=true "Optional Title")

### 1.13.6. ASG HealthCheck Comparison - EC2 vs ELB

![Stacks](../main/attachments/Screenshot-from-2023-05-03-21-23-48.png?raw=true "Optional Title")

### 1.13.7. SSL Offload and Session Stickiness

#### 1.13.7.1. Bridging - Default mode

One or more clients makes one or more connections to a load balancer.
The load balancer is configured so the **listener** uses HTTPS, SSL connections
occur between the client and the load balancer.

The load balancer then needs an SSL certificate that matches the domain name
of the application.

If you need to be careful of where your certificates are stored, you may
have a problem with this system.

ELB initiates a new SSL connection to backend instances with a removed
HTTPS certificate. This can take actions based on the content of the HTTP.

It needs to decrypt any data that is being encrypted by the client.

The EC2 will need matching SSL certificates.

Needs the compute for the cryptographic operations. Every EC2 instance must
peform these cryptographic operations.

#### 1.13.7.2. Pass-through

The client connects, but the load balancer passes the connection along without
decrypting the data at all. The instances still need the SSL certificates,
but the load balancer does not.

The load balancer is configured for TCP, it can see the source or destinations,
but it never touches the encrypted connection. The certificate never
needs to be seen by AWS.

Negative is you don't get any load balancing based on the HTTP part
because that is never exposed to the load balancer.

#### 1.13.7.3. Offload

Clients connect to the load balancer using HTTPS and are terminated on the
load balancer. The LB needs an SSL certificate to decrypt the data, but
on the backend the data is sent via HTTP. While there is a certificate
required on the load balancer, this is not needed on the LB.

Data is in plaintext form across AWS's network. Not a problem for most.

#### 1.13.7.4. Connection Stickiness

If there is no stickiness, each time the customer logs on they will have
a stateless experience. If the state is stored on a particular server,
sessions can't be load balanced across multiple servers.

Session Stickiness is an option. If enabled, the first time a user makes a
request, the load balancer generates a cookie called AWSALB. A valid duration
is between one second and seven days. For this time, sessions will be sent to
the same backend instance. This will happen until:

- If we have a server failure, then the user will be moved to a different
server.
- The cookie could expire, the whole process will repeat and will recieve a
new cookie and the process will start again.

This could cause backend unevenness

![Stacks](../main/attachments/Screenshot-from-2023-05-03-22-00-11.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-03-22-10-22.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-03-22-46-28.png?raw=true "Optional Title")


### 1.13.8. Gateway Load Balancer

![Stacks](../main/attachments/Screenshot-from-2023-05-06-22-35-54.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-06-22-55-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-06-23-15-53.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-06-23-24-36.png?raw=true "Optional Title")

## 1.14. Serverless and Application services

### 1.14.1. Architecture Deep Dive

Youtube

Once a video is uploaded to Youtube, it creates different versions in
different quality levels. Historically the most popular way to make this work
was a monolithic architecture.

#### 1.14.1.1. Monolithic

- It fails together. One error will bring the whole system down.
- Scales together. Everything expects to be running on the same compute hardware
- Bill together. All components are always running and always incurring charges.

This is the least cost effective way to architect systems.

![Stacks](../main/attachments/Screenshot-from-2023-05-07-14-49-40.png?raw=true "Optional Title")

#### 1.14.1.2. Tiered

The different components can be on the same server or different servers.

The components are coupled together because the endpoints connect together.

You can increase the size of the server that is running each application tier.

We can utilize load balancers in between tiers to add capacity.

The tiers are still coupled, the upload tier **expects** and requires
processing to respond. If the Processing fails completely, the upload tier
will fail because it does not recieve a response.

If there is a backload in one tier, it will impact the other tiers and the
customer experience.

Even if there is no job to be processed, the middle tier will need to be
running because otherwise it would fail.

![Stacks](../main/attachments/Screenshot-from-2023-05-07-14-55-05.png?raw=true "Optional Title")

#### 1.14.1.3. Evolving with Queues

This is a system that accepts messages off a queue. Often times
they are **FIFO** (first in, first out)

Instead of passing data into the processing tier. It will store this in an S3
bucket as well as detailing the information into the queue. This now
moves towards the next slot in the queue.

The upload tier doesn't expect an immediate answer from the processing tier.

It sends an asycn message. While this is happening, the upload can add more
messages to the queue.

The queue will have an autoscaling group to increase capacity at the end and
process appropriately.

The queue has the location of the S3 bucket as well as the location
of the information.

The autoscaling group will only bring up servers as their needed.

![Stacks](../main/attachments/Screenshot-from-2023-05-07-16-15-02.png?raw=true "Optional Title")

#### 1.14.1.4. Event Driven Architecture

Event producers - interact with customers or systems monitoring components.
They produce events in reaction to something.

Event consumers - pieces of software waiting for events to occur.

Services can be producers and consumers at once.

In either case, there are no resources waiting around to be used.

Event router is needed for event driven architecture that also manages
an event bus.

![Stacks](../main/attachments/Screenshot-from-2023-05-07-16-29-47.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-16-32-04.png?raw=true "Optional Title")

#### 1.14.1.5. Highlights

- No constant running or waiting for things
- Producer generate events when something happens
- Clicks, events, errors, actions
- Events are delivered to consumers of events
- Actions are taken and the system returns to waiting

Mature event driven architecture only consumes resources while handling
events.

#### 1.14.1.6. Microservices

![Stacks](../main/attachments/Screenshot-from-2023-05-07-16-17-14.png?raw=true "Optional Title")

### 1.14.2. AWS Lambda

- Function-as-a-service (FaaS)
- Event driven invocation (execution)
- **Lambda function** piece of code in one language
- Lambda functions use a **runtime** (e.g. Python 3.6)
- Runs in a **runtime environment**
- You are billed only for the duration a function runs. There is no charge
for having lambda functions waiting and ready to go.

![Stacks](../main/attachments/Screenshot-from-2023-05-07-21-11-12.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-22-57-51.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-21-20-21.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-22-04-46.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-22-09-35.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-22-10-55.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-22-14-24.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-07-22-16-11.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-08-21-35-55.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-08-22-29-36.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-08-22-36-33.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-08-22-48-22.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-08-22-53-55.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-08-23-00-19.png?raw=true "Optional Title")

#### 1.14.2.1. Lambda Architecture

Best practice is to make it very small and very specialized.
The runtime enviroment will match the language the script is written in.
The runtime enviroment is lime a mini container provided with resources.

Lambda functions can be given an IAM role, **execution role**. Whenever that
function executes, the code inside has access to permissions.

This can be **event-driven** or **manual** invocation many ways.

Each time you invoke a lambda function, the enviroment is new and clean

These are by default public services and can access any websites. By default
they cannot access private VPC resources.

Once they are configured, they can only access resources within a VPC.

Should always use AWS services for input and output.

Lambda functions can run up to 15 minutes. That is the max limit.

#### 1.14.2.2. Key Considerations

- Currently 15 min execution limit
- Assume each execution gets a new runtime environment
- Use the execution role which is assumed when needed
- Always load data from other services from public API's or S3
- Store data to other services (e.g. S3)
- 1M free requests and 400,000 GB-seconds of compute per month

### 1.14.3. CloudWatch Events and EventBridge

Delivers near real time stream of system events that describe changes in AWS
products and services. EventsBridge will replace CW Events.

EventsBridge can also handle events from third parties. Both share the same
underlying architecture. AWS is now encouraging a migration to EB.

#### 1.14.3.1. Key Concepts

They can observe if X happens at Y time(s), do Z. This is basically
CW Events V2.

Both systems have a default Event bus for a particular AWS account.

In CW Events, there is only one bus (implicit), this is not exposed.
EventBridge can have additional event buses. These can be interacted with
in the same way as the default bus.

Rules match incoming events or schedules. The rule matches an event and routes
that event to one or more targets as you define on that rule.

Architecturally at the heart of event bridge is the default event bus.

The default event bus is moving packets of JSON data.

![Stacks](../main/attachments/Screenshot-from-2023-05-08-23-44-32.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-08-23-46-47.png?raw=true "Optional Title")

### 1.14.4. Serverless

This is not one single thing, you manage few if any servers.
Applications are a collection of small and specialized functions.

These functions are stateless and run in ephemeral environments.
Each time they run, they obtain the data they need each time.

Generally, everything is event driven. While not being used, there should
be little to no cost due to compute not being used.

Should use managed services when possible.

![Stacks](../main/attachments/Screenshot-from-2023-05-09-21-25-42.png?raw=true "Optional Title")

#### 1.14.4.1. Example of Serverless

She browses to a static website that is running the uploader. The JS runs
directly from the web browser.

We use a third party auth provider, google in this case. Authenticate via
**token**.

AWS cannot use tokens provided by third parties. In this case another
service **Cognito** is called. This swaps the third party token for AWS
credentials.

It uses these temporary credentials to upload a video to S3 bucket.

The bucket will generate an event once it has completed the upload.

The event will trigger a lambda to transcode the video as needed. The
transcoder will get the original S3 bucket video location and will use
this for its workload.

These will be added to a new transcode bucket and will put an entry into
DynamoDB.

The user can then interact with another Lambda which will allow her to
pull the media from the transcode bucket using the dynamoDB entry.

![Stacks](../main/attachments/Screenshot-from-2023-05-09-21-37-24.png?raw=true "Optional Title")

### 1.14.5. Simple Notification Service (SNS)

HA, Durable, and Secure service.

This is a public service which needs access to the public endpoint. This
allows anyone from the public internet to access it.

Messages are under 256KB in size.

SNS topics are the base entity of SNS.

A publisher sends messages to a topic. Topics have subscribers which recieve
messages.

You can create topics inside the SNS.

By default all topics will recieve the message, you can put filters on
those lines to make sure they don't trigger additional lambdas.

You can use fanout to process different flows from SQS

Offers:

- Delivery Status including HTTP, Lambda, SQS
- Delivery retries - Reliable Delivery
- HA and Scalable (Regional)
- SSE (server side encryption)
- Topics can be used cross-account via Topic Policy

![Stacks](../main/attachments/Screenshot-from-2023-05-09-22-28-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-09-22-30-34.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-09-22-32-54.png?raw=true "Optional Title")

### 1.14.6. AWS Step Functions

There are many problems with lambdas limitations that can be solved with
a state machine.

This is a serverless workflow

- Start
- States
- End

States are **things** which occur

Maximum duration is 1 year

Standard workflow and express. At a high level, standard is the default
and has a 1 year workflow. Express is for IOT and highly transactional
such as IoT.

Started via API Gateway, IOT Rules, EventBridge, Lambda.

Amazon States Languate (ASL) - JSON template

These use IAM Roles for permissions.

![Stacks](../main/attachments/Screenshot-from-2023-05-10-22-38-48.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-10-22-42-44.png?raw=true "Optional Title")

#### 1.14.6.1. States

- Succeed & Fail : Will wait until either is achieved
- Wait : will wait until specific date and time or period of time
- Choice : different path is determined based on an input
- Parallel : will create parallel branches based on a choice
- Map : accepts a list of things
- Task : Single unit of work (lambda, batch, dynamoDB)

![Stacks](../main/attachments/Screenshot-from-2023-05-10-22-51-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-10-22-57-24.png?raw=true "Optional Title")

### 1.14.7. API Gateway

Application Programming Interface (API)

This is a way that applications or services can communicate with each other.

Endpoints are used to access services. Each service has its own endpoint
in its own region.

When you request AWS stops an EC2 instance, the message is set to the API
in that region for that resource.

APIs also perform authentication using passwords or keys. API authorizes
each service and needs your permissions verified each time.

![Stacks](../main/attachments/Screenshot-from-2023-05-10-23-42-30.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-10-23-45-02.png?raw=true "Optional Title")

#### 1.14.7.1. Authentication

![Stacks](../main/attachments/Screenshot-from-2023-05-10-23-52-14.png?raw=true "Optional Title")

#### 1.14.7.2. Endpoint types

![Stacks](../main/attachments/Screenshot-from-2023-05-10-23-54-37.png?raw=true "Optional Title")

#### 1.14.7.3. Errors

![Stacks](../main/attachments/Screenshot-from-2023-05-11-00-12-31.png?raw=true "Optional Title")

#### 1.14.7.3. Caching

![Stacks](../main/attachments/Screenshot-from-2023-05-11-00-19-29.png?raw=true "Optional Title")

### 1.14.8. Simple Queue Service (SQS)

Provides managed message queues, fully managed, highly available.

Replication happens within a region by default.

- Standard : 
- FIFO queue : 

Messages up to 256KB in size. These should link to larger sets of data.

Polling is checking for any messages on the queue. When a client polls
and recieves messages, they are hidden due to **visibility timeout**.

This is the amount of time that a client can wait to work on the messages.

If a client recieves messages on the queue and finishes on that workload
it can delete the message. If the client doesn't delete the message, then
it will reappear on the queue. The queue will put the message back in
and make sure a different client can retry that workload.

**Dead-letter queue** if a message is recieved multiple times but is unable
to be finished, this puts it into a different workload to try and fix
the corruption.

ASG can scale and lambdas can be invoked based on queue length.

![Stacks](../main/attachments/Screenshot-from-2023-05-11-21-58-29.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-11-21-58-50.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-11-22-09-33.png?raw=true "Optional Title")

#### 1.14.8.1. Highlights

Two types of queue

Standard - multi-lane HW
guarantee the order and at least once delivery.

FIFO - single lane road with no way to overtake
guarantee the order and at exactly once delivery
3,000 messages per second with batching or up to 300 messages second without

Billed on **requests** not messages. A request is a single request to SQS
One request can send 1 - 10 messages up to 64KB total.

Requests can return 0 messages. The more frequently you poll a SQS Queue,
the less effective it is.

Two ways to poll

- short (immediate) : uses 1 request and can return 0 or more messages. If the
queue is empty, it will return 0 and try again. This hurts queues that stay
short

- long (waitTimeSeconds) : it will wait for up to 20 seconds for messages
to arrive on the queue. It will sit and wait if none currently exist.

Messages can live on SQS Queue for up to 15 days. They offer KMS encryption
at rest.

Access is based on identity policies or a queue policy.

#### 1.14.8.2. SQS Standard vs FIFO Queues

![Stacks](../main/attachments/Screenshot-from-2023-05-13-21-07-10.png?raw=true "Optional Title")

#### 1.14.8.3. SQS Delay Queues

![Stacks](../main/attachments/Screenshot-from-2023-05-13-22-38-47.png?raw=true "Optional Title")

#### 1.14.8.4. SQS Dead-Letter Queues

![Stacks](../main/attachments/Screenshot-from-2023-05-14-10-53-45.png?raw=true "Optional Title")

### 1.14.9. Kinesis Data Streams

This is a scalable streaming service. It is designed to inject data from
lots of devices or lots of applications.

Producers send data into a Kinesis Stream.

The stream can scale from low to near infinite data rates.

Highly available public service by design.

Streams store a 24-hour moving window of data. Can be increased to 7 days.
Data that is 24 hours and a second more is replaced by new data entering
the stream.

Kinesis includes the store within it for the amount of data
that can be ingested during a 24 hour period. However much you ingest during
24 hours, that's included.

Multiple consumers can access data from that moving window.
One might look at data points once per hour while another looks at data in
real time.

Each shard can have 1MB/s for ingestion and 2MB/s consumption.

**Kinesis data records (1MB)** are stored accross shards and are the blocks
of data for a stream.

**Kinesis Firehose** connects to a Kinesis stream. It can move the data
from a stream onto S3 or another service.

![Stacks](../main/attachments/Screenshot-from-2023-05-14-11-10-24.png?raw=true "Optional Title")

### 1.14.10. SQS vs Kinesis

Is this about the ingestion of data or is it about the worker pools.

Large throughput or large numbers of devices, it is likely Kinesis.

SQS has 1 thing sending messages to the queue. One consumption group from
that tier.

Allow for async communications where the sender and reciever don't care
about what the other is doing. Once the message is processed, it is deleted.

Kinesis is desiged for huge scale ingestion with multiple consumers. Rolling
window for multiple consumers.

Designed for data ingestion, analytics, monitoring, app clicks.

![Stacks](../main/attachments/Screenshot-from-2023-05-14-11-13-21.png?raw=true "Optional Title")

### 1.14.11. Kinesis Data Firehose

![Stacks](../main/attachments/Screenshot-from-2023-05-14-11-28-50.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-19-03-18.png?raw=true "Optional Title")

### 1.14.12. Kinesis Data Analytics

![Stacks](../main/attachments/Screenshot-from-2023-05-14-19-19-42.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-19-41-11.png?raw=true "Optional Title")

### 1.14.13. Kinesis Video Streams

![Stacks](../main/attachments/Screenshot-from-2023-05-14-21-12-17.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-21-15-33.png?raw=true "Optional Title")

### 1.14.14. Amazon Cognito - User and Identity Pools

![Stacks](../main/attachments/Screenshot-from-2023-05-14-21-30-29.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-21-34-00.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-21-37-23.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-21-41-24.png?raw=true "Optional Title")

### 1.14.15. AWS Glue 101

![Stacks](../main/attachments/Screenshot-from-2023-05-14-22-36-49.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-22-38-26.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-22-48-34.png?raw=true "Optional Title")

### 1.14.16. Amazon MQ 101

![Stacks](../main/attachments/Screenshot-from-2023-05-14-22-52-44.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-21-34-00.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-22-57-49.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-22-59-34.png?raw=true "Optional Title")

### 1.14.17. Amazon AppFlow

![Stacks](../main/attachments/Screenshot-from-2023-05-14-23-04-26.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-14-23-05-56.png?raw=true "Optional Title")

## 1.15. CloudFront

### 1.15.1. Cloudfront Architecture

Cloudfront is a global object cache, also known as a content delivery network (CDN)

Content is cached in locations close to customers.
If the content is not available on the local cache when requested, ClouldFront
will pull and cache it then.

This provides lower latency and higher throughput for customers.

Can handle static and dynamic content.

**Origin**  the source location of your content
**Distribution** the configuration unit of CloudFront
Edge locations - local infrastructure which hosts a cache of your data.
There are over 200 edge locations. They can be one or more racks in a
third party server system.

Regional Edge Cache - larger version of an edge location. Provides
another layer of caching.

![Stacks](../main/attachments/Screenshot-from-2023-05-15-21-24-58.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-15-21-31-39.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-15-21-35-17.png?raw=true "Optional Title")


#### 1.15.1.1. CF TTL and Invalidations

![Stacks](../main/attachments/Screenshot-from-2023-05-17-21-44-26.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-17-21-44-33.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-17-22-02-38.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-17-22-08-46.png?raw=true "Optional Title")

#### 1.15.1.2. Caching Optimisation

Parameters can be passed on the url such as query string parameter.
An example is `?language=en` and `?language=es`

To get the cached copy, you need to use the same query strings. If you do
use them, ensure the strings are in the same order.

### 1.15.2. AWS Certificate Manager (ACM)

- HTTP lacks encryption and is insecure
- HTTPS uses SSL/TLS layer of encryption added to HTTP
- Data is encrypted in-transit
- Certificates allow servers to prove their identity
- Signed by a trusted authority (CA).
- To be secure, a website generates a certificate and has a CA sign it. The
website then uses that certificate to prove its authenticity.

Create, renew, and deploy certificates with ACM.

Supported AWS services ONLY (CloudFront and ALB, NOT EC2)

If it's not a managed service, ACM doesn't support it.

Cloudfront must have a trusted and signed certificate. It can't be self signed.

![Stacks](../main/attachments/Screenshot-from-2023-05-18-21-16-35.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-18-21-20-31.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-18-21-22-32.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-18-21-26-02.png?raw=true "Optional Title")

### 1.15.3. Cloudfront and SSL/TLS

![Stacks](../main/attachments/Screenshot-from-2023-05-18-21-36-44.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-18-22-30-47.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-18-22-42-28.png?raw=true "Optional Title")

### 1.15.4. Securing CF and S3 using OAI

This identity can be associated with a cloud front distribution.

The edge locations gain this identity.

We then remove the explicit allows and only allow the OAI to use it.

Best practice is to create one per distribution to manage permissions.

![Stacks](../main/attachments/Screenshot-from-2023-05-19-20-54-49.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-20-56-41.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-20-59-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-21-02-20.png?raw=true "Optional Title")

### 1.15.5. Private Distribution & Behaviours

![Stacks](../main/attachments/Screenshot-from-2023-05-19-22-22-17.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-22-24-47.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-22-35-31.png?raw=true "Optional Title")

### 1.15.6. Lambda@Edge

![Stacks](../main/attachments/Screenshot-from-2023-05-19-23-17-10.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-23-19-40.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-23-23-28.png?raw=true "Optional Title")

https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-examples.html#lambda-examples-redirecting-examples

### 1.15.7. AWS Global Accelerator

Starts with 2 **anycast** IP address
1.2.3.4 & 4.3.2.1

Anycast IP's allow a single IP to be in multiple locations.
Routing moves traffic to closest location.

Traffic initially uses public internet and enters a global
accelerator edge location.

#### 1.15.7.1.  Key concepts

Move the AWS network closer to customers.

Global Accelerator moves the AWS network as close as possible.

Connections enter at edge, using anycast IPs. Transit over AWS backbone to 1+
locations.

Global Accelerator is a network product. Can use TCP, UDP.

Caching is mostly CloudFront. TCP and UDP is mostly Global Accelerator

![Stacks](../main/attachments/Screenshot-from-2023-05-19-23-37-11.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-23-36-53.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-19-23-49-58.png?raw=true "Optional Title")

## 1.16. VPC Advanced

### 1.16.1. VPC Flow Logs

Capture packet metadata, not packet contents. Things like source IP,
destination IP, and packet size. Anything which could be observed
from the outside of the packet.

Capture data at various different monitoring points.

- VPC : all interfaces in that vpc
- Subnets : interfaces in that subnet
- Interface directly

VPC flow logs are not realtime.

Desination can be S3 or CloudWatch logs.

Childs of interfaces inherit the flow low monitoring from higher groups.

The packet will always have source followed by destination.

![Stacks](../main/attachments/Screenshot-from-2023-05-21-12-21-05.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-12-36-53.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-12-43-47.png?raw=true "Optional Title")

### 1.16.2. Egress-Only Internet Gateway

IPv4 addresses are private or public

NAT allows private IPs to access public networks. It will not allow externally
initiated connections.

Using IPv6, all IPs are public.

Internet Gateway (IPv6) allows all IPs **in** and **out**

Egress-only is **outbound only** for IPv6. It is exactly the same as
NAT, only outbound only.

To configure the Egress-only gateway, you must add default IPv6 route ::/0
added to RT with eigw-id as target.

![Stacks](../main/attachments/Screenshot-from-2023-05-21-13-08-09.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-13-21-13.png?raw=true "Optional Title")

### 1.16.3. VPC Endpoints (Gateway)

Provide private access to S3 and DynamoDB.

Normally when you want to access a public service through a VPC, you
need infrastructure to make this happen.

When you allocate a gateway endpoint to a subnet, a prefix list is added
to the route table.

The target is the gateway endpoint.

Any traffic destined for S3, goes via the gateway endpoint. The gateway
endpoint is highly available for all AZs in a region by default.

With a gateway endpoint you set which subnet will be used with it and
it will configure automatically.

A gateway endpoint is a VPC endpoint object.

Endpoint policy is used to control what things can be accessed by the endpoint.

Gateway endpoints can only be used to access services in the same region.
Can't access cross-region services.

S3 buckets can be set to private only by allowing access ONLY from
a gateway endpoint. For anything else, the implicit deny will apply.

They are only accessible from inside that specific VPC.

![Stacks](../main/attachments/Screenshot-from-2023-05-21-13-59-31.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-14-06-15.png?raw=true "Optional Title")

### 1.16.4. VPC Endpoints (Interface)

Provide private access to AWS Public Services
Anything EXCEPT S3 and DynamoDB

These are not HA by default and are added to specific subnets.

Must add one endpoint for one subnet per AZ

Network access controlled via security groups.

You can use Endpoint policies to restrict what can be accessed with
the endpoint.

ONLY TCP and IPv4 at the moment.

Behind the scenes, it uses PrivateLink.

Endpoint provides a **NEW** service endpoint DNS

e.g. vpce-123-xyz.sns.us-east-1.vpce.amazonaws.com

- Endpoint : Regional DNS
- Endpoint : Zonal DNS

Either of those two points of endpoints can be used

PrivateDNS overrides the default DNS for services.

![Stacks](../main/attachments/Screenshot-from-2023-05-21-20-54-36.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-20-58-47.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-21-00-35.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-21-01-32.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-21-01-57.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-21-05-05.png?raw=true "Optional Title")

### 1.16.5. VPC Peering

Direct encrypted network link between two VPCs

Works in the same or cross region and in the same or across accounts.

VPC peers have the option to allow Public Hostnames to resolve to
private IPs.

Same region SG's can reference peer security groups. This allows for the
same nesting of security groups within that region.

In different regions, you need to reference IP peers.

VPC peering connects **ONLY TWO**

VPC Peering does not support **transitive peering**

If you want to connect 3 VPCs, you need 3 connections. You can't route
through interconnected VPCs.

You are creating a logical gateway object in one VPC.

VPC Peering Connections CANNOT be created with overlapping VPC CIDRs

![Stacks](../main/attachments/Screenshot-from-2023-05-21-21-31-41.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-21-21-37-03.png?raw=true "Optional Title")

## 1.17. Hybrid Enviroment and Migration

### 1.17.1. Border Gateway Protocol 101

![Stacks](../main/attachments/Screenshot-from-2023-05-23-21-16-18.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-21-31-26.png?raw=true "Optional Title")

### 1.17.2. IPSec VPN Fundamentals

![Stacks](../main/attachments/Screenshot-from-2023-05-23-21-47-28.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-21-48-48.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-21-50-20.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-21-52-30.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-21-59-15.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-22-01-32.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-22-14-34.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-23-22-16-21.png?raw=true "Optional Title")

### 1.17.3. AWS Site-to-Site VPN

A logical connection between a VPC and on-premise network encrypted
using IPSec, running over the public internet.

This can be full High Availability if you design it correctly

Quick to provision, less than an hour.

VPNs connect VPCs and on-prem

Virtual Private Gateway (VGW) is the target on one or more route tables

Customer Gateway (CGW)

- logical configuration on AWS
- also the thing that configuration mentions

VPN connection itself stores the config and connects the VGW and CGW

![Stacks](../main/attachments/Screenshot-from-2023-05-25-10-54-17.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-11-00-34.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-11-09-05.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-11-13-38.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-11-34-09.png?raw=true "Optional Title")


#### 1.17.3.1. Considerations

Speed Cap on VPN 1.25Gbps

Latency Considerations - this is inconsistent because it uses the public
internet.

Cost - AWS hourly, GB out cost, data cap

Setup of hours or less

Great as a backup especially for Direct Connect (DX)

### 1.17.4. AWS Direct Connect (DX)

This is a 1 Gpbs or 10 Gbps Network Port into AWS

This is at a DX Location (1000-Base-LX or 10GBASE-LR)

This is a cross connect to your customer router (requires VLANS/BGP)

You can connect to a partner router if extending to your location.

The port needs to be arranged to connect somewhere else and connect to
your hardware.

This is a single fiber optic cable from the DX port to your network.

VIFS are multiple virtual interfaces (VIFS) over one DX

- Private VIF (VPC)
- Public VIF (Public Zone Services)

Has one physical cable with no high availability and no encryption.

Can take weeks or month for physica cable to be installed.

**Public VIF** is only public services, not public internet.

**Private VIF** is one VPC

DX Port Provisioning is likely quick, the cross-connect takes longer.

Generally use a VPN first then bring a DX in and leave VPN as backup.

40 Gbps with aggregation

It does not use public internet and provides consistently low latency.

DX provides NO ENCRYPTION and needs to be managed on a per application basis.

![Stacks](../main/attachments/Screenshot-from-2023-05-25-11-59-07.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-12-05-00.png?raw=true "Optional Title")

### 1.17.4.1. Direct Connect (DX) Resilience

![Stacks](../main/attachments/Screenshot-from-2023-05-25-14-04-56.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-14-11-42.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-14-14-38.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-14-19-59.png?raw=true "Optional Title")

### 1.17.4.2. Direct Connect (DX) - Public VIF + VPN (Encryption)

![Stacks](../main/attachments/Screenshot-from-2023-05-25-21-21-22.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-21-24-41.png?raw=true "Optional Title")
### 1.17.5. AWS Transit Gateway (TGW)

Network transit hub to connect VPCs to on premises networks

Significantly reduces network complexity.

There is a single network object which makes it HA and scalable.

Attachment to other network types.

VPC attachments are configured with a subnet in each AZ where service
is required.

You can use these for cross-region peering attachment.

Can share between accounts using AWS RAM

![Stacks](../main/attachments/Screenshot-from-2023-05-25-21-44-09.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-21-47-06.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-21-50-41.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-21-59-51.png?raw=true "Optional Title")

### 1.17.6. Storage Gateway

Hybrid Storage Virtual Application (On-premise)

Scenarios

Extend storange of File and Volume Storage into AWS.
Keep volume storage backups into AWS.
Tape backups into AWS. Can act as emulation layer.

Migration of extisting infrastructure into AWS slowly.

- Tape Gateway (VTL) Mode
  - Virtual Tapes are stored on S3

- File Mode : SMB and NFS
  - File Storage Backed by S3 Objects

- Volume Mode (Gateway Stored)
  - Block Storage backed by S3 and EBS
  - Great for disaster recovery
  - Data is kept locally
  - Awesome for migrations

- Volume Mode (Cache Mode)
  - Data as added to gateway is not stored locally.
  - Backup to EBS Snapshots
  - Primarily stored on AWS
  - Great for limited local storage capacity.

![Stacks](../main/attachments/Screenshot-from-2023-05-25-22-23-06.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-22-29-04.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-25-22-57-37.png?raw=true "Optional Title")

### 1.17.6.1. Storage Gateway - Tape (VTL)

![Stacks](../main/attachments/Screenshot-from-2023-05-26-10-48-10.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-10-50-32.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-10-57-14.png?raw=true "Optional Title")

### 1.17.6.2. Storage Gateway - File

![Stacks](../main/attachments/Screenshot-from-2023-05-26-11-09-45.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-11-15-08.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-11-18-03.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-11-24-58.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-11-30-26.png?raw=true "Optional Title")

### 1.17.7. Snowball / Edge / Snowmobile

Move large amounts of data IN and OUT of AWS

Physical storage the size of a suitcase or truck.

Ordered from AWS, use, then return.

#### 1.17.7.1. Snowball

Anything on Snowball uses KMS
50TB or 80TB Capacity
1 Gbps or 10 Gbps
This makes sense from 10 TB to 10 TB and over many premises.
This only includes storage

#### 1.17.7.2. Snowball Edge

Both storage and compute
Larger capacity vs snowball
10 Gbps or up to 100 Gbps

Storage optimized (with EC2) includes 1TB SSD
Compute optimized
Compute with GPU as above with GPU

These are great for remote sites when ingestion is needed

#### 1.17.7.3. Snowmobile

Portable data center within a shipping container on a truck.

This is a special order and is not available in high volume.
Ideal for single location where 10 PB+ is required.

Up to 100 PB per snowmobile.

This is not economical for multi-site for sub 10 PB

![Stacks](../main/attachments/Screenshot-from-2023-05-26-12-11-19.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-12-27-40.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-12-30-55.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-12-32-46.png?raw=true "Optional Title")

### 1.17.8. AWS Directory Service

This is a managed service with lots of use cases.

Stores objects, users, groups, computers, servers, file Shares with
a structure.

Multiple trees can be grouped into a forest.

Commonly used in Windows Environments.

Sign in to multiple devices with the same username/password provides
central management for assets.

it functions in three modes

Simple AD - An implementation of Samba 4 (compatibility with basics AD functions)
AWS Managed Microsoft AD - An actual Microsoft AD DS Implementation
AD Connector which proxies requests back to an on-premises directory.

#### 1.17.8.1. AWS managed implementation

Runs within a VPC as a private service.

Provides HA by deploying into multiple AZs.

Certain services in AWS need a directory, Amazon Workspaces.

To join EC2 instances to a domain you need a directory.

Can be isolated or integrated with existing on-prem system.

Could act as a proxy back to on-premises.

#### 1.17.8.2. Picking the Modes

Simple AD should be default

Microsoft AD is anything with Windows or if it needs a trust relationship
with on-prem. This is not an emulation.

AD Connector - Use AWS services without storing any directory info in the
cloud, it proxies to your on-prem directory.

![Stacks](../main/attachments/Screenshot-from-2023-05-26-14-20-29.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-14-26-11.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-14-32-14.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-14-34-30.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-14-37-28.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-14-39-30.png?raw=true "Optional Title")

### 1.17.9. AWS DataSync

Data transfer service TO and FROM AWS.

This is used for migrations or for large amounts of data processing transfers.

Designed to work at huge scales. Each agent can handle 10 GB and each job
can handle 50 million files.

This keeps metadata.

Has built in data validation to ensure the data matches.

Each agent is about 100 TB per day.

Can use bandwidth limiters to avoid customer impact

Has incrememetal and scheduled transfer options

Compression and encryption is also supported

It does data validation and automatic recovery from transit errors.

AWS service integration with S3, EFS, FSx for Windows servers.

Pay as you use product.

The data is encrypted in transit and all of the data transfer in parts.

#### 1.17.9.1. Components

Task is a job within datasync and defines what is going from where to where

Agent is software to read and write to on prem such as NFS or SMB

Location is the FROM and TO

![Stacks](../main/attachments/Screenshot-from-2023-05-26-17-03-44.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-17-09-31.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-17-15-22.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-17-16-48.png?raw=true "Optional Title")

### 1.17.10. FSx for Windows File Server

Fully managed native windows file servers/shares
Designed for integration with windows environments

Integrates with Directory Service or Self-Managed AD

Single or Multi-AZ within a VPC.

Can perform on-demand and scheduled backups.

File systems can be access using VPC, Peering, VPN, Direct Connect. Native
windows filesystem or Directory Services.

#### 1.17.10.1. Words to look for

VSS - User Driven Restores
Native file system accesible over SMB

Windows permissions model

Product supports DFS, scale out file share.

Managed - no file server admin

Integrates with DS and your own directory.

![Stacks](../main/attachments/Screenshot-from-2023-05-26-21-58-14.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-22-17-04.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-22-20-47.png?raw=true "Optional Title")

### 1.17.11. FSx For Lustre

![Stacks](../main/attachments/Screenshot-from-2023-05-26-22-35-04.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-22-37-49.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-22-39-53.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-22-42-01.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-26-22-44-30.png?raw=true "Optional Title")

### 1.17.12. AWS Transfer Family

![Stacks](../main/attachments/Screenshot-from-2023-05-27-11-08-29.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-11-10-11.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-11-17-38.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-11-19-04.png?raw=true "Optional Title")

## 1.18. Security, Deployment, Operations

### 1.18.1. AWS Secrets Manager

It does share functionality with parameter store.

This is designed specifically for secrets, passwords, API keys.

Usable via Console, CLI, API, or SDK

Supports the automatic rotation using Lambda.

It also directly integrates with RDS and other AWS products. If lambda
is invoked and changes a secret, the password can automatically
change in RDS.

This is great for rotating secrets and especially with RDS.

![Stacks](../main/attachments/Screenshot-from-2023-05-27-12-06-08.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-12-10-05.png?raw=true "Optional Title")

#### 1.18.1.1. Example

The Secrets Manager SDK can be used to retrieve credentials. It can use IAM
role or access keys to retrieve the secrets.

Once the application has these secrets, it can access the database.

Periodically, the lambda function can rotate the secrets. The Lambda uses
IAM roles to do this.

The authenticaion in RDS is also rotated automatically.

Secrets are secured via KMS which ensures role seperation.

#### 1.18.1.2. Application Layer (L7) Firewall

![Stacks](../main/attachments/Screenshot-from-2023-05-27-19-41-54.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-19-46-21.png?raw=true "Optional Title")

### 1.18.2. WAF (web application firewall)

Layer 7 firewall (HTTP/s) firewall

Protects against these complex layer 7 attacks like:

SQL injections, cross-site scripting, geo blocks, rate awareness.

Main entity provided is a WEBACL that is integrated with Load Balancers,
API gateways, and cloudfront.

The rules are added to WEBACL and evaluated when traffic arrives.

![Stacks](../main/attachments/Screenshot-from-2023-05-27-21-07-28.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-21-10-16.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-21-13-43.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-21-29-19.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-21-32-01.png?raw=true "Optional Title")

#### 1.18.2.1. Example of Architecture

Shield standard automatically looks at the data before any data reaches
past Route53.

The user is directed to the closest CloudFront location. Again, shield
standard looks at the data again before it moves on.

WAF Rules are defined and included in a WEBACL which is associated to a
cloud front distribution and deployed to the edge.

Shield advanced can then intercept traffic when it reaches the load balancer.

Once the data reaches the VPC, it has been filtered at Layer 3, 4, and 7
already.

Layer 7 filtering is only provided by WAF.

### 1.18.3. AWS Shield

Provides against DDoS attacks with AWS resources. This is a denial of
service attack. Normally not possible to block them by using individual
IP addresses. Without detailed anaylsis, the traffic looks like normal
requests to your website.

Shield Standard - Free with Route53 and CloudFront as default
Provides layer 3 and layer 4 protection against DDoS attacks.

Shield advanced - $3000 per month

- Includes EC2, ELB, CloudFront, Global Acceleration and R53
- Provides access to DDoS advanced response team and financial insurance
against increased costs.

![Stacks](../main/attachments/Screenshot-from-2023-05-27-22-00-27.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-22-01-52.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-22-04-39.png?raw=true "Optional Title")

![Stacks](../main/attachments/Screenshot-from-2023-05-27-22-07-57.png?raw=true "Optional Title")

### 1.18.3. CloudHSM

An applicance which creates and managed cryptographic material such as keys.

KMS is a shared service with other AWS accounts.

Although the permissions are strict, AWS still does manage the hardware for KMS.

You can run your own HSM on premise. Cloud HSM is a true "single tenant"
hardware security module (HSM)

AWS provisioned, but it is impossible for them to help. There is no way
to recover data from them if access is lost.

Fully FIPS 140-2 Level 3 (KSM is L2 overall, but some is L3)

IF you require level 3 overall, you MUST use CloudHSM.

KSM all actions are performed with AWS CLI and IAM roles.

HSM uses

- PKCS#11
- Java Cryptography Extensions (JCE)
- Microsoft CryptoNG (CNG) libraries

KMS can use CloudHSM as a custom key store, CloudHSM integrates with KMS.

HSM is not highly available and runs within one AZ. You need at least
two HSMs and one in each AZ you use. Once HSM is in a cluster, they
replicate all policies in sync automatically.

HSM needs an endpoint in the subnet of the VPC to allow resources access
to the cluster.

AWS has no access to the HSM appliances which store the keys.

#### 1.18.3.1. Cloud HSM Use Cases

No native AWS integration with AWS products. You can't use S3 SSE with
CloudHSM.

Can be used to offload the SSL/TLS processing for the webservers. CloudHSM
is much more efficent to do these encryption processes.

Oracle Databases can use CloudHSM to enable transparent data encryption (TDE)

This can be used to protect the private keys for an issuing
certificate authority.

Anything that needs to interact with non AWS products.

### 1.18.4. CloudHSM