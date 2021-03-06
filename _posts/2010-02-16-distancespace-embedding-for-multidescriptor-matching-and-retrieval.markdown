---

title: Distance-space embedding for multi-descriptor matching and retrieval
abstract: A process includes receiving an archive of video data comprising a plurality of archive descriptor types, and applying a query to the archive. The query includes a number of N query descriptor types for a query object. The process further includes determining a difference between each query descriptor type and corresponding descriptor types of the archive, and storing each difference as a point in an N dimensional space. The process further includes identifying an archive object that is similar to the query object as a function of proximities of the differences to an origin of the N dimensional space.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08442977&OS=08442977&RS=08442977
owner: Honeywell International Inc.
number: 08442977
owner_city: Morristown
owner_country: US
publication_date: 20100216
---
This invention was made with Government support under Grant Number HR0011 08 C 0135 S1 awarded by the Defense Advanced Research Projects Agency DARPA . The United States Government has certain rights in the invention.

The present disclosure relates to the processing of video data and in an embodiment but not by way of limitation matching and retrieving objects from video data using distance space embedding of multiple descriptors.

Video based object and activity recognition and retrieval systems use a variety of descriptors to represent visual attributes. In systems that handle broad categories of objects and activities no single descriptor type will normally suffice to represent all of the necessary attributes. For example in activity recognition there are normally two broad categories of activities. First there are articulated activities which are characterized by motion of a person s arms and legs or the motion of parts of a vehicle e.g. doors or other object. Second there are non articulated activities which are characterized by whole body or object motion such as a vehicle turning or simply moving forward. No single descriptor has the power to represent both articulated and non articulated activities. As a result systems use multiple descriptor types to handle both types of activities. Another example could be object recognition which uses other descriptor types some of which are based on color texture rigidity and shape.

The use of multiple descriptor types however complicates many of the steps used in recognition and retrieval systems. For example descriptors of different types cannot be compared. However there are two high level types of approaches to address this issue of the inability to compare descriptors of different types. First there are approaches that perform retrieval on individual descriptors and combine results. Second there are approaches that attempt retrieval based on heterogeneous sets of descriptors.

The subject matter described in this background section could be pursued but it has not necessarily been previously conceived or pursued. Therefore unless otherwise indicated herein the subject matter described in this background section is not prior art to the claims in this application and is not admitted to be prior art by inclusion in this background section.

In the following detailed description reference is made to the accompanying drawings that show by way of illustration specific embodiments in which the invention may be practiced. These embodiments are described in sufficient detail to enable those skilled in the art to practice the invention. It is to be understood that the various embodiments of the invention although different are not necessarily mutually exclusive. Furthermore a particular feature structure or characteristic described herein in connection with one embodiment may be implemented within other embodiments without departing from the scope of the invention. In addition it is to be understood that the location or arrangement of individual elements within each disclosed embodiment may be modified without departing from the scope of the invention. The following detailed description is therefore not to be taken in a limiting sense and the scope of the present invention is defined only by the appended claims appropriately interpreted along with the full range of equivalents to which the claims are entitled. In the drawings like numerals refer to the same or similar functionality throughout the several views.

Embodiments of the invention include features methods or processes embodied within machine executable instructions provided by a machine readable medium. A machine readable medium includes any mechanism which provides i.e. stores and or transmits information in a form accessible by a machine e.g. a computer a network device a personal digital assistant manufacturing tool any device with a set of one or more processors etc. . In an exemplary embodiment a machine readable medium includes volatile and or non volatile media e.g. read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices etc. as well as electrical optical acoustical or other form of propagated signals e.g. carrier waves infrared signals digital signals etc. . Consequently a machine readable medium can be either tangible or intangible in nature.

Such instructions are utilized to cause a general or special purpose processor programmed with the instructions to perform methods or processes of the embodiments of the invention. Alternatively the features or operations of embodiments of the invention are performed by specific hardware components which contain hard wired logic for performing the operations or by any combination of programmed data processing components and specific hardware components. Embodiments of the invention include digital analog signal processing systems software data processing hardware data processing system implemented methods and various processing operations further described herein.

A number of figures show block diagrams of systems and apparatus of embodiments of the invention. A number of figures show flow diagrams illustrating systems and apparatus for such embodiments. The operations of the flow diagrams will be described with references to the systems apparatuses shown in the block diagrams. However it should be understood that the operations of the flow diagrams could be performed by embodiments of systems and apparatus other than those discussed with reference to the block diagrams and embodiments discussed with reference to the systems apparatus could perform operations different than those discussed with reference to the flow diagrams.

