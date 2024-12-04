+----------------------------------+------------------------+----------+
| ![](vertopal_                    |                        |          |
| 92cf16098c9741678a97ed36306a7ef0 |                        |          |
| /media/image1.png){width="2.4in" |                        |          |
| height="0.5881944444444445in"}   |                        |          |
|                                  |                        |          |
| SCHOOL OF INFORMATION AND        |                        |          |
| TECHNOLOGY                       |                        |          |
+----------------------------------+------------------------+----------+
| NAME:                            | DATE PERFORMED:        | /50      |
+----------------------------------+------------------------+----------+
| Section:                         | DATE SUBMITTED:        |          |
+----------------------------------+------------------------+----------+

# SYSADM1 -- Capacity Management & Planning

## Part 1. A Simulated Dataset for Capacity Planning Exercise {#part-1.-a-simulated-dataset-for-capacity-planning-exercise .list-paragraph}

![](vertopal_92cf16098c9741678a97ed36306a7ef0/media/image2.png){width="4.749564741907261in"
height="2.4791666666666665in"}**Scenario:** A mid-sized e-commerce
website is expecting a significant surge in traffic due to an upcoming
holiday sale.

### [Projected Traffic Increase]{.underline}

-   **Expected Peak Traffic:** 5x the normal peak traffic

-   **Peak Time:** 12:00 PM - 3:00 PM on the sale day

### [System Specifications]{.underline}

-   **Server Count:** 5

-   **CPU Cores per Server:** 8

-   **RAM per Server:** 32GB

-   **Network Bandwidth per Server:** 1Gbps

### [Additional Considerations]{.underline}

-   **New Product Launch:** A highly anticipated product will be
    released during the sale.

-   **Marketing Campaign:** A major marketing campaign will be launched
    to promote the sale.

-   **Potential Cyber Threats:** Increased traffic can attract malicious
    actors.

Tasks:

1.  Review the provided server performance data and identify potential
    bottlenecks

2.  Brainstorm possible solutions to address the identified bottlenecks.
    Propose potential solutions considering hardware and software-based
    solutions.

3.  Discuss the pros and cons of each proposed solution by filling out
    the table below.

+-------------+---------------+------------+--------------+-----------+
| Proposed    |               | Cost       | Complexity   | Potential |
| Solution    | ------------- |            |              | impact on |
|             |   Pros   Cons |            |              | system    |
|             |               |            |              | pe        |
|             | ------ ------ |            |              | rformance |
|             |               |            |              |           |
|             |               |            |              |           |
|             | ------------- |            |              |           |
+=============+===============+============+==============+===========+
+-------------+---------------+------------+--------------+-----------+

Grading Rubric:

  -------------------------------------------------------------------------------
  Criteria           Excellent \| 10pts Good \| 7pts        Needs Improvement \|
                                                            4pts
  ------------------ ------------------ ------------------- ---------------------
  **Problem          Accurately         Identifies the main Identifies a problem
  Identification**   identifies the     problem and         but lacks clarity or
                     primary problem    provides a basic    accuracy.
                     and provides a     explanation.        
                     detailed                               
                     explanation.                           

  **Solution         Proposes multiple  Proposes one or two Proposes a solution
  Proposal**         relevant solutions relevant solutions  but lacks feasibility
                     and provides       but lacks detailed  or relevance.
                     detailed           explanation.        
                     explanations,                          
                     including                              
                     potential                              
                     drawbacks and                          
                     benefits.                              

  **Evaluation of    Provides a         Provides a basic    Does not evaluate the
  Solutions**        thorough           evaluation of the   proposed solutions or
                     evaluation of the  proposed solutions, provides a
                     proposed           but lacks depth.    superficial
                     solutions,                             evaluation.
                     considering                            
                     factors like cost,                     
                     complexity, and                        
                     potential impact.                      

  Score:                                                    /30
  -------------------------------------------------------------------------------

**Part 2. Network Scalability Analysis**

Recall the e-commerce website scenario we discussed earlier. Given the
expected surge in traffic, analyze the provided network topology
diagram. Identify potential bottlenecks and areas where scalability
might be a concern. Propose specific strategies to improve the
network\'s scalability and performance to ensure a seamless user
experience during the peak traffic period. Consider factors such as
increased user demand, new applications, and security threats.

![](vertopal_92cf16098c9741678a97ed36306a7ef0/media/image3.webp){width="5.049483814523184in"
height="3.8229166666666665in"}

**Analysis of the Current Network Topology**

The current topology is relatively simple, with a single core switch
connecting VLANs via Layer 2 switches. While functional, this setup has
potential bottlenecks and scalability concerns:

1.  Core Switch as a Single Point of Failure

-   If the core switch fails, the entire network collapses.

2.  Layer 2 Switch Bottlenecks

-   VLAN traffic relies heavily on the uplink to the core switch. High
    traffic during peak hours (12 PM--3 PM) can overload uplinks.

3.  Insufficient Redundancy

-   No backup for the core switch, edge router, or ISP, leading to a
    lack of fault tolerance.

4.  Limited Scalability

-   Adding more servers or applications could overwhelm existing
    switches and bandwidth.

5.  Potential Security Vulnerabilities

-   No clear indication of dedicated firewalls, intrusion
    detection/prevention systems, or DDoS protection.

**Proposed Strategies to Improve Scalability and Performance**

