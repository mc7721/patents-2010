---

title: Method and system for matching and repairing network configuration
abstract: Aspects of a method and system for matching and repairing network configuration are provided. In this regard, one or more circuits and/or processors may be operable to determine a configuration of one or more parameters in a plurality of devices along a network path, and detect whether any of the one or more parameters are configured such that communication between the plurality of devices is disabled and/or suboptimal. The devices may comprise at least one server and one or more of a network switch, a network bridge, and a router. In instances that one or more parameters are incompatibly or sub-optimally configured, a notification of the incompatibility may be communicated to a network management entity and/or one or more messages may be generated to reconfigure the one or more parameters in one or more of the plurality of devices. The determining and/or detecting may be performed automatically in response to various events.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08458305&OS=08458305&RS=08458305
owner: Broadcom Corporation
number: 08458305
owner_city: Irvine
owner_country: US
publication_date: 20100805
---
This patent application makes reference to claims priority to and claims benefit from U.S. Provisional Patent Application Ser. No. 61 231 726 filed on Aug. 6 2009.

Certain embodiments of the invention relate to networking. More specifically certain embodiments of the invention relate to a method and system for network configuration.

Information Technology IT management may require performing remote management operations of remote systems to perform inventory monitoring control and or to determine whether remote systems are up to date. For example management devices and or consoles may perform such operations as discovering and or navigating management resources in a network manipulating and or administrating management resources requesting and or controlling subscribing and or unsubscribing operations and executing and or specific management methods and or procedures. Management devices and or consoles may communicate with devices in a network to ensure availability of remote systems to monitor control remote systems to validate that systems may be up to date and or to perform any security patch updates that may be necessary. As networks become increasingly large and complex network management also becomes increasingly complex.

Further limitations and disadvantages of conventional and traditional approaches will become apparent to one of skill in the art through comparison of such systems with some aspects of the present invention as set forth in the remainder of the present application with reference to the drawings.

A system and or method is provided for matching and repairing network configuration substantially as shown in and or described in connection with at least one of the figures as set forth more completely in the claims.

These and other advantages aspects and novel features of the present invention as well as details of an illustrated embodiment thereof will be more fully understood from the following description and drawings.

Certain embodiments of the invention may be found in a method and system for matching and repairing network configuration. In various embodiments of the invention one or more circuits and or processors may be operable to determine a configuration of one or more parameters in a plurality of devices along a network path and detect whether any of the one or more parameters is configured such that communication between the plurality of devices is disabled and or suboptimal. In some instances parameters that are configured such that they are compatible with each other may be said to be matched whereas parameters which may be configured such that they are incompatible with each other may be said to be mismatched. In instances that one or more parameters are incompatibly or sub optimally configured the one or more circuits and or processors may communicate a notification of the incompatibility to a network management entity and or generate one or more messages to reconfigure the one or more parameters in one or more of the plurality of devices. In some instances reconfiguring one or more parameters such that they are matched and or optimally configured may be said to be repairing network configuration. The determining detecting matching and repairing may be performed automatically in response to a change in one or more of the parameters in one or more of the plurality of devices. The determining detecting matching and repairing may be performed automatically in response to a reconfiguration of the network path. The notification may comprise a recommended configuration of the one or more parameters in one or more of the plurality of devices. The one or more circuits and or processors may enable access to one or more application programming interfaces of one or more of the plurality of devices. The one or more circuits and or processors may be operable to translate between the one or more application programming interfaces and one or more network interfaces.

The one or more circuits and or processors may be operable to manage configuration of the one or more parameters in a first portion of the plurality of devices. The one or more circuits and or processors may be operable to communicate with one or more other circuits and or processors that manage configuration of the one or more parameters in a second portion of the plurality of devices. The one or more circuits and or processors may be operable to automatically perform the determining and or detecting in response to a communication from the one or more other circuits and or processors. Incompatibilities between parameters in the first portion of the plurality of devices and parameters in the second portion of the plurality of network devices may be reconciled via communications between the one or more circuits and or processors and the one or more other circuits and or processors.

