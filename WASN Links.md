
# Unit1
#unit1 

[Characteristics of MANETs](https://www.geeksforgeeks.org/introduction-of-mobile-ad-hoc-network-manet/)  
[Application of manet](https://www.javatpoint.com/mobile-adhoc-network)  

> ***Challenges in Manet***
> 
> Mobile Ad hoc Networks (MANETs) present several challenges due to their unique characteristics and dynamic nature. Some of the key challenges faced in MANETs include:
>  
>  1. Limited Network Resources: MANETs typically have limited resources in terms of bandwidth, processing power, and energy. Since the nodes in the network are mobile and operate on battery power, resource constraints become a significant challenge.
>  
>  2. Dynamic Network Topology: Nodes in MANETs can join or leave the network at any time, leading to a highly dynamic network topology. This dynamic nature makes routing and maintaining connectivity between nodes challenging.
>  
>  3. Node Mobility: The mobility of nodes in MANETs introduces additional challenges. As nodes move, the network topology changes, which requires efficient and adaptive routing algorithms to handle frequent changes in connectivity.
>  
>  4. Scalability: The scalability of MANETs is a significant challenge. As the network size increases, the overhead associated with routing and maintaining network state information also increases. The design of scalable routing protocols that can handle large-scale MANETs is a challenging task.
>  
>  5. Security: MANETs are susceptible to various security threats due to their open and dynamic nature. Attacks such as node impersonation, eavesdropping, and denial-of-service can compromise the integrity, confidentiality, and availability of communication in the network.
>  
>  6. Quality of Service (QoS): Ensuring QoS requirements such as latency, reliability, and throughput in MANETs is challenging due to resource constraints, dynamic topology, and node mobility. Providing efficient QoS support is crucial for applications such as multimedia streaming and real-time communication.
>  
>  7. Routing: Designing efficient and robust routing protocols for MANETs is a significant challenge. Traditional routing protocols, such as those used in wired networks, may not be suitable due to the dynamic nature of MANETs. The routing protocols in MANETs should adapt to changing network conditions, handle node mobility, and minimize overhead.
>  
>  8. Energy Efficiency: Energy conservation is crucial in MANETs due to limited battery power. Energy-efficient protocols and techniques, such as power-aware routing and sleep mode operation, need to be developed to prolong the network's lifetime.
>  
>  9. Quality of Experience (QoE): In addition to QoS, providing a satisfactory user experience is essential in MANETs. Applications should be designed to handle the intermittent connectivity and network disruptions common in MANETs, ensuring smooth and seamless user experience.
>  
>  Addressing these challenges requires innovative solutions, including the development of efficient protocols, algorithms, and system designs tailored specifically for MANETs. Researchers and engineers continue to work on advancing the state-of-the-art to overcome these challenges and make MANETs more reliable, secure, and efficient.


> ***Topology based routing***
> 
>   Topology-based routing protocols depend on the information about existing links in the network and utilize them to carry out the task of packet forwarding.

### Types of topology-based

> ***Proactive routing protocol***
>   
>    These are also known as table-driven routing protocols. Each mobile node maintains a separate routing table which contains the information of the routes to all the possible destination mobile nodes. 
>
>   Since the topology in the mobile ad-hoc network is dynamic, these routing tables are updated periodically as and when the network topology changes. It has a limitation that it doesn’t work well for the large networks as the entries in the routing table becomes too large since they need to maintain the route information to all possible nodes.

### Type of proactive protocols
![Screenshot 2023-05-24 112917.png](./Screenshot%202023-05-24%20112917.png)
![Screenshot 2023-05-24 112850.png](Screenshot%202023-05-24%20112850.png)

>1. **DESTINATION-SEQUENCED DISTANCE-VECTOR PROTOCOL** : 
>    
>    The destination sequenced distance-vector (DSDV)  is a proactive hop-by-hop distance vector routing protocol, requiring each node to periodically broadcast routing updates. Here, every mobile node in the network maintains a routing table for all possible destinations within the network and the number of hops to each destination. Each entry is marked with a sequence number assigned by the destination node. The sequence numbers enable the mobile nodes to distinguish stale routes from new ones, thereby avoiding the formation of routing loops. Routing table updates are periodically transmitted throughout the network in order to maintain consistency in the table. To alleviate the potentially large amount of network update traffic, route updates can employ two possible types of packets: full dumps or small increment packets. A full dump type of packet carries all available routing information and can require multiple network protocol data units (NPDUs). These packets are transmitted infrequently during periods of occasional movement. Smaller incremental packets are used to relay only the information that has changed since the last full dump. Each of these broadcasts should fit into a standard-size NPDU, thereby decreasing the amount of traffic generated. The mobile nodes maintain an additional table where they store the data sent in the incremental routing information packets. New route broadcasts contain the address of the destination, the number of hops to reach the destination, the sequence number of the information received regarding the destination, as well as a new sequence number unique to the broadcast. The route labeled with the most recent sequence number is always used. In the event that two updates have the same sequence number, the route with the smaller metric is used in order to optimize (shorten) the path. Mobiles also keep track of settling time of the routes, or the weighted average time that routes to a destination could fluctuate before the route with the best metric is received. By delaying the broadcast of a routing update by the length of the settling time, mobiles can reduce network traffic and optimize routes by eliminating those broadcasts that would occur if a better route could be discovered in the very near future.
>    used. In the event that two updates have the same sequence number, the route with the smaller metric is used in order to optimize (shorten) the path. Mobiles also keep track of settling time of the routes, or the weighted average time that routes to a destination could fluctuate before the route with the best metric is received. By delaying the broadcast of a routing update by the length of the settling time, mobiles can reduce network traffic and optimize routes by eliminating those broadcasts that would occur if a better route could be discovered in the very near future.
>   ![Screenshot 2023-05-24 121638.png](Screenshot%202023-05-24%20121638.png)![Screenshot 2023-05-24 122644.png](Screenshot%202023-05-24%20122644.png)
>   
>   
>    2. **THE WIRELESS ROUTING PROTOCOL** : 
>    The Wireless Routing Protocol (WRP) described is a table-based protocol with the goal of maintaining routing information among all nodes in the network. Each node in the network is responsible for maintaining four tables: Distance table, Routing table, Link-cost table, and the Message Retransmission List (MRL) table. Each entry of the MRL contains the sequence number of the update message, a retransmission counter, an acknowledgment-required flag vector with one entry per neighbour, and a list of updates sent in the update message. The MRL records which updates in an update message need to be retransmitted and neighbours should acknowledge the retransmission. Mobiles inform each other of link changes through the use of update messages. An update message is sent only between neighbouring nodes and contains a list of updates (the destination, the distance to the destination, and the predecessor of the destination), as well as a list of responses indicating which mobiles should acknowledge (ACK) the update. After processing updates from neighbours or detecting a change in a link, mobiles send update messages to a neighbour. In the event of the loss of a link between two nodes, the nodes send update messages to their neighbours. The neighbours then modify their distance table entries and check for new possible paths through other nodes. Any new paths are relayed back to the original nodes so that they can update their tables accordingly.
>    Nodes learn about the existence of their neighbours from the receipt of acknowledgments and other messages. If a node is not sending messages, it must send a hello message within a specified time period to ensure connectivity. Otherwise, the lack of messages from the node indicates the failure of that link; this may cause a false alarm. When a mobile receives a hello message from a new node, that new node is added to the mobiles routing table, and the mobile sends the new node a copy of its routing table information. Part of the novelty of WRP stems from the way in which it achieves freedom from loops. In WRP, routing nodes communicate the distance and second-to-last hop information for each destination in the wireless networks. WRP belongs to the class of path-finding algorithms with an important exception. It avoids the “count-to-infinity” problem by forcing each node to perform consistency checks of predecessor information reported by all its neighbour’s. This ultimately (although not instantaneously) eliminates looping situations and provides faster route convergence when a link failure occurs.
>    ![Screenshot 2023-05-24 123258.png](Screenshot%202023-05-24%20123258.png)
>    ![Screenshot 2023-05-24 123337.png](Screenshot%202023-05-24%20123337.png)
>
>   **Other methods** :
>   3. The Topology Broadcast based on Reverse Path Forwarding Protocol
>   4. The Optimized Link State Routing Protocol
>   5. Multipoint Relays
>   6. The Source Tree Adaptive Routing Protocol
>    

> ***Reactive routing protocols***
> 
>   These are also known as on-demand routing protocol. In this type of routing, the route is discovered only when it is required/needed. The process of route discovery occurs by flooding the route request packets throughout the mobile network. It consists of two major phases namely, route discovery and route maintenance.

### Type of reactive routing protocols

>  1. **DYNAMIC SOURCE ROUTING** : Theory in notes ![Screenshot 2023-05-24 124055.png](Screenshot%202023-05-24%20124055.png)![Screenshot 2023-05-24 124523.png](Screenshot%202023-05-24%20124523.png)
>  2. **THE AD HOC ON-DEMAND DISTANCE VECTOR PROTOCOL** : theory in notes![Screenshot 2023-05-24 125308.png](Screenshot%202023-05-24%20125308.png)
>  ![Screenshot 2023-05-24 125214.png](Screenshot%202023-05-24%20125214.png)
>  Other without theory:
>  1.  Link Reversal Routing and TORA

> ***Hybrid Routing Protocols***
>   It basically combines the advantages of both, reactive and pro-active routing protocols. These protocols are adaptive in nature and adapts according to the zone and position of the source and destination mobile nodes. One of the most popular hybrid routing protocol is **Zone Routing Protocol (ZRP)**. 
>
>   The whole network is divided into different zones and then the position of source and destination mobile node is observed. If the source and destination mobile nodes are present in the same zone, then proactive routing is used for the transmission of the data packets between them. And if the source and destination mobile nodes are present in different zones, then reactive routing is used for the transmission of the data packets between them.
> ![Pasted image 20230524144620.jpg](Pasted%20image%2020230524144620.jpg)
> 
>  Types: 
>   1. Zone Routing Protocol
>   2. Fisheye State Routing
>   3. Landmark Routing (LANMAR) for MANET with Group Mobility
>   4. Cluster-Based Routing Protocol
>   
>   


> ***position based routing***
>
>  Since mobile ad-hoc networks change their topology frequently and without prior notice, routing in such networks is a challenging task. Position-based routing algorithms eliminate some of the limitations of topology-based routing by using additional information. They require information about the physical position of the participating nodes in the network their availability. Commonly, each node determines its own position through the use of GPS or some other type of positioning service. Position based routing is mainly focused on two issues: one; A location service is used by the sender of a packet to determine the position of the destination and to include it in the packet's destination address and two; A forwarding strategy used to forward the packets. 
>  
>  A location service can be any one of the four:
>    a) Some for some 
>    b) Some for all 
>    c) All for all 
>    d) All for some. 
>    Protocols are : 
>    - Distance Routing Effect Algorithm for Mobility
>    - Quorum-Based Location Service
>    - Grid Location Service
>    - Homezone
>    
>   A forwarding strategy can be like; 
>    a) Greedy forwarding 
>    b) Restricted directional flooding 
>    >  Subtypes:
>    >   1. DREAM
>    >   2. Location-Aided Routing
>    >   3. Relative Distance Micro-Discovery Ad Hoc Routing
>    c) Hierarchical routing. 
>    >Subtypes:
>    >   1. Terminodes Routing
>    >   2. Grid Routing
>    >   3. Relative Distance Micro-Discovery Ad Hoc Routing
>    
>    
>   The routing decision at each node is then based on the destination's position contained in the packet and the position of the forwarding node's neighbors. Position-based routing does not require the establishment or maintenance of routes. The nodes neither have to store routing tables nor do they need to transmit messages to keep routing tables up-to date.