One or more embodiments disclosed herein relate to video object recognition and retrieval based on heterogeneous sets of descriptors. These embodiments can employ all information i.e. all descriptor types known about the relevant video data at hand.

The one or more embodiments allow for the use of all descriptor types in a recognition and retrieval setting and address the recognition retrieval and refinement of a return set based on user feedback. While each descriptor type defines its own space a single item in an archive i.e. a moving object will give rise to several descriptors that exist in different spaces and cannot be compared. Consequently in an embodiment it is required that each descriptor type have an associated similarity or distance function defined in its respective space. The distance function need not be calibrated or otherwise modified to make them directly comparable across descriptor types.

Distance space embedding is used to perform matching and refinement. Descriptors representing moving objects in the archive are generated wherein each descriptor has some temporal duration. When retrieving similar instances based on a set of query descriptors each segment of the moving object s trajectory is represented as a single point in a distance space wherein its position in each of the dimensions of the distance space is determined by the distance similarity between the types of query descriptors and the corresponding types of descriptors representing segments of tracks in the archive.

Initial retrieval can be performed by learning a similarity metric in the distance space. The similarity metric is influenced by similarity with respect to each of the descriptor types. Multiple metrics can be learned for different types of searches. For example a different distance metric could be used for a vehicle track versus a person track. Tracks that are similar to the query will cluster around the origin of an N dimensional space in one or more dimensions and this leads to a way to leverage a similarity based index. However while embedding a point in the distance space for all tracks would be time consuming an embodiment only embeds those points that are similar with respect to at least one of the descriptors. That is the index is used to retrieve and embed only those tracks that will be near the origin along at least one descriptor dimension.

An embodiment can refine retrievals based on user feedback. Additionally relevance weighting can be applied to the distance space and this will implicitly perform feature selection. In another embodiment query expansion can be used to expand a return set beyond the initial set in the event that one or more descriptors are found not to be discriminative with respect to a particular query.

Since each archive track as well as each query track may give rise to multiple descriptors of each type the reduction of these sets to a single distance value can be done in a number of different ways. Depending on the embodiment the minimum distance between descriptors might be used or the mean median or maximum distance between the descriptors might be used. For example if a user was trying to identify archive tracks that are not similar to a query track then a maximum distance might be used.

As noted above the use of an index to support searches against large archives requires that each set of descriptors be organized in a data structure that allows for similarity searching. This requires that each descriptor have an associated distance or similarity function defined.

Referring specifically to the first example in at an archive of video data is received at a computer processor. The video data can include virtually any scene such as a parking lot an airport terminal a town or city plaza or a shopping mall just to name a few examples. The video data is processed and a plurality of descriptor types are computed. As a simple example the descriptor types for an object in the archive video data may include height width speed and motion of the object over some time range. For example as illustrated in view of a frame includes a depiction of a person . The person has a width W height H and may have a velocity V. The person may also have a particular body movement such as the waving of a hand at . These descriptor types are used to identify objects in the archive video data such as people since people in the video data will generally be of a known height width speed and motion. One of skill in the art will realize this is a simplified example and in practice a video data processing system that is used to process video data from any public or private area in which there are several objects can have up to 1 000 or more complex descriptors.

At a user applies a query to the archive. The query includes a number of query descriptors of different types or a query video from which such descriptors may be computed. These query descriptors are compared to the descriptors which represent the archive video data to match a query object with an archive object and retrieve that archive object if it matches the query object. As noted in the simple example above such matching can include comparing the height of a query object with an archive object the width of a query object with an archive object the expected speed of a query object with the speed of an archive object and any potential articulated motion of a query object with that of the archive object. In some embodiments a user is looking to identify any object such as any person that may come into the field of view of the system. In another embodiment the user is hoping to identify a particular individual or a particular object such as a particular type of automobile and even a particular automobile. In this second embodiment discriminating features such as color or texture can be used.