The network may comprise a plurality of link layer technologies such as Ethernet Fiber Channel and Infiniband. In an exemplary embodiment of the invention the network may utilize one or more data center bridging DCB techniques and or protocols such as Congestion Notification CN Priority Flow Control PFC and Enhanced Transmission Selection ETS .

The racks may comprise rack mount networking systems that may house for example computing devices such as servers and computers and network devices such as switches and or other devices such as power supplies. In this regard the term computing device is utilized herein to describe a device such as a server which is conventionally managed by a first management entity and or utilizing a first set of management protocols and or tools. Similarly the term network device is utilized herein to describe a device such as an Ethernet switch which is conventionally managed by a second management entity and or utilizing a second set of management protocols and or tools. However in practice the line between a network device and a computing device is becoming increasingly blurry. For example a virtual switch residing in a server may depending on the circumstances be referred to by either or both terms. Similarly other devices such as the UPS or displays not shown may comprise various functionalities which may result in them being considered as computing devices and or network devices. Accordingly computing devices network devices and other devices are referred to collectively and individually herein as simply devices. Furthermore aspects of the invention may enable simplifying and or unifying management of various devices particularly in instances when multiple management entities need or desire to manage various devices and or portions thereof.

Each rack may comprise N servers where N is an integer greater than or equal to 1 and m is an integer between 1 and M. The servers of rack may each comprise suitable logic circuitry interfaces and or code that may be operable to provide services to clients such as PCs mobile devices and other servers. Each of the servers may be operable to for example run one or more applications that processes input from the clients and or output information to the clients.

Each of the servers may interface with the network via a corresponding one of network interface circuits NICs . The NICs of the rack may each comprise suitable logic circuitry interfaces and or code that may be operable to interface the corresponding servers to the switch .

Each rack may also comprise a switch . Each of the switches may comprise suitable logic circuitry interfaces and or code that may be operable to forward packets between corresponding NICs other ones of the switches and other networks and or storage area networks such as the subnetwork .

Each logical point of management LPM may comprise suitable logic circuitry interfaces and or code that may enable managing configuration of one or more devices with which it is associated. Each LPM may comprise for example one or more processors memory devices and bus controllers. Each LPM may comprise for example dedicated shared and or general purpose hardware and or may comprise firmware and or software executed by dedicated shared and or general purpose hardware. Each LPM or portions thereof may reside in various places. For example for a rack portions of the LPM may reside in the switch in one or more of the servers in one or more of the NICs on the rack itself or a combination thereof. In various embodiments of the invention each LPM may be similar to or the same as a central management unit CMU described in U.S. patent application Ser. No. 12 619 221 which is incorporated by reference above.

In the exemplary embodiment of the invention depicted in each rack may comprise a LPM such that all the devices of each rack may be associated with and managed via a corresponding LPM . As a result the rack servers the NICs the switch and the UPS may be managed via the LPM . Additionally in some instances devices external to the rack such as devices not shown residing in the subnetwork may be associated with and thus managed via a LPM .

Each LPM may enable management of associated devices by for example exposing one or more application programming interfaces APIs of the associated devices to one or more network management entities such as the console . In this regard each LPM may be operable to translate between one or more APIs and one or more network interfaces. For instance each LPM may be operable to receive a command or request over a network interface and may de packetize convert reformat and or otherwise process the command or request to generate a corresponding command or request on one or more APIs to one or more devices.

In the exemplary embodiment of the invention depicted in each LPM may expose an internal API of the rack to the one or more management consoles .

In operation each LPM may collect configuration information from its associated devices make the information available among the associated devices and make the information available to the management console . Similarly each LPM may receive configuration information from the management console and or other LPMs and distribute or make available the received configuration information among the devices associated with the LPM . Such exchanged configuration information may be utilized to ensure that devices are compatibly and or optimally configured to enable and or optimize communications in the network . In this regard parameters in various devices of the network may be configured based on information communicated to from and or between the LPMs .

Whether various parameters are compatible or how to make parameters compatible may vary with the parameters and the circumstances. For example one or more parameters in a first device may be compatible with one or more corresponding parameters in a second device when the parameters in the first device have the same values as the corresponding parameters in the second device. As another example one or more parameters in a first device may be compatible with one or more corresponding parameters in a second device when the parameters in the first device are configured to have values associated with transmission and the corresponding parameters in the second device are configured to have values associated with reception. Whether parameters are compatible may be characterized by for example whether messages that utilize or depend on the parameters can be successfully communicated. Similarly whether parameters are optimal may be characterized by for example a data rate and or error rate that may be achieved in communications that utilize or depend on those parameters.