> ***OTHER ROUTING PROTOCOLS*** 
>  
 >   There is plenty of routing protocol proposals for mobile ad hoc networks. Our discussion here is far from being exhaustive. Below we will describe some other routing protocols which employ different optimization criteria as the ones we have previously described.
 >   
>   1. **SIGNAL STABILITY ROUTING** : Another on-demand protocol is the Signal Stability-Based Adaptive Routing protocol (SSR). Unlike the algorithms described so far, SSR selects routes based on the signal strength (weak or strong) between nodes and a node’s location stability. The signal strengths of neighboring nodes are obtained by periodic beacons from the link layer of each neighboring node. This route selection criterion of SSR has the effect of choosing routes that have “stronger” connectivity.
>   2. **POWER AWARE ROUTING**: In this protocol, power-aware metrics are used for determining routes in wireless ad hoc networks. It has been shown that using these metrics in a shortest-cost routing algorithm reduces the cost/packet of routing packets by 5 - 30 percent over shortest-hop routing (this cost reduction is on top of a 40- 70 percent reduction in energy consumption over the MAC layer protocol used). Furthermore, using these new metrics ensures that mean time to node failure is increased significantly, but packet delays do not increase. A recent work concentrates on selecting a route based the traffic and congestion characteristics in the network.
>   3. **ASSOCIATIVITY-BASED ROUTING** : This is a totally different approach in mobile routing. The Associativity-Based Routing (ABR) protocol is free from loops, deadlock, and packet duplicates, and defines a new routing metric for ad hoc mobile networks. In ABR, a route is selected based on a metric that is known as the degree of association stability. Each node periodically generates a beacon to signify its existence. When received by neighboring nodes, this beacon causes their associability tables to be updated. For each beacon received, the associatively tick of the current node with respect to the beaconing node is incremented. Association stability is defined by connection stability of one node with respect to another node over time and space. A high (low) degree of association stability may indicate a low (high) state of node mobility. Associability ticks are reset when the neighbors of a node or the node itself move out of proximity. A fundamental objective of ABR is to derive longer-lived routes for ad hoc networks. The three phases of ABR are: 
>   • Route discovery, 
>   • Route reconstruction (RRC), 
>   • Route deletion

# Unit2
#unit2 