At a difference between each query descriptor and a corresponding archive descriptor is determined. This difference can be thought of as a simple distance. illustrate an example of this process. In the differences between a width height velocity and motion of an archive from the weight height velocity and motion of a query are determined. This results in several points P which can be placed in a distance space vector as illustrated in . Thereafter the points Pare placed into an N dimensional space such as in . As a specific example and referring to if the descriptor is a height the difference between the query object and the archive object may be 2 pixels so the difference or distance in such a case is 2. Then if the differences between width descriptors and speed descriptors are 3 and 5 respectively at this results in a single point for this object in a multi dimensional space at 2 3 5 as indicated in which is a certain distance from the origin . Of course for any practical implementation of a distance space embedding system N will be much greater than 3 and practical implementations are not amenable to a visual representation of the N dimensional space.

At an archive object that is similar to the query object is identified as a function of proximities of the differences between the query object and the archive object to an origin of the N dimensional space. At it is noted that the query descriptors can be stored in and retrieved from a database.

In one or more embodiments feedback can be received from a user in order to refine a recognition or retrieval. For example at one or more archive objects are identified as a function of a similarity of the query object and archive objects. At feedback is received from a user. This feedback can include an indication of whether a particular archive object is similar to a query object. At additional feedback is received from the user. This additional feedback includes a modification of the query. For example if the original set of descriptors recognizes and retrieves objects that are simply of no interest to the user the user can submit additional descriptor types in order to narrow the recognitions and retrievals. At the modified query is applied to the archive which should generate a different set of objects that are recognized and retrieved.

At a relevance weight is applied to a descriptor type such that the descriptor type has more or less relevance as compared to other descriptor types in the identification of a query object. This feature permits the identification of a descriptor type or feature that is more important than others and which will be accorded more weight in the recognition and retrieval of archive objects. For example if a user is searching for a known person within the confines of an airport terminal and the user knows that this sought after person is quite tall then any descriptor type relating to the height of such person can be given greater weight. This increased weight to the height descriptor type will narrow any objects returned in the recognition and retrieval steps of the system.

If too many objects are recognized and retrieved from the archive video data this means that the descriptor types are not discriminative. In one or more embodiments the query can be expanded by adding or removing descriptor types in order to narrow the set of the objects recognized and retrieved. The query can also be expanded by placing the user provided query descriptors with descriptors corresponding to an archive track identified by a user as being a match. Specifically at it is determined that one or more query descriptor types are not discriminative. At the query is expanded to include additional descriptor types and at the modified query is applied to the archive. In an embodiment this expansion can be an automatic feature of the system. In another embodiment the expansion can be based on user feedback and user input.

At only the set of archive objects that are similar to the query object as a function of at least a single distance are embedded in the N dimensional space. This single distance represents a distance between a single query descriptor and a single archive descriptor.

Referring to the second example in at an archive of video data is received at a computer processor and descriptors are computed on the archive at . At a user applies a query video. At the computer processor computes query descriptors on the query video. At a loop is entered the loop consisting of blocks wherein for a current descriptor type all descriptors that have a high similarity to the query are retrieved. Then at for each such similar descriptor all descriptors relating to a track segment are retrieved. At the similarity is measured with respect to query descriptors of like types. The loop terminates at wherein if there are more descriptor types the process returns to block and if there are no more query descriptor types the process proceeds to block .

At an N dimensional point is generated for each track segment. The N dimensional point is further based on N similarity measures. At the similarity of the track segments is measured from the proximity of the corresponding N dimensional point to the origin of the N dimensional space. At the most similar tracks are returned to the user. At feedback is received from the user and at the dimensions in the N dimensional space are re weighted based on any user feedback.

Moreover those skilled in the art will appreciate that the invention may be practiced with other computer system configurations including hand held devices multiprocessor systems microprocessor based or programmable consumer electronics network PCs minicomputers mainframe computers and the like. The invention may also be practiced in distributed computer environments where tasks are performed by I 0 remote processing devices that are linked through a communications network. In a distributed computing environment program modules may be located in both local and remote memory storage devices.

In the embodiment shown in a hardware and operating environment is provided that is applicable to any of the servers and or remote clients shown in the other Figures.

As shown in one embodiment of the hardware and operating environment includes a general purpose computing device in the form of a computer e.g. a personal computer workstation or server including one or more processing units a system memory and a system bus that operatively couples various system components including the system memory to the processing unit . There may be only one or there may be more than one processing unit such that the processor of computer comprises a single central processing unit CPU or a plurality of processing units commonly referred to as a multiprocessor or parallel processor environment. In various embodiments computer is a conventional computer a distributed computer or any other type of computer.

