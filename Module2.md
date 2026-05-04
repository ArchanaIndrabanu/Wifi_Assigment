**1. Brief about SplitMAC architecture and how it improves the AP's performance**

SplitMAC architecture is a design approach in Wi-Fi networks where the MAC (Medium Access Control) functions are divided between the Access Point (AP) and a centralized controller.

In this architecture, time-critical functions such as frame transmission, acknowledgments, and real-time processing are handled by the access point, while non-time-critical functions like authentication, security management, and network policies are managed by a central controller.

This separation helps improve the performance of the access point in several ways. Since heavy processing tasks are offloaded to the controller, the AP becomes lighter and more efficient. It reduces the processing load on individual APs, allowing them to handle more client devices effectively. It also enables centralized management, making it easier to control multiple APs, apply configurations, and maintain consistency across the network.

Overall, SplitMAC architecture improves scalability, reduces latency for critical operations, and enhances the overall performance and efficiency of Wi-Fi networks.

**2. Describe about CAPWAP, explain the flow between AP and Controller**

CAPWAP (Control And Provisioning of Wireless Access Points)

CAPWAP is a protocol used for communication between wireless access points and a centralized controller. It enables centralized management by separating control and data functions.

In a CAPWAP-based network, the access point connects to the controller and establishes two tunnels:
- Control tunnel for management communication
- Data tunnel for user traffic

Flow between Access Point and Controller

1. Discovery Phase: The access point searches for a controller using DHCP, DNS, or a pre-configured IP address.

2. Join Phase: The access point sends a join request and establishes a secure connection with the controller.

3. Configuration Phase: The controller sends configuration details such as SSID, security settings, and policies to the access point.

4. Operation Phase: The access point starts serving clients. Control messages are exchanged through the control tunnel, and user data is transmitted through the data tunnel.

5. Keepalive / Maintenance: The access point and controller continuously exchange messages to maintain connectivity and monitor the network.

**3.Where this CAPWAP fits in OSI model, what are the two tunnels in CAPWAP and its purpose**

CAPWAP in OSI Model

CAPWAP operates mainly at the Application Layer (Layer 7) of the OSI model. It uses UDP at the Transport Layer for communication between the access point and the controller.

CAPWAP Tunnels and their Purpose

CAPWAP uses two types of tunnels between the Access Point (AP) and the Controller:

1. Control Tunnel:  
   This tunnel is used for management and control communication. It carries messages related to configuration, authentication, AP registration, and network policies.

2. Data Tunnel:  
   This tunnel is used to carry user data traffic between wireless clients and the network. It ensures that client data is forwarded properly through the controller.

**4. Whats the difference between Lightweight APs and Cloud-based APS**

Difference between Lightweight APs and Cloud-based APs

Lightweight Access Points and Cloud-based Access Points differ mainly in how they are managed and controlled.

Lightweight APs depend on a centralized wireless controller that is usually deployed within the local network. These APs handle basic functions, while most of the processing, configuration, and management are done by the controller. This setup is commonly used in enterprise environments where on-premises control is required.

Cloud-based APs, on the other hand, are managed through a cloud platform over the internet. There is no need for a physical controller on-site, as configuration, monitoring, and updates are handled remotely via the cloud. This makes deployment simpler and more scalable.

In terms of deployment, lightweight APs require a controller setup, which can increase initial cost and complexity. Cloud-based APs are easier to install and manage, especially for distributed networks.

Overall, lightweight APs offer strong local control and are suitable for large enterprise networks, while cloud-based APs provide flexibility, remote management, and ease of use.

**5. How the CAPWAP tunnel is maintained between AP and controller**

Maintenance of CAPWAP Tunnel between AP and Controller

The CAPWAP tunnel between the Access Point (AP) and the Controller is maintained through continuous communication and monitoring mechanisms.

Once the tunnel is established, both the AP and the controller exchange periodic **keepalive messages** (also called heartbeat messages). These messages ensure that both devices are active and the connection is still valid.