An exchange of configuration information to validate a configuration of and or reconfigure one or more devices may occur upon for example one or more of a change in network topology e.g. addition removal power up or power down of a device a change in one or more parameters a request from a management console and reception of configuration information at an LPM from another one of the LPMs or from a management entity. In this regard various events may automatically trigger a collection of configuration information an exchange of configuration information and or a reconfiguration of one or more devices.

The exchanged information may ensure link partners and devices along a network path are compatibly configured to enable and or optimize communication along the respective link s and path s . For example one or more parameters in the servers and or NICs may need to match or be compatible with a corresponding one or more parameters in the switch to enable and or optimize communication between the switch and the server . That is if parameters in the server and or NIC and the switch are incompatibly configured then communication over the corresponding link may fail or be sub optimal. In this example the server the NIC and the switch may all be associated with a single LPM however multiple LPMs may interact to achieve the same results. To elaborate the LPM and the LPM may exchange information with each other and or with one or more management consoles to ensure link partners and or devices along a network path are compatibly and or optimally configured. For example the server may need or desire to communicate with the server . As a result one or more parameters in the server or NIC one or more parameters in the server or NIC and one or more corresponding parameters in any switches routers or other intermediary devices between the server and the server may need to be compatibly configured to enable and or optimize communication along the path. Accordingly the LPM the LPM and any LPM s associated with any intermediary device s if such intermediary devices are present and if such devices are not associated with either of the LMP and may exchange configuration information with each other and or with one or more management consoles to ensure compatible and or optimal configuration along the network path between server and server .

In an exemplary embodiment of the invention in instances that an exchange of configuration information results in a detection that one or more parameters are incompatibly configured one or more of LPMs may generate a notification to another one or more of the LPMs and or to one or more management entities such as the console . The notification may comprise for example current configuration possible compatible configurations and or a recommended configuration. In this manner current configuration and or recommended configuration may be presented to for example management software and or to a network administrator who may view the information and make management decisions based on the notification. In instances that there are multiple management entities the management entities may then negotiate with each other to determine how to configure the devices. The management entities may then reconfigure one or more parameters to eliminate the incompatibility. The configuration by the management entities may be performed utilizing standard management protocols and or tools and or via the LPMs .

In an exemplary embodiment of the invention in instances that an exchange of configuration information results in a detection that one or more parameters are mismatched or sub optimally configured the corresponding ones of the LPMs may automatically reconfigure the parameters into a best possible configuration. In such instances that LPMs interact to automatically reconfigure one or more parameters one LPM may act as a master while others may act as a slave. Which device is master and which is slave may be determined on a per parameter per link per connection per network per function and or on any other basis.

In various embodiments of the invention configuration compatibility may be determined per link and or end to end for various parameters. Exemplary parameters may comprise virtual local area networking VLAN identifiers and or other VLAN parameters teaming parameters MAC addresses parameters regarding data rates supported and or utilized parameters regarding whether communications are to be simplex duplex and or unidirectional an indication of whether or not IEEE 802.3 PAUSE is to be enabled energy efficient networking EEN or energy efficient Ethernet EEE parameters and parameters regarding supported and or expected formatting of packets. Also the parameters may be associated with data center bridging DCB policies and or settings such as whether priority flow control PFC support is enabled a number of priority classes utilized for PFC number of lossless priority classes whether ETS is enabled whether and how quantized congestion notification QCN is supported whether and how iSCSI is supported whether and how Fiber Channel over Ethernet FCoE is supported the maximum transmission unit MTU supported for a lossless priority the maximum MTU for all priorities whether and how a lossless performance mode is supported.

In some embodiments of the invention FCoE iSCSI or other protocols that require lossless communication may be utilized. Accordingly aspects of the invention may enable ensuring that support of lossless behavior is compatibly configured among link partners and end to end. In some instances if a mismatch either among link partners or at some point along an end to end path is detected because a NIC does not support lossless behavior but a corresponding switch does then IEEE 802.3 PAUSE may be enabled on the link between the NIC and the switch .