![image](https://github.com/user-attachments/assets/5e1d8329-88a7-43ab-a8f5-1f94caa3fa0a)

height="4.632638888888889in"}

I.  Add a Backup Core Switch

-   Introduce a secondary core switch configured in Active-Passive mode
    using protocols like VRRP or HSRP to ensure network redundancy and
    eliminate the core switch as a single point of failure. This setup
    ensures seamless failover if the primary core switch fails,
    maintaining network uptime during critical periods.

II. Upgrade to Layer 3 Distribution Switches

-   Replace the existing Layer 2 switches with Layer 3 switches to
    handle inter-VLAN routing more efficiently. By offloading routing
    tasks from the core switch and implementing EtherChannel for
    increased uplink bandwidth, this upgrade reduces bottlenecks and
    improves scalability.

III. Introduce Redundant ISPs

-   Add a backup ISP and configure the edge router for load balancing or
    failover to ensure uninterrupted internet connectivity during peak
    traffic periods or ISP outages, enhancing overall network
    availability.

IV. Increase Uplink Bandwidth

-   Utilize EtherChannel to combine multiple physical links into a
    single logical connection, effectively increasing the bandwidth
    between switches and alleviating potential congestion during
    high-traffic events.

V.  Deploy Load Balancers

-   Implement hardware or load balancers to evenly distribute traffic
    across servers, preventing server overload and improving response
    times and user experience during peak periods.

VI. Add a Firewall and IDS/IPS

-   Deploy a robust firewall solution such as Adguard to block external
    threats and integrate an IDS/IPS like Snort for real-time monitoring
    and prevention of attacks, safeguarding the network from malicious
    actors during high-profile campaigns.

VII. Optimize Server Resources

-   Scale server resources by increasing CPU cores and RAM (vertical
    scaling) or adding more servers (horizontal scaling) to ensure
    sufficient capacity for handling the anticipated fivefold increase
    in traffic during peak hours.

VIII. Bandwidth Management

-   If the number of connected devices increases, will the links between
    layers (core to distribution, distribution to access) have enough
    bandwidth to avoid congestion. If the current uplinks are 1 Gbps,
    will they support future needs? If not, consider upgrading to 10
    Gbps links or higher.

**Addressing Concerns and Scalability**

  -----------------------------------------------------------------------
  **Concern**             **Proposed Solution**   **Impact**
  ----------------------- ----------------------- -----------------------
  Single point of failure Add a backup core       Ensures network
                          switch and redundant    reliability and uptime
                          ISPs.                   during peak traffic.

  VLAN performance issues Replace Layer 2         Offloads routing from
                          switches with Layer 3   core switch, improves
                          distribution switches.  performance.

  ISP downtime            Add a backup ISP with   Ensures continuous
                          load balancing or       internet connectivity.
                          failover.               

  Server overload         Scale server resources  Handles increased
                          (vertical and           traffic during peak
                          horizontal scaling).    hours.

  Security threats        Deploy firewalls,       Mitigates risks from
                          IDS/IPS, and DDoS       malicious actors during
                          protection.             marketing campaigns.
  -----------------------------------------------------------------------

**Benefits of the Proposed Changes**

1.  Improved Scalability

-   Supports additional servers, applications, and traffic demands.

2.  Enhanced Performance

-   Reduced congestion and faster response times for end users.

3.  High Availability

-   Redundant systems ensure uninterrupted service during failures.

4.  Better Security

-   Proactive measures protect against cyber threats.

  ------------------------------------------------------------------------------
  Criteria          Excellent \| 10pts Good \| 7pts        Needs Improvement \|
                                                           4pts
  ----------------- ------------------ ------------------- ---------------------
  **Network         Accurately         Identifies key      Identifies some basic
  Analysis**        identifies         network components  network components
                    potential          and some potential  but lacks a
                    bottlenecks,       bottlenecks.        comprehensive
                    security risks,                        analysis.
                    and capacity                           
                    limitations.                           

  **Scalability     Proposes multiple  Proposes some       Proposes limited
  Planning**        relevant solutions relevant            scalability
                    and provides       scalability         strategies.
                    detailed           strategies but      
                    explanations,      lacks detail.       
                    including                              
                    potential                              
                    drawbacks and                          
                    benefits.                              

  **Evaluation of   Proposes           Provides a basic    Does not evaluate the
  Solutions**       comprehensive      evaluation of the   proposed solutions or
                    scalability        proposed solutions, provides a
                    strategies,        but lacks depth.    superficial
                    including specific                     evaluation.
                    recommendations                        
                    for hardware                           
                    upgrades, software                     
                    configurations,                        
                    and network                            
                    optimizations.                         

  **Proposed        Provides a         Provides a basic    Does not provide a
  Design**          detailed and       design but lacks    clear and detailed
                    well-justified     specific details    design.
                    design, including  and justifications. 
                    network diagrams,                      
                    configuration                          
                    details, and                           
                    implementation                         
                    plans.                                 

  **Evaluation and  Provides a         Provides a basic    Does not evaluate the
  Justification**   thorough           evaluation of the   proposed solutions or
                    evaluation of the  proposed solutions, provides a
                    proposed           but lacks depth.    superficial
                    solutions,                             evaluation
                    considering                            
                    factors like cost,                     
                    complexity, and                        
                    potential impact.                      

  Score:                                                   /50
  ------------------------------------------------------------------------------