If the controller does not receive keepalive messages from the AP within a specific time, it assumes the AP is disconnected and terminates the session. Similarly, the AP will try to reconnect or discover a new controller if the connection is lost.

In addition to keepalive messages, CAPWAP uses **timers and acknowledgments** to ensure reliable communication. Any configuration updates or control messages are acknowledged to confirm successful delivery.

Some implementations also support **failover mechanisms**, where the AP can switch to a backup controller if the primary controller becomes unavailable.

**6.Whats the difference between Sniffer and monitor mode, use case for each mode**

Difference between Sniffer Mode and Monitor Mode

Sniffer mode and monitor mode are used for analyzing wireless traffic, but they differ in how they capture data and their purpose.

Monitor mode allows a wireless device to capture all Wi-Fi frames available in the air, without being connected to any specific network. It can capture raw packets, including management, control, and data frames from all nearby networks. This mode is mainly used for deep packet analysis and troubleshooting.

Sniffer mode, on the other hand, is typically used to capture and analyze traffic of a specific network or channel. It may be implemented using special tools or devices that collect packets for analysis, often focusing on a particular access point or client.

Key Difference

Monitor mode captures all wireless traffic in the air (broad capture), while sniffer mode focuses on capturing and analyzing specific traffic for inspection.

Use Cases

Monitor Mode:
- Network troubleshooting and debugging
- Security analysis and penetration testing
- Capturing all types of Wi-Fi frames

Sniffer Mode:
- Analyzing specific client or AP traffic
- Performance monitoring
- Packet-level inspection for a particular network

**7.If WLC deployed in WAN, which AP mode is best for local network and how?**

AP Mode for WAN-deployed WLC

When the Wireless LAN Controller (WLC) is deployed over a WAN, the best suited AP mode for the local network is **FlexConnect mode** (also known as H-REAP).

In this mode, the Access Point can perform local switching of client data traffic instead of sending all traffic to the controller over the WAN. This reduces WAN bandwidth usage and improves performance.

How it Works

- The AP still connects to the WLC for control and management functions.
- Client authentication and policies can be managed by the controller.
- Data traffic from clients is switched locally at the AP to the local network.
- If the WAN link fails, the AP can continue to operate and serve clients using locally stored configurations.

Advantages

- Reduces dependency on WAN for data traffic
- Improves latency and performance
- Provides better reliability during WAN failure
- Suitable for branch or remote office deployments

**8. What are challenges if deploying autonomous APs (more than 50) in large network like university**

Challenges of Deploying Autonomous APs in Large Networks

Deploying more than 50 autonomous access points in a large network like a university can create several challenges.

1. Configuration Complexity:  
   Each access point must be configured manually, which becomes time-consuming and difficult to manage as the number of APs increases.

2. Lack of Centralized Management:  
   There is no central controller, so monitoring, updates, and troubleshooting have to be done individually on each AP.

3. Inconsistent Configuration:  
   Maintaining the same settings (SSID, security, policies) across all APs is difficult, which may lead to misconfigurations.

4. Poor Scalability:  
   As the network grows, adding and managing more APs becomes inefficient and harder to control.

5. Roaming Issues:  
   Seamless roaming between APs is not well optimized, which can affect user experience in large areas like campuses.

6. Increased Maintenance Effort:  
   Firmware updates, security patches, and issue resolution must be handled separately for each AP.

7. Performance Optimization Challenges:  
   Channel selection, power levels, and interference management are harder to coordinate without centralized control.

**9. What happens on wireless client connected to Lightweight AP in local mode if WLC goes down.**

Behavior of Client when WLC Goes Down (Lightweight AP - Local Mode)

When a wireless client is connected to a Lightweight Access Point (LAP) operating in local mode, the AP depends on the Wireless LAN Controller (WLC) for both control and data traffic.

If the WLC goes down, the CAPWAP tunnel between the AP and the controller is lost. As a result, the access point is no longer able to forward client data traffic or receive control instructions.

Because of this:
- The AP stops serving wireless clients.
- Existing client connections are disconnected.
- New clients cannot connect to the network.
- The AP will continuously try to reconnect to the controller or discover a new one.