In the exemplary embodiment of the invention depicted in the network comprises an LPM for each of the racks . However the network and racks and are for illustration purposes only and the invention is not limited with regard to network topology the particular devices within a network the particular devices within a Rack and or the particular devices managed by an associated LPM .

The LPM may be substantially similar to the LPMs described with respect to . In various exemplary embodiments of the invention the LPM may be implemented via any combination of dedicated and or shared logic circuitry interfaces and or code that resides anywhere on or within the Rack . In the exemplary embodiment of the invention depicted in the LPM is implemented in dedicated logic circuitry interfaces and or code residing on the rack separately from the servers the blade switches and the TOR switch .

The NIC may comprise suitable logic circuitry interfaces and or code that may be operable to transmit and receive data in adherence with one or more networking standards. With reference to the OSI model the NIC may implement physical layer functions data link layer functions and in some instances functions associated with OSI layer and higher OSI layers. Similarly with reference to the TCP IP model the NIC may be operable to implement network interface layer functions Internet layer functions and in some instances transport layer functions and application layer functions. The NIC may for example communicate in adherence with one or more Ethernet standards defined in IEEE 802.3. The NIC may be enabled to utilize virtualization such that it may present itself as multiple network adapters.

The BMC may comprise suitable logic circuitry interfaces and or code that may be operable to monitor various conditions on the corresponding server and control various functions and or hardware components of the corresponding server based on the monitored conditions. For example the BMC may receive data from one or more sensors and determine that the server needs to be reset based on the sensor data. As another example the BMC may monitor temperature of the server and adjust fan speed accordingly. The BMC may also comprise suitable logic circuitry interfaces and or code that may be operable communicate with a management entity via an internal data bus and or a network link. For example a management entity may request a status report from the BMC and in response the BMC may gather information from various sensors and communicate the information to the management entity.

The storage may comprise for example a hard drive or solid state memory. The storage may store for example data that may be read written and or executed locally or remotely via the NIC .

The processor and the memory may comprise suitable logic circuitry interfaces and or code that may enable processing data and or controlling operations of the server . The memory may comprise for example SRAM DRAM and or non volatile memory that stores data and or instructions. The processor utilizing the memory may be operable to execute code to effectuate operation of the server . For example the processor may execute code stored in the memory to realize the hypervisor and the VMs OSs .

In operation a configuration of any one or more of the TOR switch the blade switches and any one or more components of any one or more of the servers may be managed via the LPM . In this regard the LPM may be operable to determine a configuration of one or more parameters in any one or more components of the rack and may be operable to determine. For instance if one or more parameters in the blade switch is configured incompatibly with one or more parameters in the NIC of the server then traffic to and or from the server may be impossible or sub optimal. Similarly if a remote client not shown requests a datastream from the VM OS of the server but one or more parameters in the vSwitch of the server is incompatibly or sub optimally configured with one or more corresponding parameters in the NIC of server the blade switch and or in the remote client then the datastream may not be communicated or may be communicated sub optimally. In instances that one or more parameters are incompatible or sub optimal messages may be exchanged between the LPM and a LPM associated with the remote client automatically reconfigure the parameter s and or notify one or more management entities based on network and or device policies or settings. Reconciliation of one or more incompatible parameters may depend for example on an order of precedence or hierarchy of LPMs and or management entities. For example in resolving conflicts in parameter configuration the decisions of certain management entities may control over the decisions of other management entities and or decisions of certain LPMs may control over the decisions of other LPMs.

The LPM may determine and or configure parameters of various components of the rack via one or more data busses such as a PCI X bus. Additionally or alternatively the LPM may determine and or configure parameters of various components of the rack via one or more network connections such as an Ethernet connection. For example in an exemplary embodiment of the invention the LPM may manage various components of the server utilizing Ethernet packets communicated via the TOR switch and the blade switch . In such an embodiment a portion of the LPM may comprise an agent for example a virtual machine or software agent running on the server such that the agent may be operable to receive process implement generate and or transmit configuration messages. In this regard the agent may be operable to collect configuration information from various components of the server generate one or more network messages for example an Ethernet frame comprising the configuration information and communicate the message s to another portion of the LPM and or to a management entity such as the console described with respect to .