[Broadcasting Storm](https://www.geeksforgeeks.org/whats-a-broadcast-storm/)  
[Tcp](https://www.javatpoint.com/tcp)  

> ***Fairness-Related***
> 
> Here's the information about ***Neighborhood RED (NRED)***:
>
>  Neighborhood RED (NRED) is a congestion control algorithm designed specifically for TCP in ad hoc networks. It focuses on achieving fairness among neighboring nodes by controlling the transmission rate based on the observed congestion levels in the local neighborhood.
>
>  NRED works by maintaining a congestion level estimate for each TCP flow within a node's neighborhood. Nodes exchange congestion-related information with their immediate neighbors to obtain a more accurate picture of the network's congestion state. This information can include metrics such as packet loss rates, delay measurements, or buffer occupancy levels.
>
>  Based on the received congestion information, a node adjusts its own TCP transmission rate to alleviate congestion and promote fairness. If a neighboring node is experiencing high congestion, the node reduces its transmission rate to avoid exacerbating the congestion problem. On the other hand, if the congestion level is relatively low, the node can increase its transmission rate to utilize the available network capacity more effectively.
>
>  By considering the congestion levels within its local neighborhood, NRED aims to achieve fairness among neighboring nodes and prevent congestion hotspots. It allows nodes to adapt their TCP transmission rates in a distributed manner based on the observed local congestion conditions.
>
>  NRED is an example of a localized congestion control mechanism that leverages neighborhood information to make congestion-aware decisions. It improves fairness and performance in ad hoc networks by dynamically adjusting the transmission rates of TCP flows based on the observed congestion levels within the neighborhood.
>  
>   Here's the information about ***Continuation-based Path Routing***:
>
>  Continuation-based path routing is a technique used in ad hoc networks to improve fairness and efficiency in routing. It aims to address the issues related to traditional hop-by-hop routing protocols, such as the overhead caused by frequent route discoveries and updates.
>
>  In hop-by-hop routing, each intermediate node in a route makes an individual routing decision based on its local information. This can lead to suboptimal routes, frequent route discoveries, and high control overhead, especially in dynamic and mobile ad hoc networks.
>
>  Continuation-based path routing, on the other hand, takes a different approach. It focuses on establishing routes for multiple hops at once, reducing the need for frequent route discoveries. It introduces the concept of path continuation, where a source node identifies a sequence of intermediate nodes that can be used as a path to the destination. Instead of sending packets on a hop-by-hop basis, the source node encapsulates multiple packets together and forwards them to the first node in the path continuation.
>
>  The intermediate nodes along the path continuation follow the predetermined sequence and forward the packets to the next node until they reach the destination. This approach reduces the control overhead and eliminates the need for individual route discoveries and updates for each hop.
>
>  By establishing longer paths in advance, continuation-based path routing improves the efficiency of packet delivery and reduces the latency caused by frequent route discoveries. It also promotes fairness as each node along the path continuation has an equal opportunity to forward packets, preventing congestion or resource imbalance at specific nodes.
>
>  Continuation-based path routing can be implemented using various protocols and algorithms, such as AODV-CBR (Ad hoc On-Demand Distance Vector with Continuation-Based Routing) or PCR (Path Continuation Routing).
>
>  Overall, continuation-based path routing offers a promising approach to enhance fairness and efficiency in routing for ad hoc networks by reducing control overhead and establishing longer paths in advance.


>***Broadcasting***
>
>  Broadcasting is a communication technique where a source node sends a message to all nodes in the network. In ad hoc networks, broadcasting is often used for tasks like route discovery, information dissemination, or broadcasting emergency alerts. When a node wants to broadcast a message, it sends the message to all of its neighbors, and each receiving node, in turn, rebroadcasts the message to its neighbors until it reaches all nodes in the network. Broadcasting is a simple and effective way to disseminate information to all nodes in an ad hoc network.
>  
>  ***Broadcating types***
>
>  1. Simple Flooding:
     Simple flooding is a basic broadcasting technique where a source node broadcasts a message to all its neighbors, and each receiving node rebroadcasts the message to its own neighbors, resulting in the message being flooded throughout the network. This approach ensures that the message reaches all nodes in the network. However, simple flooding can lead to redundant transmissions, known as the broadcast storm problem, which can cause excessive collisions and consume significant network resources.
>
>  2. Probability-based Methods:
     Probability-based methods aim to reduce the redundant transmissions and collisions associated with simple flooding. Instead of blindly forwarding every received message, each node makes a probabilistic decision to forward the message based on a predefined probability threshold. By setting an appropriate forwarding probability, nodes can control the extent of message propagation. For example, a node may forward a message with a probability of p, meaning it will rebroadcast the message with a probability of p and discard it with a probability of (1-p). This helps to reduce the broadcast storm problem and improve network efficiency.
 >    
 >    **Subtypes**
 >    1. Probabilistic Scheme
 >    2. Counter-Based Scheme
> 
>  3. Area-based Methods:
      Area-based broadcasting methods take into account the spatial information or geographic location of nodes to optimize the broadcasting process. Nodes are divided into different geographical areas or zones. When a node wants to broadcast a message, it initially broadcasts the message within its own zone. Nodes in adjacent zones overhear the message and may selectively rebroadcast it to nodes in their own zones. By restricting the message propagation to specific zones, area-based methods can reduce redundant transmissions and collisions, leading to more efficient broadcasting.
>
>   **Subtypes**
 >    1. Distance-Based Scheme
 >    2. Location-Based Scheme
>
>  4. Neighbor Knowledge Methods:
     Neighbor knowledge methods utilize information about the neighboring nodes to make informed decisions during the broadcasting process. Nodes maintain information about their immediate neighbors, such as their connectivity, transmission range, or channel conditions. Based on this knowledge, nodes selectively forward the message to the most appropriate neighbors, considering factors like the quality of the wireless link or the proximity to the destination. This approach reduces unnecessary transmissions to distant or less reliable neighbors, improving the efficiency and reliability of broadcasting.
 >    
>    **Subtypes**
 >    1. Flooding with Self Pruning
 >    2. Flooding with Self Pruning
 >    3. Dominant Pruning
 >    4. Multipoint Relaying
 >    5. Ad Hoc Broadcast Protocol
 >    6. Connected Dominating Set-Based Broadcast Algorithm
>
>  These broadcasting methods offer different strategies to overcome the challenges associated with simple flooding and improve the efficiency of message dissemination in ad hoc networks. The choice of method depends on the specific requirements, network conditions, and trade-offs between overhead, reliability, and scalability.


> ***Multicasting***
> 
>  Multicasting is a communication technique that enables a source node to send a message to a subset of nodes in the network. Instead of sending the message to all nodes as in broadcasting, the source node specifies a multicast group, and only the nodes belonging to that group receive the message. Multicasting is particularly useful for applications where a message needs to be delivered to a specific group of nodes, such as multimedia streaming or group communication. Efficient multicasting in ad hoc networks requires appropriate multicast routing protocols that determine the optimal paths to deliver the message to the multicast group members while minimizing overhead and ensuring reliability.
>
>   ***Issues in Providing Multicast in a MANET*** - in book
>
>***Multicasting Types***
>
>In multicasting, different approaches can be used to establish efficient communication paths for delivering multicast messages to a specific group of nodes in the network. Here are explanations of tree-based approaches, mesh-based approaches, stateless approaches, and hybrid approaches in multicasting:
>  
>  1. Tree-Based Approaches:
      Tree-based approaches construct a multicast distribution tree rooted at the source node and branching out to the group members. The tree structure ensures that messages are efficiently delivered to all group members without unnecessary duplication. 
.      **Subtypes**
 >     1.  Ad hoc Multicast Routing Protocol Utilizing Increasing Id-Numbers
         2.  Multicast Ad hoc On-Demand Distance Vector Protocol
         3. Lightweight Adaptive Multicast (LAM)
         4.  Location Guided Tree Construction Algorithm for Small Group Multicast
         5. Multicast Zone Routing
         6.  Multicast Optimized Link State Routing
         7.  Other Protocols
>       
>
>  2. Mesh-Based Approaches:
     Mesh-based approaches aim to establish multiple direct communication links between the source node and the group members. Instead of relying on a specific tree structure, mesh-based approaches allow for more flexible and robust multicast communication.  
>
>     ***Subtypes***
 >     1. On-Demand Multicast Routing Protocol
 >     2. Core-Assisted Mesh Protocol
 >     3.  Forwarding Group Multicast Protocol
 >     4. Other Protocols
>
>
>  3. Stateless Approaches:
     Stateless approaches, also known as flooding-based approaches, do not rely on any specific tree or mesh structures. Instead, each multicast-capable node simply broadcasts the multicast message to all of its neighbors. The neighbors, in turn, broadcast the message to their neighbors, and this process continues until all group members receive the message. While simple to implement, stateless approaches can suffer from excessive redundancy and broadcast storms if not carefully controlled.  
       **Subtypes**
 >     1. Differential Destination Multicast
 >     2. DSR Simple Multicast and Broadcast Protocol
>
>  4. Hybrid Approaches:
      Hybrid approaches combine multiple techniques to achieve efficient multicasting. They leverage the advantages of different approaches to optimize the multicast communication. For example, a hybrid approach might use a tree-based structure for the core part of the network, while utilizing mesh-based or stateless approaches for the periphery or specific areas of the network where direct links or flooding are more efficient.  
      **Subtypes**  
 >     1. Ad hoc Multicast Routing Protocol
 >     2. Multicast Core-Extraction Distributed Ad Hoc Routing
 >     3. Mobility-based Hybrid Multicast Routing

> ***Geocasting***
> 
>   Geocasting is a communication technique that targets nodes within a specific geographic region in an ad hoc network. It allows a source node to send a message to a specific geographical area defined by coordinates or a geographic boundary. Geocasting is useful in applications such as location-based services, where messages need to be delivered to nodes within a particular region. Geocasting protocols typically involve the use of geographic routing algorithms that utilize location information to forward the message towards the target region while avoiding nodes outside that region. This helps in conserving network resources and reducing communication overhead.
>   
>   ***Geocasting Types***
> 
>  1. Data-Transmission Oriented Geocasting Protocol:
        Data-transmission oriented geocasting protocols prioritize efficient and reliable delivery of the geocast message to the intended group of nodes within the specified geographical area. These protocols focus on optimizing the data transmission phase rather than explicitly establishing and maintaining specific routes. Some characteristics of data-transmission oriented geocasting protocols include:
>  
  >   - Area-Based Broadcasting: Messages are initially broadcasted to the entire geographical region of interest. Nodes within the region receive the message and selectively rebroadcast it to their neighbors within the same area. This approach ensures that the message reaches all nodes within the specified region.
>
   >  - Message Replication: To enhance reliability, data-transmission oriented protocols may involve message replication. Multiple copies of the geocast message are transmitted to increase the chances of successful delivery to all intended nodes. Replication strategies may take into account factors such as the node density, communication range, or the distance from the source to optimize the replication process.
>
   >  - Forwarding Decision Metrics: Data-transmission oriented protocols often employ metrics or rules to determine which nodes should forward the geocast message. These metrics may consider factors such as the node's location, distance from the source, transmission range, or communication quality. By making informed forwarding decisions, the protocols aim to minimize redundant transmissions and improve message propagation efficiency.
   >  
   >   **Subtypes**
 >       1. Location-Based Multicast
 >       2. Voronoi Diagram Based Geocasting
 >       3. GeoGRID
> 
>  2. Route Creation Oriented Geocasting Protocol:
      Route creation oriented geocasting protocols focus on explicitly establishing routes or paths from the source node to the targeted geographical region. These protocols aim to establish efficient paths that ensure message delivery to the intended group of nodes. Key characteristics of route creation oriented geocasting protocols include:
>  
 >    - Route Discovery: The geocasting protocols initiate a route discovery process to identify a path from the source node to the desired geographical region. This can be achieved using route establishment techniques such as flooding, proactive routing, reactive routing, or hybrid routing. The goal is to establish a route that covers the intended region efficiently.
>  
 >    - Route Maintenance: Once the route is established, the route creation oriented protocols employ mechanisms to maintain the path's integrity and adapt to changing network conditions. This may involve periodic route updates, monitoring link quality, handling node mobility, or handling route failures.
>  
 >    - Destination-Driven Forwarding: Route creation oriented protocols follow a destination-driven forwarding approach. Messages are forwarded along the established path, leading to the targeted geographical region. Intermediate nodes along the path may perform local decision-making to optimize message delivery.
 >
 >    **Subtypes**
 >       1. GeoTORA
 >       2. Mesh-based Geocast Routing Protocol

youtube video to know more about geocasting multicasting and broadcasting - https://www.youtube.com/watch?v=2jK3hNdM0Lk


# Unit3
#unit3 

[Classification of wsn](https://assignmentpoint.com/classification-of-wireless-sensor-networks/)  

> ***Classification of wsn** (acc to book)
>
>  A WSN is deployed primarily to collect sensed data by different WSs and it is critical to see how requently the sensed values are collected. Looking at various ways in which one can employ the network resources, WSNs can be classified on the basis of their mode of operation or functionality, and the type of target applications. Accordingly, we hereby classify WSNs into three types: 
>  • Proactive Networks - The nodes in this network periodically switch on their sensors and transmitters, Sense the environment and transmit the data of interest. Thus, they provide a snapshot of the relevant Parameters at regular intervals and are well suited for applications requiring periodic data monitoring. 
>  • Reactive Networks - In this scheme, the nodes react immediately to sudden and drastic changes in the value of a sensed attribute. As such, these are well suited for time critical applications. 
>  • Hybrid Networks - This is a combination of both proactive and reactive networks where sensor node not only send data periodically, but also respond to sudden changes in attribute values. 
>
>  Once the type of network is decided, protocols that efficiently route data from the SNs to the users have to be designed, perhaps using a suitable MAC protocol to avoid collisions and subsequent energy consumption. Attempts should be made to distribute energy dissipation evenly among all nodes in the network, as it is usually not common to assume the presence of specialized high-energy nodes in the network. In this chapter we cover proactive, reactive and hybrid protocols, while highlighting the fact that the protocols ought to be directly related to application requirements

[Mac in wsn](https://www.geeksforgeeks.org/mac-protocol-used-in-wireless-sensor-networks/)  
[Architecture of wsn](https://www.elprocus.com/architecture-of-wireless-sensor-network-and-applications/)  
[Application of wsn](https://encyclopedia.pub/entry/17294)  

> ***Physical Layer***
> 
>   This layer transfers stream of bits over physical medium. Frequency selection, carrier frequency generation, signal detection, modulation and data encryption are main tasks of this layer. IEEE 802.15.4 is the suggested standard for Wireless sensor network with low cost, low complexity, low power consumption and low range of communication to maximize battery life.
>   
>   The Physical Layer in Wireless Sensor Networks (WSNs) is the lowest layer in the network protocol stack, responsible for the transmission and reception of raw data bits over the physical medium. It handles the physical characteristics of the wireless communication, including the modulation, encoding, and transmission of the signals. Here are some key aspects of the Physical Layer in WSNs:
>
>  1. Modulation and Encoding:
   >  The Physical Layer utilizes modulation techniques to convert digital data into analog signals suitable for wireless transmission. Common modulation schemes used in WSNs include amplitude shift keying (ASK), frequency shift keying (FSK), and phase shift keying (PSK). These schemes encode the digital data into different signal properties, such as amplitude, frequency, or phase, to represent binary 0s and 1s.
>
>  2. Channel Access and Radio Propagation:
     The Physical Layer deals with the challenges of wireless channel access and radio propagation in WSNs. It includes techniques for channel allocation and access control, such as Carrier Sense Multiple Access (CSMA) or Time Division Multiple Access (TDMA). Additionally, the Physical Layer considers radio propagation characteristics, including signal attenuation, path loss, interference, and multipath fading, which affect the reliability and quality of wireless communication.
>
>  3. Transceiver:
     The Physical Layer operates through the transceiver, which is the hardware component responsible for transmitting and receiving radio signals. The transceiver contains a radio frequency (RF) module that performs the modulation, encoding, and decoding of signals. It also handles aspects such as transmission power control, frequency selection, and synchronization.
>
>  4. Antenna Design:
     Antennas play a crucial role in the Physical Layer, as they transmit and receive radio signals. The design of antennas in WSNs is optimized for wireless communication within the desired range and coverage area. Various antenna types, such as omnidirectional antennas for broad coverage or directional antennas for focused transmission, can be used depending on the specific network requirements.
>
>  5. Signal Processing and Error Correction:
     The Physical Layer may involve signal processing techniques to enhance the quality of received signals and mitigate the effects of noise, interference, and fading. Signal processing algorithms, such as filtering, equalization, and error correction codes (e.g., Reed-Solomon or convolutional codes), can be applied to improve the reliability and integrity of data transmission.
>
>  6. Power Management:
     Power efficiency is a critical concern in WSNs due to limited energy resources in sensor nodes. The Physical Layer may incorporate power management techniques, such as adaptive transmission power control or duty cycling, to optimize energy consumption during wireless communication.
>
>  The specific implementation of the Physical Layer in WSNs depends on the chosen wireless technology (e.g., Wi-Fi, Bluetooth, Zigbee) and the specific requirements of the application and network design. Different physical layer standards and protocols may be utilized to address the unique challenges of WSNs, including low power consumption, reliable communication, and efficient use of the wireless medium.


> ***Link layer***
> 
> Data link layer is used for multiplexing of data stream and medium and error control and data frame detection. Communication link between sensor nodes are created by MAC protocol considering power efficiency as most important.
> 
> In Wireless Sensor Networks (WSNs), the Link Layer is responsible for establishing and maintaining communication links between neighboring sensor nodes. It is the layer in the network protocol stack that handles the transmission of data frames over the wireless medium. The Link Layer performs several functions to ensure reliable and efficient data transmission within the network. Here are some key aspects of the Link Layer in WSNs:
>
>  1. Medium Access Control (MAC) Protocol:
     The Link Layer in WSNs incorporates a MAC protocol that determines how sensor nodes access the shared wireless medium. The MAC protocol governs when and how nodes transmit data to avoid collisions and maximize channel utilization. Common MAC protocols used in WSNs include TDMA (Time Division Multiple Access), CSMA (Carrier Sense Multiple Access), and their variations.
>
>  2. Addressing and Framing:
     The Link Layer assigns unique addresses to sensor nodes to identify them within the network. It also defines the frame structure, which encapsulates data from the upper layers for transmission. The frame typically includes fields for addressing, error checking, synchronization, and control information.
>
>  3. Reliable Data Delivery:
     The Link Layer implements mechanisms to ensure reliable data delivery between neighboring nodes. It includes error detection and correction techniques, such as checksums or cyclic redundancy checks (CRC), to detect and correct transmission errors. Additionally, the Link Layer may incorporate acknowledgment mechanisms, such as acknowledgement frames or automatic retransmission, to handle packet loss and ensure reliable data transmission.
>
>  4. Neighbor Discovery and Management:
     The Link Layer facilitates neighbor discovery, where sensor nodes identify and establish communication links with neighboring nodes within their transmission range. Neighbor management mechanisms monitor the presence, availability, and quality of neighboring nodes' links. This information helps in routing decisions and network maintenance.
>
>  5. Power Management:
     Energy efficiency is a critical aspect of WSNs due to limited battery resources in sensor nodes. The Link Layer may incorporate power management techniques to optimize energy consumption, such as duty cycling, sleep-wake cycles, and adaptive transmission power control. These techniques help conserve energy and prolong the network lifetime.
>
>  6. Link Quality Estimation:
     The Link Layer may also include mechanisms to estimate the quality of wireless links between nodes. Link quality estimation techniques measure signal strength, signal-to-noise ratio (SNR), or other metrics to assess the reliability and stability of communication links. This information is valuable for routing decisions and link reliability-aware protocols.
>
>  The specific design and features of the Link Layer in WSNs can vary depending on the network requirements, application scenarios, and protocol specifications. Different protocols and algorithms may be used to address the unique challenges of WSNs, such as limited resources, wireless channel characteristics, and node mobility.


# Unit4
#unit4 

![1.png](./1.png)


![2.png](./2.png)

> ***Flat routing***
> 
> In flat routing based protocols, all nodes play the same role. Here, we present the most prominent protocols falling in this category.


  
### Subtypes of flat routing (Only do limited🤦‍♂️)

> ***Directed Diffusion***
> 
> Directed Diffusion is a data-centric routing protocol designed for Wireless Sensor Networks (WSNs). It was proposed as a way to efficiently disseminate data from multiple sources to a sink or base station in a network. The protocol focuses on the characteristics of the data rather than traditional source-destination communication.
>
>  In Directed Diffusion, the network is organized into a hierarchical structure, with the sink or base station at the top and sensor nodes at lower levels. The sink is the ultimate destination for the collected data, while sensor nodes are responsible for sensing the environment and forwarding the data towards the sink.
>
>  The key concept in Directed Diffusion is the notion of "interest" and "gradient." Interest is expressed by the sink or other nodes in the network to indicate their desire for specific types of data. Gradients represent the paths along which data should flow to reach the interested nodes. These gradients are created based on the communication patterns and data requirements in the network.
>
>  The routing process in Directed Diffusion involves the following steps:
>   
> 1. Interest Discovery: The sink broadcasts an interest packet into the network to express its interest in a particular type of data. This interest packet propagates through the network, and intermediate nodes may also express their interest by generating additional interest packets.
>   
>   2. Gradient Formation: As interest packets propagate, gradients are established between nodes to form paths for data dissemination. Gradients represent the direction and strength of data flow. They are created based on the feedback received from interested nodes and the observed data transmission patterns.
>   
>   3. Data Propagation: Sensor nodes that have collected data relevant to the interests propagate the data towards the sink following the established gradients. Data packets are disseminated along the gradient paths, potentially being aggregated or processed by intermediate nodes before reaching the sink.
>   
>   4. Feedback and Reinforcement: The sink provides feedback to the nodes by sending reinforcement packets or interest adjustments. This feedback helps refine the gradients and optimize the routing paths for efficient data delivery. Nodes can adapt their forwarding behavior based on the reinforcement received.
>   
>   Directed Diffusion offers advantages such as localized data processing, energy efficiency through data aggregation, and robustness in dynamic environments. However, it requires careful tuning of parameters and may have higher initial overhead compared to other routing protocols.
>
>  
>  ![3.png](./3.png)


> ***Sequential Assignment routing***
> 
> ![4.png](./4.png)

> ***The Minimum Cost Forwarding***
> 
> The Minimum Cost Forwarding (MCF) algorithm is a routing algorithm used in Wireless Sensor Networks (WSNs) to determine the path with the minimum cost or energy consumption for forwarding data packets from source nodes to a sink or base station. The primary objective of the MCF algorithm is to optimize energy efficiency and prolong the network lifetime.
>   
>   The MCF algorithm typically operates based on the following principles:
>
>   1. Cost Metric: Each link or path in the network is associated with a cost metric, which represents the energy consumption or cost of transmitting a packet across that link. The cost metric can be determined based on factors such as distance, transmission power, link quality, or residual energy of the nodes.
>   
>   2. Path Selection: When a node needs to forward a data packet to the sink, it selects the path with the minimum cost metric. This can be achieved through techniques like Dijkstra's algorithm or a distributed approach where nodes exchange cost information with their neighbors and collectively make decisions.
>   
>   3. Energy-Aware Forwarding: The MCF algorithm ensures that nodes forward packets through the path with the minimum cost metric, thus reducing energy consumption. By choosing paths that minimize energy expenditure, the network's overall energy efficiency is improved, leading to extended network lifetime.
>   
>   4. Dynamic Adaptation: The MCF algorithm can adapt to changes in the network, such as node failures or variations in link conditions. If a link's cost increases due to deteriorating quality or energy depletion, the algorithm can dynamically select an alternative path with a lower cost to maintain efficient packet forwarding.
>   
>   The MCF algorithm aims to strike a balance between routing packets along low-cost paths and ensuring reliable data delivery to the sink. It considers energy consumption as a critical factor in decision-making, making it suitable for resource-constrained WSNs where energy efficiency is of utmost importance.

> ***Coherent and Non-Coherent Processing***
>   In general, sensor nodes cooperate with each other in processing different data flooded throughout the network. Two examples of data processing techniques are coherent and non-coherent data processing-based routing . 
>   In non-coherent data processing routing, nodes locally process the raw data before being sent to other nodes for further processing. The nodes that perform further processing are called the aggregators.
>    In coherent routing, the data is forwarded to aggregators after minimum processing of time stamping and duplicate suppression. To perform energy-efficient routing, normally coherent processing is selected.
>    Non-coherent functions generate fairly low load. 
>    Coherent processing, however, generates long data streams and as such must achieve energy efficiency by path optimality. 
>    
>    In non-coherent processing, data processing is done three phases: (i) Target detection, data collection, and preprocessing; (ii) Membership declaration; and (iii) Central node election. During phase (i), a target is detected, its data collected and preprocessed. When a node decides to participate in a cooperative function, it enters phase (ii) and declares this intention to all neighbors. This should be done as soon as possible so that each sensor has a local understanding of the network topology. Phase (iii) performs the election of the central node, which must have sufficient energy reserves and computational capability as it is selected to perform more sophisticated information processing.


> ***Energy Aware Routing***
>
>  A destination initiated reactive protocol is proposed in  in order to prolong the network lifetime. This protocol is similar to directed diffusion (discussed earlier) with the difference that it maintains a set of paths instead of maintaining or enforcing one optimal path. These paths are maintained and chosen by means of a certain probability, which depends on how low the energy consumption of each path can be achieved. By selecting different routes at different times, the energy of any single route will not deplete so quickly. With this scheme, the network degrades gracefully as energy is dissipated more equally amongst all nodes. 
>  
>  The protocol initiates a connection through localized flooding, which is used to discover all routes between source/destination pair and their costs; thus building up the routing tables. Next, the highcost paths are discarded and a forwarding table is constructed by choosing neighboring nodes inversely proportional to their cost. Then, data is sent to the destination using the forwarding table with a probability that is inversely proportional to the node cost. Finally, in order to keep the various paths alive, localized flooding is carried out by the destination node.
  
  
![5.png](./5.png)

> ***Subtype of hierarchical routing***
> 
> 1.  Cluster Based Routing Protocol (CBRP)
> 2. Scalable Coordination
> 3. Low-Energy Adaptive Clustering Hierarchy (LEACH)
> 4. Power-Efficient Gathering in Sensor Information Systems (PEGASIS)
> 5. Small Minimum Energy Communication Network (MECN)
> 6. Threshold-Sensitive Energy Efficient (TEEN)
> 7. Adaptive Periodic TEEN (APTEEN)
> 8. Routing in Fixed-Size Clusters
> 9. Sensor Aggregates Routing
> 10. Hierarchical Power-Aware Routing
> 
>  nkli mdu 🤦‍♂️ bs topic copy paste kr die. y apne aap m ek unit h🥲

![6.png](6.png)

>***Adaptive routing***
>
>Adaptive routing in Wireless Sensor Networks (WSNs) refers to the ability of the network to dynamically adjust its routing decisions based on changing network conditions, such as node failures, varying link qualities, or energy constraints. Adaptive routing aims to improve the network's performance, robustness, and energy efficiency by dynamically adapting to the current network state.
>
>  In WSNs, where the topology may change frequently and nodes have limited resources, adaptive routing protocols can play a crucial role. Here are some key aspects and techniques involved in adaptive routing in WSNs:
>  
>  1. Dynamic Route Selection: Adaptive routing protocols continuously monitor the network state and make routing decisions based on real-time information. They can select the most appropriate route based on factors such as link quality, energy levels, traffic load, or latency. This adaptability allows the network to avoid congested or unreliable paths and utilize more favorable routes.
>  
>  2. Distributed Decision-Making: Adaptive routing protocols often distribute the decision-making process across the network nodes. Instead of relying on a centralized controller, individual nodes make routing decisions based on local information and collaborative mechanisms. Distributed decision-making enhances scalability and enables faster adaptation to changing network conditions.
>  
>  3. Reactive and Proactive Approaches: Adaptive routing protocols can be reactive or proactive in nature. Reactive protocols initiate route discovery and maintenance procedures only when needed, typically in response to specific communication requests. Proactive protocols maintain and update routing information periodically, enabling faster route setup when communication requests occur. Hybrid protocols combine reactive and proactive elements to achieve a balance between responsiveness and overhead.
>  
>  4. Feedback and Reinforcement: Adaptive routing protocols often incorporate feedback mechanisms to improve their performance over time. For example, nodes can exchange information about successful or failed transmission attempts, link quality measurements, or energy levels. This feedback helps nodes make informed routing decisions and adapt their behavior based on observed network conditions.
>  
>  5. Quality-of-Service (QoS) Considerations: Adaptive routing in WSNs may also take into account QoS requirements, such as latency, reliability, or data freshness. The routing decisions can be optimized to satisfy specific QoS objectives or trade-offs based on application requirements.
>  
>  Examples of adaptive routing protocols in WSNs include AODV (Ad hoc On-Demand Distance Vector), DSR (Dynamic Source Routing), and RPL (Routing Protocol for Low-Power and Lossy Networks). These protocols employ various techniques to adapt to changing network conditions and optimize routing decisions accordingly.
>
>  The choice of an adaptive routing protocol depends on the specific requirements of the WSN application, network dynamics, and resource constraints. Factors such as energy efficiency, scalability, fault tolerance, and QoS considerations influence the selection of an appropriate adaptive routing protocol for a given WSN deployment.


> ***Protocol operation***
> 
> In this class of routing protocols, the protocol operation determines the classification. Altogether, the protocols in this class can be classified as negotiation-based, multipath-based, query-based and location-based.

### Subtypes of protocol operation

> ***Negotiation-Based Routing***
> 
>  Negotiation-based routing protocols use high level data descriptors in order to eliminate redundant data transmissions. Communication decisions are also made based on the available resources.

> ***Multipath-Based Routing***
> 
>   Network performance, and possibly lifetime, in WSNs can be significantly improved if the routing protocol is able to maintain multiple, instead of a single, paths to a destination, and protocols in this class are called multipath protocols. By employing multipath protocols, the fault tolerance (resilience) of the network is considerably increased. The fault tolerance of a protocol is measured by the likelihood that an alternate path exists between a source and a destination when the primary path fails. Clearly, this can be increased if we maintain multiple paths between the source and the destination at the expense of an increased energy consumption and traffic generation (i.e., overhead), as alternate paths are kept alive by sending periodic messages.


> ***Query-Based Routing***
> 
>   In query-based routing, the destination nodes propagate a query for data (sensing task) from a node throughout the network. A node having the data matching the query sends it back to the node which requested it. Usually, these queries are described in natural language or in high-level query languages.


>***Location-Based Routing*** 
>  
>  In location-based routing, SNs are addressed by means of their locations. Here, the distance between neighboring SNs can be estimated on the basis of incoming signal strengths, and relative coordinates of neighboring SNs can be obtained by exchanging such information. Alternatively, the location of nodes may be available directly through GPS if we consider nodes are equipped with a small low power GPS receiver.


> ***Transport layer***
> 
> In the context of Wireless Sensor Networks (WSNs), the transport layer is responsible for the end-to-end communication between applications running on different nodes within the network. However, due to the resource-constrained nature of WSNs, the traditional transport layer protocols used in wired networks, such as TCP (Transmission Control Protocol) and UDP (User Datagram Protocol), are not directly applicable. Instead, specialized transport layer protocols are often designed specifically for WSNs.
>  
>  The main objectives of the transport layer in WSNs are to ensure reliable and efficient data transfer, manage congestion and flow control, and provide necessary support for the application layer. Here are some key considerations and characteristics of the transport layer in WSNs:
>   
>   1. Energy Efficiency: Energy efficiency is crucial in WSNs, as sensor nodes are typically battery-powered and have limited energy resources. Transport layer protocols for WSNs aim to minimize energy consumption by using efficient communication strategies, such as aggregated data transmission, duty cycling, or sleep scheduling.
>   
>   2. Reliability: Reliable data transfer is essential in WSNs, particularly in applications where data accuracy is critical. However, achieving reliability while conserving energy poses challenges in resource-constrained environments. WSN transport layer protocols employ mechanisms such as error detection, retransmission, and acknowledgment to ensure reliable data delivery while considering energy constraints.
>   
>   3. Scalability: WSNs often consist of a large number of nodes, and the transport layer protocols should be scalable to handle the communication requirements of the network. Protocols should be designed to efficiently manage routing, congestion control, and end-to-end communication in large-scale WSN deployments.
>   
>   4. Congestion Control: Congestion control mechanisms are necessary to prevent network congestion and ensure efficient data transfer in WSNs. Transport layer protocols employ techniques such as hop-by-hop flow control, congestion detection, and avoidance mechanisms to manage traffic and prevent congestion-related issues.
>   
>   5. Quality-of-Service (QoS) Support: Some WSN applications may have specific QoS requirements, such as latency, reliability, or data freshness. Transport layer protocols in WSNs can incorporate QoS mechanisms to meet these requirements and provide differentiated services based on the application needs.
>   
>   Examples of transport layer protocols designed specifically for WSNs include Collection Tree Protocol (CTP), Reliable Transport Protocol (RTP), and Sensor Protocol for Information via Negotiation (SPIN). These protocols address the unique challenges and requirements of WSNs, such as energy efficiency, reliability, and scalability, while providing the necessary communication services to the application layer.
>   
>   It's important to note that the specific design and characteristics of the transport layer in WSNs may vary depending on the application domain, network architecture, and specific requirements of the deployed WSN.



> ***High-level application layer support***
> 
> For specific applications, a higher level of abstraction specifically tailored to WSN appears to be useful. In this section, we outline some of the activities in this direction. 
> 
> **Distributed Query Processing**: The number of messages generated in distributed query processing is several magnitudes less than in centralized scheme. discusses the application of distributed query execution techniques to improve communication efficiency in sensor and device networks. They discuss two approaches for processing sensor queries: warehousing and distributed. In the warehousing approach, data is extracted in a pre-defined manner and stored in a central database (e.g., the BS). Subsequently, query processing takes place on the BS. In the distributed approach, only relevant data is extracted from the sensor network, when and where it is needed. A language similar to the Structured Query Language (SQL) has been proposed for query processing in homogeneous sensor networks.
>  
>  **Sensor Databases**: One can view the wireless sensor network as a comprehensive distributed database and interact with it via database queries. This approach solves, en passant, the entire problem of service definition and interfaces to WSNs by mandating, for example, SQL queries as the interface. The problems encountered here are in finding energyefficiency ways of executing such queries and of defining proper query languages that can express the full richness of WSNs. The TinyDB project carried out at the University of California at Berkeley is looking at these issues. A model for sensor database systems known as COUGAR defines appropriate user and internal representation of queries. The sensor queries are also considered so that it is easier to aggregate the data and to combine two or more queries. In COUGAR, routing of queries is not handled. COUGAR has three-tier architecture. 
>    • The Query Proxy: A small database component running on the sensor nodes to interpret and execute queries 
>    • A Front end Component: A query-proxy that allows the sensor network to connect to the outside world. Each front-end includes a full-fledged database server 
>    • A Graphical User Interface (GUI): Through the GUI, users can pose ad hoc and long running queries on the WSN. A map that allows the user to query by region and visualize the topology of sensors in the network. 
>  
>  **Distributed Algorithms**: WSNs are not only concerned with merely sensing the environment but also with interacting with the environment. Once actuators like valves are added to WSNs, the question of distributed algorithms becomes inevitable. One showcase is the question of distributed consensus, where several actuators have to reach a joint decision (a functionality which is also required for distributed software update, for example). This problem has been investigated to some degree for ad hoc networks, but it has not been fully addressed in the context of WSNs where new scalability and reliability issues emerge and where the integration in the underlying, possibly data-centric routing architecture, has not yet been investigated. 


>  ***Adapting to the Inherent Dynamic Nature of WSNs***
>  
>  Some important goals that current research in this area is aiming to achieve are as follows: 
>    • Exploit spatial diversity and density of sensor/actuator nodes to build an adaptive node sleep schedule 
>    • Spontaneously create and assemble network, dynamically adapt to device failure and degradation, manage mobility of sensor nodes and react to changes in task and sensor requirements 
>    • Adaptability to drastic changes in the traffic • Having finer control over the precision and coverage.

> ***Sensor Networks and mobile robots***
> 
> Sensor networks and mobile robots are two distinct but complementary technologies that are often used together to achieve various applications and tasks. Sensor networks consist of a large number of interconnected sensor nodes that are deployed in a specific area to collect and transmit data. Mobile robots, on the other hand, are autonomous or semi-autonomous devices capable of physical movement and performing tasks in the environment.
>  
>  When combined, sensor networks and mobile robots offer several advantages and enable a range of applications:
>  
>  1. Environmental Monitoring: Sensor networks can be deployed to gather data about environmental conditions such as temperature, humidity, air quality, or presence of pollutants. Mobile robots can be employed to traverse the environment and collect data from specific locations or perform targeted measurements. This combination allows for comprehensive monitoring of large areas and gathering data from inaccessible or hazardous locations.
>  
>  2. Target Localization and Tracking: Mobile robots equipped with sensors can navigate through a sensor network to localize and track specific targets or events. The sensor network provides initial detection or localization information, while the mobile robot can move closer to the target for detailed observations or follow dynamic targets.
>  
>  3. Task Allocation and Collaboration: Sensor networks can provide information about the current state of the environment, and mobile robots can utilize this information to allocate tasks efficiently. Mobile robots can be assigned specific objectives based on the data collected by the sensor network, optimizing resource utilization and collaboration between the robots.
>  
>  4. Data Fusion and Processing: Sensor networks generate vast amounts of data, and mobile robots can assist in data fusion and processing tasks. Mobile robots can move to specific locations to collect sensor data, perform local computations, and transmit aggregated or processed data back to the base station. This approach reduces the amount of data transmitted wirelessly and can save energy in resource-constrained sensor networks.
>  
>  5. Maintenance and Repair: Mobile robots can be deployed to inspect, maintain, or repair the sensor nodes in the network. They can identify malfunctioning nodes, replace batteries, or perform physical repairs, ensuring the longevity and reliability of the sensor network.
>  
>  6. Surveillance and Security: Mobile robots can be integrated with sensor networks to enhance surveillance and security applications. They can navigate the environment, detect anomalies or intrusions using sensor data, and respond accordingly, providing an active surveillance capability.
>
>  Overall, the combination of sensor networks and mobile robots provides a powerful platform for data collection, environmental monitoring, task execution, and collaborative decision-making. It enables the integration of sensing, actuation, and mobility, leading to more efficient and effective applications in various domains such as agriculture, environmental monitoring, disaster response, and industrial automation.


> ***Security in Ad Hoc Networks***
> 
>   Security in Ad Hoc Networks As we know, there is no fixed infrastructure in ad hoc networks and as the name implies they are formed on the fly. The devices connect to each other in their own communication range via wireless links. Individual devices act as routers when relaying messages to other distant devices. The topology of an ad hoc network is not fixed either. It changes all the time when these mobile stations move in and out of each others transmission range. All this makes ad hoc networks very vulnerable to attacks and the security issues become very complex. In this section we give an overview of the security issues over ad hoc and sensor networks. 
> 
>   **REQUIREMENTS**
>  
>   The security services of ad hoc networks are not altogether different than those of other network communication paradigms. Below we describe the requirements ad hoc networks must meet
>
>    1. **Availability**: Availability ensures that the desired network services are available whenever they are needed. Systems that ensure availability seek to combat denial of service (DoS) and energy starvation attacks. In ad hoc networks, ensuring availability is perhaps more important than it is in traditional Internet. As all the devices in the network depend on each other to relay messages, DoS attacks are easy to perpetrate. For example, a malicious user could try to jam or otherwise try to interfere with the flow of information. Or else, the routing protocol should be able to malicious users by feeding the network with accurate information. There are routing protocols that can adjust well to the changing topology, but there are none that can defy all the possible attacks. Another vulnerable point, which has no equivalence in traditional networks, is the limited battery power of wireless nodes. Normally, these nodes try to save energy with power saving schemes, so that when the device is not in active use, energy is not consumed. With battery exhaustion attacks, a malicious user can cause higher power consumption from other devices' battery, causing these devices to die prematurely.
>    
>    2. **Authorization and key management**: Authorization is another difficult matter in ad hoc      networks. As there is little or no infrastructure, identifying users (e.g., participants in a meeting room) is not an easy task. There are problems with rusted third party schemes and identity-based mechanisms for key agreement. A generic protocol for password authenticated key exchange is described. It has several drawbacks even though it is possible to construct very good authentication mechanisms for ad hoc networks. A password uthenticated multi-party Diffie - Hellman key exchange seems to overcome many problems of the generic protocol. 
>
>   3. **Confidentiality and Integrity Data**: confidentiality is a core security primitive for ad hoc networks. It ensures that the message cannot be understood by anyone other than the authorized personnel. With wireless communication, anyone can sniff the messages going through the air, and without proper encryption all the information is easily available. On the other hand, without proper authentication, it is difficult to enforce confidentiality. And if the proper authenticity has been established, securing the connection with appropriate keys does not pose a big problem. Data integrity denotes the immaculateness of data sent from one node to another. That is, it ensures that a message sent from node A to node B was not modified during transmission by a malicious node C. If a robust confidentiality mechanism is employed, ensuring data integrity may be as simple as adding one-way hashes to encrypted messages
>   
>   4.  **Non-Repudiation**: Non-repudiation ensures that the origin of a message cannot deny having sent the message. It is useful for detection and isolation of compromised nodes. When a node A receives an erroneous message from a node B, non-repudiation allows A to accuse B using this message and to convince other nodes that B is compromised.
>   
>   5. **Security Solutions Constraints**: Historically, network security personnel have adopted a centralized, largely protective paradigm to satisfy aforementioned requirements. This is effective because the privileges of every node in the network are managed by dedicated machines - authentication servers, firewalls, etc. - and the professionals who maintain them. Membership in such a network allows individual nodes to operate in an open fashion - sharing sensitive files, allowing incoming network connections - because it is implicitly guaranteed that any malicious user from outside world will not be allowed access. Although these solutions have been considered very early in the evolution of ad hoc networks, attempts to adapt similar client-server solutions to a decentralized environment have largely been ineffective. To be efficiently applicable, security solutions for ad hoc networks should ideally have the following characteristics: 
>   
>    • Lightweight: Solutions should minimize the amount of computation and communication required to ensure the security services to accommodate the limited energy and computational resources of mobile, ad hocenabled devices; 
>     
>    • Decentralized: Like ad hoc networks themselves, attempts to secure them must be ad hoc: they must establish security without reference to centralized, persistent entities. Instead, security paradigms should levy the cooperation of all trustworthy nodes in the network; 
>     
>    • Reactive: Ad hoc networks are dynamic. Nodes - trustworthy and malicious - may enter and leave the network spontaneously and unannounced. Security paradigms must react to changes in network state; they must seek to detect compromises and vulnerabilities. Therefore, these solutions should be reactive; 
>     
>    • Fault-Tolerant: Wireless mediums are known to be unreliable; nodes are likely to leave or be compromised without warning. The communication requirements of security solutions should be designed with such faults in mind; they should not rely on message delivery or ordering. 
>     
>   Naturally, these are not stringent requirements: specific applications may relax some or all of the above based on their domain and the sensitivity of the information involved. Moreover, many ad hoc network applications do not require 2-party secure communication; instead, achieving broadcast or group security may be all that is needed. 

> ***Key Management*** 
> 
> Public key systems are generally recognized to have an upper hand in key distribution. In a public key infrastructure, each node has a public/private key pair. A node distributes its public key freely to the other nodes in the network; however it keeps its private key to only itself. A CA is used for key management and has its own public/private key pair. The CA's public key is known to every network node. The trusted CA is responsible to sign certificates, binding public keys to nodes, and has to stay online to verify the current bindings. The public key of a node should be revoked if this node is no longer trusted or leaves the network. A single key management service for an ad hoc network is probably not an acceptable solution, as it is likely to become Achilles' heel of the network. If the CA is unavailable, nodes cannot get the current public keys of other nodes to establish secure connections. In addition, if a CA is compromised, the attacker can sign erroneous certificates using the database of the private keys. Naive replication of CAs can make the network more vulnerable, since compromising of any single replica can cause the system to fail. Hence, it may be more prudent to distribute the trust to a set of nodes by letting these nodes share the key management responsibility.
> ***
> // can expand more


> ***Secure routing***
> 
> The contemporary routing protocols designed for ad hoc networks (discussed in Chapter 2) cope well with dynamically changing topology, but are not designed to provide defense against malicious attackers. In these networks, nodes exchange network topology in order to establish routes between them, and are another potential target for malicious attackers who intend to bring down the network. As for attackers, we can classify them into external and internal. External attackers may inject erroneous routing information, replay old routing data or distort routing information in order to partition or overload the network with retransmissions and inefficient routing. Compromised nodes inside the network are harder to detect and are far more detrimental. Routing information signed by each node may not work, as compromised nodes can generate valid signatures using their private keys. Isolating compromised nodes through routing information is also difficult due to the dynamic topology. Solutions must overcome these potential problems and use some properties of ad hoc networks to facilitate secure routing. Once the compromised nodes have been identified, if there is sufficient number of possibly disjoint and valid routes, the routing protocol should be able to bypass the compromised nodes by using alternate routes.
>  ***
> // can expand more



>***Cooperation in MANETs***
>   As opposed to networks using dedicated nodes to support basic networking functions such as packet forwarding and routing, in ad hoc networks these functions are carried out by all available network nodes. There is no reason, however, to assume that the nodes in the network will eventually cooperate with one another since network operation consumes energy, a particularly scarce resource in a battery powered environment like MANETs. 
>   
>   The new type of node misbehavior that is specific to ad hoc networks is caused by the lack of cooperation and goes under the name of node selfishness . A selfish node does not directly intend to damage other nodes with active attacks (mainly because performing active attacks can be very expensive in terms of energy consumption) but it simply does not cooperate to the network operation, saving battery life for its own communications.
>   
>   Damages provoked by selfish behavior can not be underestimated: a simulation study presented shows the impact of a selfish behavior in terms of global network throughput and global communication delay when the DSR routing protocol is used. The simulation results show that even a small percentage of selfish nodes present in the network leads to severe performance degradation. Furthermore, any security mechanism that tries to enforce cooperation among the nodes ought to focus not only on one particular function, but on both the routing and the packet forwarding function. 
>   
>   Schemes that enforce node cooperation in a MANET can be divided in two categories: the first is currency based and the second uses a local monitoring technique. The currency based systems are simple to implement but rely on a tamperproof hardware. The main drawback of this approach lies in establishing how the virtual currency has to be exchanged, making their use not realistic in a practical system. On the other hand, cooperative security schemes based on local monitoring of neighbors by each node, evaluating a metric that reflects nodes' behavior. Based on that metric, a selfish node can be gradually isolated from the network. 
>   
>   The main drawback of the second approach is related to the absence of a well-accepted mechanism that securely identifies the nodes of the network: any selfish node could elude the cooperation enforcement mechanism and get rid of its bad reputation just by changing its identity. 
>   
>   The main research efforts addressing node selfishness problem are presented as follows.
>   
   > **The CONFIDANT**: (Cooperation Of Nodes, Fairness In Dynamic Ad hoc NeT works) cooperation mechanism  detects malicious nodes by means of observation or reports about several types of attacks, thus allowing nodes to route around misbehaved nodes and thereby isolate them. CONFIDANT works as an extension to a routing protocol such as DSR. Here, nodes are provided with:  
   > • A monitor for observations; Reputation records for first-hand and trusted second-hand observations about routing and forwarding behavior of other nodes;  
    >• Trust records to control trust given to received warnings;  
    >• A path manager to adapt their behavior according to reputation and to take action against malicious nodes.  
>
>    The dynamic behavior of CONFIDANT is as follows.  
    Nodes monitor their neighbors and change the reputation accordingly. If they have some reason to believe that a node is misbehaving, they can take action in terms of their own routing and forwarding and they can decide to inform other nodes by sending an ALARM message. When a node receives such an ALARM either directly or by promiscuously listening to the network, it evaluates how trustworthy the ALARM is based on the source of the ALARM and the accumulated ALARM messages about the node in question. It can then decide whether to take action against the misbehaved node in the form of excluding routes containing the misbehaved node, re-ranking paths in the path cache, reciprocating by non-cooperation, and forwarding an ALARM about the node. Simulations with nodes that do not participate in the forwarding function have shown that CONFIDANT can cope well, even if half of the network population acts maliciously. 
    Further simulations on the effect of second-hand information and slander have shown that slander can effectively be prevented while still retaining a significant detection speed-up over using merely first-hand information. The limitations of CONFIDANT lie in the assertion that the reputation is based on the detection. Events have to be observable and classifiable for detection, and reputation can only be meaningful if the identity of each node is persistent; otherwise it is vulnerable to spoofing attacks. 
>   
> **Token-Based**: Token-Based In an approach presented, each node of the ad hoc network has a token in order to participate in the network operations, and its local neighbors collaboratively monitor to detect any misbehavior in routing or packet forwarding services. Upon expiration of the token, each node renews its token via its multiple neighbors: the period of validity of a node's token is dependent on how long it has stayed and behaved well in the network. A well-behaving node accumulates its credit and renews its token less frequently as time evolves. 
> 
> The security solution is composed of four closely connected components: 
> • Neighbor verification: describes how to verify whether each node in the network is a legitimate or malicious node; 
> • Neighbor monitoring: describes how to monitor the behavior of each node in the network and detect occasional attacks from malicious nodes; 
> • Intrusion reaction: describes how to alert the network and isolate the attackers; 
> • Security enhanced routing protocol: explicitly incorporates the security information collected by other components into the ad hoc routing protocol. 
> In the token issuing/renewal phase, it is assumed a global secret key (SK)/public key (PK) pair, where PK is well known by every node of the network. SK is shared by k neighbors who collaboratively sign the token requested or renewed by local nodes. On the other hand, token verification follows three steps: 
> 1) Identity match between the nodes's ID and the token ID, 
> 2) Validity time verification, 
> 3) Issuer signature. If the token verification phase fails, the corresponding node is rejected from the network and both routing and data packets are dropped for that node. Routing security relies on the redundancy of routing information rather than cryptographic techniques enforced by suitably modifying the AODV protocol and the Watchdog technique described earlier. However, the proposed solution possesses some drawbacks. The bootstrap phase needed to generate a valid collection of partial tokens, which are used by a node to create its final token, has some limitations. 
> 
> For example, the number of neighbors necessary to complete the signature of every partial token has to be at least k, suggesting the use of such security mechanism in rather large and dense ad hoc networks. On the other side, the validity period of a token increases proportionally to the time during which the node behaves 63 well, and this feature has less impact if node mobility is high. Frequent changes in the local subset of the network nodes who share a key for issuing valid tokens can cause high computational overhead, not to mention the high traffic generated by issuing/renewing a token, suggesting that the token-based mechanism is more suitable in ad hoc networks where node mobility is low. Spoofing attacks, where a node can request more than one token based on different identities, are not taken into account.


> ***ids***
>    Each MH in an ad hoc network is an autonomous unit and is free to move independently. This implies that a node without adequate physical protection is susceptible to being captured or compromised. It is difficult to track down a single compromised node in a large network. Hence, every node in a wireless ad hoc network should be able to work in a mode wherein it trusts no peer. While intrusion prevention techniques such as encryption and authentication can reduce the risks of intrusion, they cannot be completely eliminated. Intrusion detection can be used as a second line of defense to protect network systems, because once an intrusion is detected, appropriate action can be put in place to minimize the damage, launch counter offensive measures, or even gather evidence for possible follow up prosecution. 
>    
>    **Authentication**: Authentication denotes the accurate, absolute identification of users who wish to participate in the network. Historically, authentication has been accomplished by a well-known central authentication server. The role of the server is to maintain a database of entities, or users, and their corresponding unique IDs. The ID may be a digital certificate, public key, or both. Unfortunately the ad hoc paradigm does not accommodate a centralized entity creating protocol deployment issues. 
>    
>    **Trusted Third Parties**: One of the most rudimentary approaches to authentication in ad hoc networks uses a Trusted Third Party (TTP). Every node that wishes to participate in an ad hoc network obtains a certificate from a universally trusted third party. When two nodes wish to communicate, they first check to see if the other node has a valid certificate. Although popular, the TTP approach is laden with flaws. Foremost, it probably is not reasonable to require all ad hoc network-enabled devices to have a certificate. Secondly, each node needs to have a unique name. Although this is reasonable in a large internet, it is a bit too restrictive in an ad hoc setting. Recent research has introduced many appropriate variations of TTPs, and these are discussed later.

[More about ids](https://www.geeksforgeeks.org/intrusion-detection-system-ids/)  

> ***Sensor network hardware***
> 
>   Sensor node hardware can be grouped into three categories, each of which entails a different trade-offs in the design choices. 
>   
>   ***AUGMENTED GENERAL-PURPOSE COMPUTERS** : Examples include low-power PCs, embedded PCs (e.g. PC104), custom-designed PCs, (e.g. Sensoria WINS NG nodes), and various personal digital assistants (PDA). These nodes typically run –ff-the-shelf operating systems such as WinCE, Linux, or real-time operating systems and use standard wireless communication protocols such as IEEE 802.11, Bluetooth, Zigbee etc. Because of their relatively higher processing capability, they can accommodate wide variety of sensors, ranging from simple microphones to more sophisticated video cameras. 
>   
>   **DEDICATED EMBEDDED SENSOR NODES** : Examples include the Berkeley mote family [1], the UCLA Medusa family [2], Ember nodes and MIT AMP [3]. These platforms typically use commercial off-the-shelf (COTS) chip sets with emphasis on small form factor, low power processing and communication, and simple sensor interfaces. Because of their COTS CPU, these platforms typically support at least one programming language, such as C. However, in order to keep the program footprint small to accommodate their small memory size, programmers of these platforms are given full access to hardware but rarely any operating system support. A classical example is the TinyOS platform and its companion programming language, nesC. 
>   
>   ***SYSTEM ON-CHIP (SOC) NODES*** : Examples of SoC hardware include smart dust [4], the BWRC picoradio node [5], and the PASTA node [6]. Designers of these platforms try to push the hardware limits by fundamentally rethinking the hardware architecture trade-offs for a sensor node at the chip design level. The goal is to find new ways of integrating CMOS, MEMS, and RF technologies to build extremely low power and small footprint sensor nodes that still provide certain sensing, computation, and communication capabilities. Among these hardware platforms, the Berkeley motes, due to their small form factor, open source software development, and commercial availability, have gained wide popularity in the sensor network research.

> ***Mica Mote***
> 
>   The MICA mote is a popular type of sensor node used in wireless sensor networks (WSNs). It was developed at the University of California, Berkeley, and is widely recognized for its small form factor, low power consumption, and flexibility. Here are some key features and characteristics of the MICA mote:
>  
>  1. Hardware: The MICA mote consists of a compact PCB (Printed Circuit Board) with integrated components, including a microcontroller, memory, radio transceiver, sensors, and power management circuitry. The original MICA mote used an 8-bit Atmel AVR microcontroller, but subsequent versions incorporated more powerful processors.
>  
>  2. Communication: The MICA mote supports wireless communication through an onboard radio transceiver. The original MICA mote used an IEEE 802.15.4 radio for low-power and low-data-rate communication. Later versions of the mote introduced support for different wireless protocols, such as Zigbee.
>  
>  3. Sensors: The MICA mote can be equipped with various sensors depending on the application requirements. Some commonly used sensors include temperature, humidity, light, and accelerometers. The modular design of the MICA mote allows for easy integration of additional or customized sensors.
>  
>  4. Power Management: The MICA mote is designed to operate with limited power resources. It includes power management circuitry to maximize energy efficiency and extend the node's battery life. Techniques such as duty cycling and sleep modes are employed to conserve energy.
>  
>  5. Programming and Software: The MICA mote supports programmability, allowing developers to write custom software for the node. It provides a development environment and programming tools that enable firmware development and deployment. The software can be developed using programming languages such as C or TinyOS, a popular operating system for WSNs.
>  
>  6. Expansion and Modularity: The MICA mote features expansion ports or connectors that enable the integration of additional hardware modules or sensors. This allows for customization and flexibility in adapting the mote to specific application needs.
>  
>  The MICA mote has been widely used in research and practical applications of wireless sensor networks. Its small size, low power consumption, and modular design make it suitable for various deployments, ranging from environmental monitoring to industrial automation and healthcare.



> ***Sensor Network Programming Challenges***
> 
> Sensor network programming presents several challenges due to the unique characteristics and constraints of sensor networks. Here are some common challenges faced when programming sensor networks:
>  
>  1. Limited Resources: Sensor nodes typically have limited computational power, memory, energy, and communication bandwidth. Programming for sensor networks requires careful resource management and optimization to ensure efficient utilization of these constrained resources.
>  
>  2. Energy Efficiency: Energy conservation is critical in sensor networks as nodes are often battery-powered and may be deployed in remote or inaccessible locations. Programmers need to employ energy-efficient algorithms, scheduling techniques, and sleep/wake strategies to maximize the network's lifetime.
>  
>  3. Scalability: Sensor networks can consist of a large number of nodes, making scalability a significant challenge. Programming must account for the potential increase in the network size and ensure that the application can handle the communication and data processing requirements of a large-scale deployment.
>  
>  4. Dynamic Network Topology: Sensor networks may have a dynamic topology due to node failures, mobility, or changing environmental conditions. Programmers need to develop routing and data dissemination protocols that can adapt to these changes and maintain reliable communication in the face of network dynamics.
>  
>  5. Data Aggregation and Fusion: Sensor networks generate a vast amount of data, and transmitting all raw data can be inefficient and wasteful. Programming techniques for data aggregation and fusion are required to reduce data redundancy, filter noise, and extract meaningful information before transmission.
>  
>  6. Heterogeneity: Sensor nodes in a network may have different capabilities, such as varying sensing modalities, processing power, or communication ranges. Developing programming techniques that accommodate this heterogeneity and enable cooperation and collaboration among nodes is a challenge.
>  
>  7. Fault Tolerance: Sensor networks are susceptible to node failures, communication disruptions, and environmental challenges. Programming for fault tolerance involves designing algorithms and protocols that can detect and handle node failures, recover from communication disruptions, and maintain data integrity and reliability.
>  
>  8. Security and Privacy: Sensor networks often handle sensitive data, and ensuring security and privacy is crucial. Programming must include mechanisms for secure data transmission, authentication, access control, and encryption to protect data and preserve user privacy.
>  
>  9. Real-Time Constraints: Some applications in sensor networks require real-time data processing and response. Programming for real-time constraints involves meeting specific timing requirements, minimizing latency, and ensuring timely delivery of critical information.
>  
>  10. Programming Abstraction and Tools: Developing programming abstractions and tools that simplify the programming process and hide low-level details of the underlying hardware and protocols is important. This can enhance programmer productivity and allow for rapid development and deployment of sensor network applications.
>  
>  Addressing these challenges requires a combination of efficient algorithms, distributed protocols, energy-aware programming techniques, and careful consideration of the specific application requirements and constraints of the sensor network.

> ***NODE-LEVEL SOFTWARE PLATFORMS*** 
> 
> Most design methodologies for sensor network software are node-centric, where programmers think in terms of how a node should behave in the environment. A node- level platform can be node-centric operating system, which provides hardware and networking abstractions of a sensor node to programmers, or it can be a language platform, which provides a library of components to programmers.
> 
>  A typical operating system abstracts the hardware platform by providing a set of services for applications, including file management, memory allocation, task scheduling, peripheral device drivers, and networking. For embedded systems, due to their highly specialized applications and limited resources, their operating systems make different trade- offs when providing these services. 
 >  
   >For example, if there is no file management requirement, then a file system is obviously not needed. If there is no dynamic memory allocation, then memory management can be simplified. If prioritization among tasks is critical, then a more elaborate priority scheduling mechanism may be added.
   
>   ***Operating System: TinyOS*** 
>   
>   Tiny OS aims at supporting sensor network applications on resource-constrained hardware platforms, such as the Berkeley motes. To ensure that an application code has an extremely small foot-print, TinyOS chooses to have no file system, supports only static memory allocation, implements a simple task model, and provides minimal device and networking abstractions. Furthermore, it takes a language-based application development approach so that only the necessary parts of the operating system are compiled with the application. 
>   
>   To a certain extent, each TinyOS application is built into the operating system. Like many operating systems, TinyOS organizes components into layers. Intuitively, the lower a layer is, the „closer‟ it is to the hardware; the higher a layer is, the closer it is to the application. In addition to the layers, TinyOS has a unique component architecture and provides as a library a set of system software components. A components specification is independent of the components implementation. Although most components encapsulate software functionalities, some are just thin wrappers around hardware. 
>   
>   An application, typically developed in the nesC language, wires these components together with other application-specific components. A program executed in TinyOS has two contexts, tasks and events, which provide two sources of concurrency. Tasks are created (also called posted) by components to a task scheduler. The default implementation of the TinyOS scheduler maintains a task queue and invokes tasks according to the order in which they were posted. Thus tasks are deferred computation mechanisms. Tasks always run to completion without preempting or being preempted by other tasks. Thus tasks are non-preemptive. 
>   
>   The scheduler invokes a new task from the task queue only when the current task has completed. When no tasks are available in the task queue, the scheduler puts the CPU into the sleep mode to save energy. The ultimate sources of triggered execution are events from hardware: clock, digital inputs, or other kinds of interrupts. The execution of an interrupt handler is called an event context. The processing of events also runs to completion, but it preempts tasks and can be preempted by other events. Because there is no preemption mechanism among tasks and because events always preempt tasks, programmers are required to chop their code, especially the code in the event contexts, into small execution pieces, so that it will not block other tasks for too long.
>   
>    Another trade-off between non-preemptive task execution and program reactiveness is the design of split-phase operations in TinyOS. Similar to the notion of asynchronous method calls in distributed computing, a split-phase operation separates the initiation of a method call from the return of the call. A call to split-phase operation returns immediately, without actually performing the body of the operation. The true execution of the operation is scheduled later; when the execution of the body finishes, the operation notifies the original caller through a separate method call. 
>    
>    In summary, many design decisions in TinyOS are made to ensure that it is extremely lightweight. Using a component architecture that contains all variables inside the components and disallowing dynamic memory allocation reduces the memory management overhead and makes the data memory usage statically 67 analyzable. The simple concurrency model allows high concurrency with low thread maintenance overhead. However, the advantage of being lightweight is not without cost. 
>    
>    Many hardware idiosyncrasies and complexities of concurrency management are left for the application programmers to handle. Several tools have been developed to give programmers language-level support for improving programming productivity and code robustness.


>   ***IMPERATIVE LANGUAGE: NESC*** 
>   
>   NesC [9] is an extension of C to support and reflect the design of TinyOS. It provides a set of language constructs and restrictions to implement TinyOS components and applications. A component in nesC has an interface specification and an implementation. To reflect the layered structure of TinyOS, interfaces of a nesC component are classified as provides or uses interfaces. A provides interface is a set of method calls exposed to the upper layers, while a uses interface is a set of method calls hiding the lower layer components. Methods in the interfaces can be grouped and named. Although they have the same method call semantics, nesC distinguishes the directions of the interface calls between layers as event calls and command calls. An event call is a method call from a lower layer component to a higher layer component, while a command is the opposite. 
>   
>   The separation of interface type definitions from how they are used in the components promotes the reusability of standard interfaces. A component can provide and use the same interface type, so that it can act as a filter interposed between a client and a service. A component may even use or provide the same interface multiple times. 
>   
>   **COMPONENT IMPLEMENTATION**:  There are two types of components in nesC, depending on how they are implemented: modules and configurations. Modules are implemented by application code (written in a C-like syntax). Configurations are implemented by connecting interfaces of existing components. nesC also supports the creation of several instances of a component by declaring abstract components with optional parameters. 
>   
>   **Abstract components**:Abstract components are created at compile time in configuration.  As TinyOS does not support dynamic memory allocation, all components are statically constructed at compile time. A complete application is always a configuration rather than a module. An application must contain the main module, which links the code to the scheduler at run time. The main has single StdControl interface, which is the ultimate source of initialization of all components


>   ***DATAFLOW-STYLE LANGUAGE: TINYGALS***
>   
>    Dataflow languages are intuitive for expressing computation on interrelated data units by specifying data dependencies among them. A dataflow diagram has a set of processing units called actors. Actors have ports to receive and produce data, and the directional connections among ports are FIFO queues that mediate the flow of data. Actors in dataflow languages intrinsically capture concurrency in a system, and the FIFO queues give a structured way of decoupling their executions. 
>    
>    The execution of an actor is triggered when there are enough input data at the input ports. Asynchronous event-driven execution can be viewed as a special case of dataflow models, where each actor is triggered by every incoming event. The globally asynchronous and locally synchronous (GALS) mechanism is a way of building event- triggered concurrent execution from thread-unsafe components. TinyGALS is such as language for TinyOS. 
>    
>    One of the key factors that affect component reusability in embedded software is the component composability, especially concurrent composability. In general, when developing a component, a programmer may not anticipate all possible scenarios in which the component may be used. Implementing all access to variables as atomic blocks, incurs too much overhead. At the other extreme, making all variable access unprotected is easy for coding but certainly introduces bugs in concurrent composition. TinyGALS addresses concurrency concerns at the system level, rather than at component level as in nesC. Reactions to concurrent events are managed by a dataflow-style FIFO queue communication. 
>    
>    **TINYGALS PROGRAMMING MODEL** : TinyGALS supports all TinyOS components, including its interfaces and module implementations. All method calls in a component interface are synchronous method calls- that is, the thread of control enters immediately into the callee component from the caller component. 
>    
>    An application in TinyGALS is built in two steps: 
  >   1. constructing asynchronous actors from synchronous components, and 
  >   2. constructing an application by connecting the asynchronous components through FIFO queues. An actor in TinyGALS has a set of input ports, a set of output ports, and a set of connected TinyOS components. 
  >   a. An actor is constructed by connecting synchronous method calls among TinyOS components. 
  >   b. At the application level, the asynchronous communication of actors is mediated using FIFO queues. Each connection can be parameterized by a queue size. 
  >   c. In the current implementation of TinyGALS, events are discarded when the queue is full. 
  >   However, other mechanisms such as discarding the oldest event can be used
  
> ***NODE-LEVEL SIMULATORS:***
> 
>   Node-level design methodologies are usually associated with simulators that simulate the behavior of a sensor network on a per-node basis. Using simulation, designers can quickly study the performance (in terms of timing, power, bandwidth, and scalability) of potential algorithms without implementing them on actual hardware and dealing with the vagaries of actual physical phenomena. A node-level simulator typically has the following components:
>
>   **SENSOR NODE MODEL** : A node in a simulator acts as a software execution platform, a sensor host, as well as a communication terminal. In order for designers to focus on the application-level code, a node model typically provides or simulates a communication protocol stack, sensor behaviors (e.g., sensing noise), and operating system services. If the nodes are mobile, then the positions and motion properties of the nodes need to be modeled. If energy characteristics are part of the design considerations, then the power consumption of the nodes needs to be modeled.
>
>   **COMMUNICATION MODEL** : Depending on the details of modeling, communication may be captured at different layers. The most elaborate simulators model the communication media at the physical layer, simulating the RF propagation delay and collision of simultaneous transmissions. Alternately, the communication may be simulated at the MAC layer or network layer, using, for example, stochastic processes to represent low-level behaviors.
>   
>   **PHYSICAL ENVIRONMENT MODEL** : A key element of the environment within a sensor network operates is the physical phenomenon of interest. The environment can also be simulated at various levels of details. For example, a moving object in the physical world may be abstracted into a point signal source. The motion of the point signal source may be modeled by differential equations or interpolated from a trajectory profile. If the sensor network is passive- that is, it does not impact the behavior of the environment-then the environment can be simulated separately or can even be stored in data files for sensor nodes to read in. If, in addition to sensing, the network also performs actions that influence the behavior of the environment, then a more tightly integrated simulation mechanism is required.
>   
>   **STATISTICS AND VISUALIZATION** : The simulation results need to be collected for analysis. Since the goal of a simulation is typically to derive global properties from the execution of individual nodes, visualizing global behaviors is extremely important. An ideal visualization tool should allow users to easily observe on demand the spatial distribution and mobility of the nodes, the connectivity among nodes, link qualities, end- toend communication routes and delays, phenomena and their spatio-temporal dynamics, sensor readings on each node, sensor nodes states, and node lifetime parameters (e.g., battery power). A sensor network simulator simulates the behavior of a subset of the sensor nodes with respect to time.
>
>   Depending on how the time is advanced in the simulation, there are two types of execution models: cycle-driven simulation and discrete-event simulation. A cycle-driven (CD) simulation discretizes the continuous notion of real time into (typically regularly spaced) ticks and simulates the system behavior at these ticks. At each tick, the physical phenomena are first simulated, and then all nodes are checked to see if they have anything to sense, process, or communicate. Sensing and computation are assumed to be finished before the next tick. Sending a packet is also assumed to be completed by then.
>   However, the packet will not be available for the destination node until next tick. This split-phase communication is a key mechanism to reduce cyclic dependencies that may occur in cycle-driven simulations. Most CD simulators do not allow interdependencies within a single tick
>   Unlike cycle-driven simulators, a discrete-vent (DE) simulator assumes that the time is continuous and an event may occur at any time. As event is 2-tuple with a value and a time stamp indicating when the event is supposed to be handled. Components in a DE simulation react to input events and produce output events. In node-level simulators, a component can be a sensor node, and the events can be communication packets; or a component can be software module within and the events can be message passings among these nodes. Typically, components are causal, in the sense that if an output event is computed from an input event, then the time stamp of the output should not be earlier than that of the input event. Non-causal components require the simulators to be able to roll back in time, and worse, they may not define a deterministic behavior of a system.
>
>   A DE simulator typically requires a global event queue. All events passing between nodes or modules are put in the event queue and sorted according to their chronological order. At each iteration of the simulation, the simulator removes the first event (the one with earliest time stamp) from the queue and triggers the component that reacts to that event. In terms of timing behavior, a DE simulator is more accurate than a CD simulator, and as a consequence, DE simulators run slower. The overhead of ordering all events and computation, in addition to the values and time stamps of events, usually dominates the computation time. At an early stage of a design when only the asymptotic behaviors rather than timing properties are of concern, CD simulations usually require less complex components and give faster simulations. This is partly because of the approximate timing behaviors, which make simulation results less comparable from application to application, there is no general CD simulator that fits all sensor network simulation tasks. Many of the simulators are developed for particular applications and exploit application-specific assumptions to gain efficiency
>   
>   DE simulations are sometimes considered as good as actual implementations, because of their continuous notion of time and discrete notion of events. There are several open- source or commercial simulators available. One class of these simulators comprises extensions of classical network simulators, such as ns-2, J-Sim (previously known as JavaSim), and GloMoSim/ Qualnet.
>   The focus of these simulators is on network modeling, protocol stacks, and simulation performance. Another class of simulators, sometimes called software-in-the-loop simulators, incorporate the actual node software into the simulation. For this reason, they are typically attached to particular hardware platforms and are less portable. Example include TOSSIM [12] for Berkeley motes and Em* [13] for Linux-based nodes such as Sensoria WINS NG platforms.


>  ***THE NS-2 SIMULATOR AND ITS SENSOR NETWORK EXTENSIONS***
>  
>  The simulator ns-2 is an open-source network simulator that was originally designed for wired, IP networks. Extensions have been made to simulate wireless/mobile networks (e.g. 802.11 MAC and TDMA MAC) and more recently sensor networks.  
>
>  While the original ns-2 only supports logical addresses for each node, the wireless/mobile extension of it (e.g. [14]) introduces the notion of node locations and a simple wireless channel model. This is not a trivial extension, since once the nodes move, the simulator needs to check for each physical layer event whether the destination node is within the communication range. For a large network, this significantly slows down the simulation speed. There are two widely known efforts to extend ns-2 for simulating sensor networks:
>  
>  SensorSim form UCLA and the NRL sensor network extension from the Navy Research Laboratory . SensorSim also supports hybrid simulation, where some real sensor nodes, running real applications, can be executed together with a simulation. The NRL sensor network extension provides a flexible way of modeling physical phenomena in a discrete event simulator. Physical phenomena are modeled as network nodes which communicate with real nodes through physical layers
>
>  The main functionality of ns-2 is implemented in C++, while the dynamics of the simulation (e.g., timedependent application characteristics) is controlled by Tcl scripts. Basic components in ns-2 are the layers in the protocol stack. They implement the handlers interface, indicating that they handle events. Events are communication packets that are passed between consecutive layers within one node, or between the same layers across nodes. The key advantage of ns-2 is its rich libraries of protocols for nearly all network layers and for many routing mechanisms. These protocols are modeled in fair detail, so that they closely resemble the actual protocol implementations. Examples include the following:
>  TCP: reno, tahoe, vegas, and SACK implementations. MAC: 802.3, 802.11, and TDMA. Ad hoc routing: Destination sequenced distance vector (DSDV) routing, dynamic source routing (DSR), ad hoc on-demand distance vector (AOPDV) routing, and temporarily ordered routing algorithm (TORA). Sensor network routing: Directed diffusion, geographical routing (GEAR) and geographical adaptive fidelity (GAF) routing.


>   ***THE SIMULATOR TOSSIM*** 
>   
>    TOSSIM is a dedicated simulator for TinyOS applications running on one or more Berkeley motes. The key design decisions on building TOSSIM were to make it scalable to a network of potentially thousands of nodes, and to be able to use the actual software code in the simulation. To achieve these goals, TOSSIM takes a cross-compilation approach that compiles the nesC source code into components in the simulation. The event-driven execution model of TinyOS greatly simplifies the design of TOSSIM. By replacing a few low-level components such as the A/D conversion (ADC), the system clock, and the radio front end, 
>    
>    TOSSIM translates hardware interrupts into discrete-event simulator events. The simulator event queue delivers the interrupts that drive the execution of a node. The upper-layer TinyOS code runs unchanged. TOSSIM uses a simple but powerful abstraction to model a wireless network. A network is a directed graph, where each vertex is a sensor node and each directed edge has a bit- error rate. Each node has a private piece of state representing what it hears on the radio channel. By setting connections among the vertices in the graph and a bit-error rate on each connection, wireless channel characteristics, such as imperfect channels, hidden terminal problems, and asymmetric links can be easily modeled. 
>    
>    Wireless transmissions are simulated at the bit level. If a bit error occurs, the simulator flips the bit. TOSSIM has a visualization package called TinyViz, which is a Java application that can connect to TOSSIM simulations. TinyViz also provides mechanisms to control a running simulation by, for example, modifying ADC readings, changing channel properties, and injecting packets. TinyViz is designed as a communication service that interacts with the TOSSIM event queue. The exact visual interface takes the form of plug-ins that can interpret TOSSIM events. Beside the default visual interfaces, users can add application- specific ones easily.


   





   
   