The system bus can be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of bus architectures. The system memory can also be referred to as simply the memory and in some embodiments includes read only memory ROM and random access memory RAM . A basic input output system BIOS program containing the basic routines that help to transfer information between elements within the computer such as during start up may be stored in ROM . The computer further includes a hard disk drive for reading from and writing to a hard disk not shown a magnetic disk drive for reading from or writing to a removable magnetic disk and an optical disk drive for reading from or writing to a removable optical disk such as a CD ROM or other optical media.

The hard disk drive magnetic disk drive and optical disk drive couple with a hard disk drive interface a magnetic disk drive interface and an optical disk drive interface respectively. The drives and their associated computer readable media provide non volatile storage of computer readable instructions data structures program modules and other data for the computer . It should be appreciated by those skilled in the art that any type of computer readable media which can store data that is accessible by a computer such as magnetic cassettes flash memory cards digital video disks Bernoulli cartridges random access memories RAMs read only memories ROMs redundant arrays of independent disks e.g. RAID storage devices and the like can be used in the exemplary operating environment.

A plurality of program modules can be stored on the hard disk magnetic disk optical disk ROM or RAM including an operating system one or more application programs other program modules and program data . A plug in containing a security transmission engine for the present invention can be resident on any one or number of these computer readable media.

A user may enter commands and information into computer through input devices such as a keyboard and pointing device . Other input devices not shown can include a microphone joystick game pad satellite dish scanner or the like. These other input devices are often connected to the processing unit through a serial port interface that is coupled to the system bus but can be connected by other interfaces such as a parallel port game port or a universal serial bus USB . A monitor or other type of display device can also be connected to the system bus via an interface such as a video adapter . The monitor can display a graphical user interface for the user. In addition to the monitor computers typically include other peripheral output devices not shown such as speakers and printers.

The computer may operate in a networked environment using logical connections to one or more remote computers or servers such as remote computer . These logical connections are achieved by a communication device coupled to or a part of the computer the invention is not limited to a particular type of communications device. The remote computer can be another computer a server a router a network PC a client a peer device or other common network node and typically includes many or all of the elements described above I O relative to the computer although only a memory storage device has been illustrated. The logical connections depicted in include a local area network LAN and or a wide area network WAN . Such networking environments are commonplace in office networks enterprise wide computer networks intranets and the internet which are all types of networks.

When used in a LAN networking environment the computer is connected to the LAN through a network interface or adapter which is one type of communications device. In some embodiments when used in a WAN networking environment the computer typically includes a modem another type of communications device or any other type of communications device e.g. a wireless transceiver for establishing communications over the wide area network such as the internet. The modem which may be internal or external is connected to the system bus via the serial port interface . In a networked environment program modules depicted relative to the computer can be stored in the remote memory storage device of remote computer or server . It is appreciated that the network connections shown are exemplary and other means of and communications devices for establishing a communications link between the computers may be used including hybrid fiber coax connections T1 T3 lines DSL s OC 3 and or OC 12 TCP IP microwave wireless application protocol and any other electronic media through any suitable switches routers outlets and power lines as the same are known and understood by one of ordinary skill in the art.

Thus an example system method and machine readable medium for distance space embedding for multi descriptor matching and retrieval has been described. Although specific example embodiments have been described it will be evident that various modifications and changes may be made to these embodiments without departing from the broader scope of the invention. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense. The accompanying drawings that form a part hereof show by way of illustration and not of limitation specific embodiments in which the subject matter may be practiced. The embodiments illustrated are described in sufficient detail to enable those skilled in the art to practice the teachings disclosed herein. Other embodiments may be utilized and derived therefrom such that structural and logical substitutions and changes may be made without departing from the scope of this disclosure. This Detailed Description therefore is not to be taken in a limiting sense and the scope of various embodiments is defined only by the appended claims along with the full range of equivalents to which such claims are entitled.

Such embodiments of the inventive subject matter may be referred to herein individually and or collectively by the term invention merely for convenience and without intending to voluntarily limit the scope of this application to any single invention or inventive concept if more than one is in fact disclosed. Thus although specific embodiments have been illustrated and described herein it should be appreciated that any arrangement calculated to achieve the same purpose may be substituted for the specific embodiments shown. This disclosure is intended to cover any and all adaptations or variations of various embodiments. Combinations of the above embodiments and other embodiments not specifically described herein will be apparent to those of skill in the art upon reviewing the above description.

The Abstract is provided to comply with 37 C.F.R. 1.72 b and will allow the reader to quickly ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate example embodiment.