In the exemplary embodiment of a potion of the LPM resides in the TOR switch and a portion resides in each server . The portion may communicate over one or more network links for example Ethernet links with one or more management entities such as console and may communicate with each of the servers via one or more network links internal to the rack . The portion may comprise for example a software agent. Each portion on each of the servers may receive packets from the portion and generate corresponding signals and or commands on the corresponding server to implement and or respond to requests and or commands contained in the received packets.

In an exemplary operation a management entity may send a request for configuration information to the LPM . The LPM may send corresponding requests to the agents . Each agent may collect the configuration information for its respective server and report such information to the portion . The portion may then aggregate the configuration and report the information to the management entity.

In an exemplary operation a portion may detect a change in one or more parameters in the server on which it resides. The portion may report this change to the portion which may determine whether the new configuration is incompatible with one or more parameters on any of the other servers and or with one or more devices external to the server . In some instances if there is an incompatibility internal to the rack the portion may automatically reconfigure one or more of the parameters to reconcile the incompatibility. In some instances if there is an incompatibility and or sub optimal configuration internal to the rack the portion may send a notification of the incompatibility and or sub optimal configuration to a management entity. The notification may comprise a possible and or recommended reconfiguration to optimize the configuration and or eliminate the incompatibility. In some instances if there is an incompatibility and or sub optimal configuration with respect to a device that is external to the rack the portion may communicate with a LPM associated with the external device to optimize the configuration and or reconcile the incompatibility.

In operation communication may be desired between devices and and enabling and or optimizing such communication may require that the parameters and be compatibly configured in each of the devices and . For illustration to enable and or optimize delivery of a media stream from the device to the device each of the parameters and may need to be set to A. 

Accordingly configuration information as indicated by dashed lines may be communicated among the LPMs and and or the management entities and . In this regard the LPM may collect the current configuration of the parameters and the LPM may collect the current configuration of the parameters and and the LPM may collect the current configuration of the parameters and and then the LPMs and may exchange the collected configuration information. Upon receiving the configuration information from other LPMs one or more of the LPMs and and or the management entities and may inspect the information to detect any incompatibilities or sub optimal configurations. In the exemplary embodiment of the invention it may be detected that parameters and are incompatibly configured.

Upon detection the incompatibility may be resolved in variety of ways. The LPMs and may for example automatically determine a compatible configuration to enable and or optimize communication of the media stream. In this regard the LPMs and may negotiate and or one of LPMs and may take precedence over the other ones of the LPMs and to reconcile the incompatibility and resolve any conflicts. Similarly the management entities and may negotiate to resolve the conflict or if one of the management entities and takes precedence over the other then that management entity may decide how to resolve the incompatibility.

In an exemplary embodiment of the invention the LPMs may have priority for example be a master and may decide that the optimum configuration is to reconfigure parameters and to a value of A. Accordingly the LPM may reconto A send a command to LPM to reconto a value of A and then notify the LPM and or the management entity the reconfiguration. The LPM may then notify the management entity .

In an exemplary embodiment of the invention the management entity may decide that the optimum configuration is to reconfigure parameters and to a value of A. Accordingly the management entity may communicate such a decision to the LPM . In response the LPM may reconto A send a command to LPM to reconto a value of A and then notify the LPM and or the management entity the reconfiguration. The LPM may then notify the management entity . In this manner the single management entity may need only submit configuration parameters once to the LPM and configuration of the entire network path may occur as a result of that single message.

Although depicts an LPM associated with each of the devices and the invention is not so limited. For example each of devices may represent a plurality of devices. Similarly the LPMs and may each correspond to portions logical and or physical of a single LPM. In this regard an LPM may be distributed and or virtualized across multiple devices.

In step the one or more LPMs associated with the devices to be validated and or configured may obtain the current configuration of the devices and may determine whether any parameters are incompatibly configured with one or more corresponding parameters in other devices of the network path. In instances that the parameters are optimally configured the exemplary steps may advance to end step . Returning to step in instances that one or more parameters in one or more of the devices are mismatched and or sub optimal the exemplary step may depending on the network policies circumstances and or other implementation details advance to step and or step .

