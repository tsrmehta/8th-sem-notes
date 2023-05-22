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

[Routing protocols](https://www.geeksforgeeks.org/manet-routing-protocols/)  


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
     **Subtypes**
 >    1. On-Demand Multicast Routing Protocol
 >    2. Core-Assisted Mesh Protocol
 >    3.  Forwarding Group Multicast Protocol
 >    4. Other Protocols
>
>
>  3. Stateless Approaches:
     Stateless approaches, also known as flooding-based approaches, do not rely on any specific tree or mesh structures. Instead, each multicast-capable node simply broadcasts the multicast message to all of its neighbors. The neighbors, in turn, broadcast the message to their neighbors, and this process continues until all group members receive the message. While simple to implement, stateless approaches can suffer from excessive redundancy and broadcast storms if not carefully controlled.
     **Subtypes**
 >    1. Differential Destination Multicast
 >    2. DSR Simple Multicast and Broadcast Protocol
>
>  4. Hybrid Approaches:
      Hybrid approaches combine multiple techniques to achieve efficient multicasting. They leverage the advantages of different approaches to optimize the multicast communication. For example, a hybrid approach might use a tree-based structure for the core part of the network, while utilizing mesh-based or stateless approaches for the periphery or specific areas of the network where direct links or flooding are more efficient.
      **Subtypes**
 >    1. Ad hoc Multicast Routing Protocol
 >    2. Multicast Core-Extraction Distributed Ad Hoc Routing
 >    3. Mobility-based Hybrid Multicast Routing

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