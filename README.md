# CCNP-DCCORE-350-601
these are my notes and  labs i completed for preparing for  the CCNP DCCORE 350-601 Certification exam of CISCO networking Enterprise
This README provides a detailed description of the network configuration for the "Enterprise of LAWYER BROTHERS" network mega lab. The configuration includes various components such as WAN setup, OSPF, BGP, HSRP (Hot Standby Router Protocol), VLANs, VRF (Virtual Routing and Forwarding), and DHCP configurations. It also involves three routers interconnected in a complex network.

## **WAN Configuration and ISP Protocols**

### **Router 1**

- **WAN Configuration**:
    - Interface e0/0:
        - IP Address: 10.10.3.1 /30
    - Interface e0/1:
        - IP Address: 10.10.2.1 /30
- **OSPF Configuration**:
    - Area 0:
        - OSPF Process: 1
        - Interface Range: e0/0-1
    - Area 1:
        - OSPF Process: 1
        - Interface e0/2 and e0/3

### **Router 2**

- **WAN Configuration**:
    - Interface e0/1:
        - IP Address: 10.10.2.2 /30
    - Interface e0/2:
        - IP Address: 1.1.2.2 /30
    - Interface e1/1:
        - IP Address: 1.1.3.2 /30
- **OSPF Configuration**:
    - OSPF Process: 1
    - Area 0:
        - Interfaces e0/1, e0/2, and e1/1

### **Router 3**

- **WAN Configuration**:
    - Interface e0/0:
        - IP Address: 10.10.3.2 /30
    - Interface e0/3:
        - IP Address: 1.1.1.2 /30
    - Interface e1/1:
        - IP Address: 1.1.4.2 /30
- **OSPF Configuration**:
    - OSPF Process: 1
    - Area 0:
        - Interface e1/1
    - Area 1:
        - Interface e0/0

### **ISP 1 BGP & BFD Configuration (AS 65200)**

- **Router 4**:
    - Interfaces e0/0, e0/1, e0/2, e0/3, e1/0-1 with BFD
    - BGP Configuration with neighbors from Router 1 and Router 2
- **Router 5**:
    - Interfaces e0/0-3, e1/1 with BFD
    - BGP Configuration with neighbors from Router 1 and Router 3

### **ISP 2 Configuration**

- **Vios 5 Router**:
    - Interfaces g0/0-1 with BFD
    - BGP Configuration with neighbors from Router 5 and Router 6
- **Vios 6 Router**:
    - Interfaces g0/0-1 with BFD
    - BGP Configuration with neighbors from Router 5 and Router 6

## **Router 1 Standby Configuration**

- Standby Interfaces for Router 1:
    - e0/0.1: IP 172.16.1.200
    - e0/0.2: IP 172.16.3.200

## **Router 3 Standby Configuration**

- Standby Interfaces for Router 3:
    - e0/1.1: IP 192.168.1.200
    - e0/2.2: IP 172.16.3.200

## **VLAN Configuration**

### **VLAN 2:**

- Configuration for VLAN 2 on switches

### **VLAN 3:**

- Configuration for VLAN 3 on switches

### **VLAN 4:**

- Configuration for VLAN 4 on switches

## **Router 1 Sub-Interfaces**

- Configuration for sub-interfaces on Router 1:
    - Sub-interface e0/2.1: VLAN 2
    - Sub-interface e0/2.2: VLAN 3

## **Router 3 Sub-Interfaces**

- Configuration for sub-interfaces on Router 3:
    - Sub-interface e0/1.1: VLAN 2
    - Sub-interface e0/1.2: VLAN 3
    - Sub-interface e0/1.3: VLAN 4

## **Router 1 HQ**

### **HQ_CEO:**

- Configuration for VRF, DHCP, and HSRP:
    - VRF HQ_CEO
    - DHCP for the HQ_CEO network
    - HSRP Configuration for failover and redundancy

### **HR_DEP:**

- Configuration for VRF, DHCP, and HSRP:
    - VRF HR_DEP
    - DHCP for the HR_DEP network
    - HSRP Configuration for failover and redundancy

### **IT_Admin:**

- Configuration for VRF, DHCP, and HSRP:
    - VRF IT_Admin
    - DHCP for the IT_Admin network
    - HSRP Configuration for failover and redundancy

### **Secretary:**

- Configuration for VRF, DHCP, and HSRP:
    - VRF Secretary
    - DHCP for the Secretary network
    - HSRP Configuration for failover and redundancy

## **Router 1 Branch Office**

### **Accountants:**

- Configuration for VRF, DHCP, and HSRP:
    - VRF Accountants
    - DHCP for the Accountants network
    - HSRP Configuration for failover and redundancy

### **Lawyers:**

- Configuration for VRF, DHCP, and HSRP:
    - VRF Lawyers
    - DHCP for the Lawyers network
    - HSRP Configuration for failover and redundancy

## **Router 2**

### **Accountants:**

- Configuration for VRF, DHCP, HSRP, and BGP with neighbors

### **Lawyers:**

- Configuration for VRF, DHCP, HSRP, and BGP with neighbors

## **Router 3**

### **HQ_CEO:**

- Configuration for VRF, DHCP, HSRP, and BGP with neighbors

### **HR_DEP:**

- Configuration for VRF, DHCP, HSRP, and BGP with neighbors

### **IT_Admin:**

- Configuration for VRF, DHCP, HSRP, and BGP with neighbors

### **Secretary:**

- Configuration for VRF, DHCP, HSRP, and BGP with neighbors

## **VLAN and Interface Configuration**

- Additional VLAN and interface configurations for network segmentation.

This README provides an in-depth understanding of the complex networking configuration for the "Enterprise of LAWYER BROTHERS" network. You can use this information as a reference when setting up or troubleshooting this network configuration.