In step the LPM s may automatically reconfigure one or more of the devices based on factors such as the nature of the parameter s that are mismatched and or sub optimal whether current configuration results in no communication or just reduced communication the types of the devices security levels of the devices effect of the parameters on other network paths or other network or device functions any other policy or setting that may be established by network administrators.

In step the LPM that detects the mismatched and or sub optimal configuration may generate a notification to other LPMs and or to one or more network management entities. The notification may comprise a recommendation as to how to optimize the configuration and or repair the mismatch. A network management entity e.g. a automated or manned management console may utilize the notification and or recommendation to determine how to optimize configuration.

Various aspects of a method and system for matching and repairing network configuration are provided. In an exemplary embodiment of the invention one or more circuits and or processors such as any of LPMs and or a combination thereof may be operable to determine a configuration of one or more parameters and in devices and along a network path and detect whether any of the one or more parameters and is configured such that communication between the devices and is disabled and or suboptimal. In some instances parameters that are configured such that they are compatible with each other may be said to be matched whereas parameters which may be configured such that they are incompatible with each other may be said to be mismatched. In instances that one or more parameters and or are incompatibly or sub optimally configured the one or more circuits and or processors may communicate a notification of the incompatibility to a network management entity and or generate one or more messages to reconfigure one or more of the parameters and or in one or more of devices and . In some instances reconfiguring one or more parameters such that they are matched and or optimally configured may be said to be repairing network configuration. The determining detecting matching and repairing may be performed automatically in response to a change in one or more of the parameters and or in one or more of devices and . The determining and or detecting may be performed automatically in response to a reconfiguration of the network path. The notification may comprise a recommended configuration of the one or more parameters and or in one or more of devices and . The one or more circuits and or processors may enable access to one or more application programming interfaces of one or more of devices and . The one or more circuits and or processors may be operable to translate between the one or more application programming interfaces and one or more network interfaces.

The one or more circuits and or processors may be operable to configure of the one or more parameters in a first portion such as a first one of devices and of the plurality of devices and . The one or more circuits and or processors may be operable to communicate with one or more other circuits and or processors such as any of LPMs and or a combination thereof that manage configuration of the one or more parameters in a second portion of the plurality of devices such as a second one of devices and . The one or more circuits and or processors may be operable to automatically perform the determining and or detecting in response to a communication from the one or more other circuits and or processors. Incompatibilities between parameters and or in the first portion of the plurality of devices and parameters in the second portion of the plurality of network devices may be reconciled via communications between the one or more circuits and or processors and the one or more other circuits and or processors.

Other embodiments of the invention may provide a non transitory computer readable medium and or storage medium and or a non transitory machine readable medium and or storage medium having stored thereon a machine code and or a computer program having at least one code section executable by a machine and or a computer thereby causing the machine and or computer to perform the steps as described herein for matching and repairing network configuration.

Accordingly the present invention may be realized in hardware software or a combination of hardware and software. The present invention may be realized in a centralized fashion in at least one computer system or in a distributed fashion where different elements are spread across several interconnected computer systems. Any kind of computer system or other apparatus adapted for carrying out the methods described herein is suited. A typical combination of hardware and software may be a general purpose computer system with a computer program that when being loaded and executed controls the computer system such that it carries out the methods described herein.

The present invention may also be embedded in a computer program product which comprises all the features enabling the implementation of the methods described herein and which when loaded in a computer system is able to carry out these methods. Computer program in the present context means any expression in any language code or notation of a set of instructions intended to cause a system having an information processing capability to perform a particular function either directly or after either or both of the following a conversion to another language code or notation b reproduction in a different material form.

While the present invention has been described with reference to certain embodiments it will be understood by those skilled in the art that various changes may be made and equivalents may be substituted without departing from the scope of the present invention. In addition many modifications may be made to adapt a particular situation or material to the teachings of the present invention without departing from its scope. Therefore it is intended that the present invention not be limited to the particular embodiment disclosed but that the present invention will include all embodiments falling within the scope of the appended claims.

