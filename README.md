## Beacon frames

### _1. What are the SSIDs of the two access points that are issuing most of the beacon frames in this trace?_

![image](https://github.com/user-attachments/assets/493e4354-6a80-47d2-a719-37d888d5acd5)
The SSID of the two access points issuing most of the beacon frames are:
- 30 Munroe St
- linksys_SES_24086

### _2. What are the intervals of time between the transmissions of the beacon frames the linksys_ses_24086 access point? From the 30 Munroe St. access point? (Hint: this interval of time is contained in the beacon frame itself)._

![image](https://github.com/user-attachments/assets/ed2d1cee-0d66-4bd1-b71b-76cbfb4c0046)

Beacon interval of linksys_SES_24086 is 0.102400 seconds.

![image](https://github.com/user-attachments/assets/736961ba-a5da-4500-949b-b189d5c708c5)
Beacon interval of 30 Munroe St is 0.102400 seconds.

### _3. What (in hexadecimal notation) is the source MAC address on the beacon frame from 30 Munroe St?_

![image](https://github.com/user-attachments/assets/1c5340f4-e83c-4a4d-9096-fa837633fd37)
The source MAC address of beacon frame from 30 Munroe St is 00:16:b6:f7:1d:51.

### _4. What (in hexadecimal notation) is the destination MAC address on the beacon frame from 30 Munroe St??_

![image](https://github.com/user-attachments/assets/b5304309-00e7-4f99-bab0-89350548033f)
A beacon frame is a management frame that Wi-Fi access points (APs) send periodically to advertise its existence and help devices connect to it. Beacon frames always send broadcast messages. So, the destination MAC address of beacon frame from 30 Munroe St is ff:ff:ff:ff:ff:ff.

### _5. What (in hexadecimal notation) is the MAC BSS id on the beacon frame from 30 Munroe St?_

![image](https://github.com/user-attachments/assets/3d414009-4837-4662-91e0-f6183005af2c)
BSS ID stands for Basic Service Set Identifier. It is a 48-bit MAC address for a specific access point (AP) within a wireless network. The BSS ID on the beacon frame from 30 Munroe St is 00:16:b6:f7:1d:51.

### _6. The beacon frames from the 30 Munroe St access point advertise that the access point can support four data rates and eight additional “extended supported rates.” What are these rates?_

![image](https://github.com/user-attachments/assets/e528b8e0-9b1d-4c3c-9111-97f32ee87788)
The four supported rates are:
- 1(B) (0x82)
- 2(B) (0x84)
- 5.5(B) (0x8b)
- 11(B) (0x96)

The eight extended supported rates are:
- 6(B) (0x8c)
- 9 (0x12)
- 12(B) (0x98)
- 18 (0x24)
- 24(B) (0xb0)
- 36 (0x48)
- 48 (0x60)
- 54 (0x6c)

## Data transfer

### _7. Find the 802.11 frame containing the SYN TCP segment for this first TCP session (that downloads alice.txt). What are three MAC address fields in the 802.11frame? Which MAC address in this frame corresponds to the wireless host (give the hexadecimal representation of the MAC address for the host)? To the access point? To the first-hop router? What is the IP address of the wireless host sending this TCP segment? What is the destination IP address? Does this destination IP address correspond to the host, access point, first-hop router, or some another network-attached device? Explain._

Filter using http to find the packet corresponding to the request for alice.txt:
![image](https://github.com/user-attachments/assets/f8340639-4c93-48b4-a1cd-99173b451fe1)

Filter using tcp to identify the corresponding first SYN TCP segment for alice.txt:
![image](https://github.com/user-attachments/assets/98f73cf4-325e-4a21-b00b-102d3254ecea)

To verify if the SYN TCP corresponds to the downloading of alice.txt:
![image](https://github.com/user-attachments/assets/bf7a3d21-13e5-4edf-87bb-ac00d95f85a4)

![image](https://github.com/user-attachments/assets/1295c54e-a120-428f-acd7-d969de5379e5)

![image](https://github.com/user-attachments/assets/110fca47-7bda-48af-acb6-0c0e8717aa66)

The MAC address fields are:
- Source address: 00:13:02:d1:b6:4f
- Destination address: 00:16:b6:f4:eb:a8
- BSS ID: 00:16:b6:f7:1d:51

- The MAC address that corresponds to the wireless host is the source address: 00:13:02:d1:b6:4f.
- The MAC address that corresponds to the access point is the BSS ID: 00:16:b6:f7:1d:51.
- The MAC address that corresponds to the first-hop router is the receiver address: 00:16:b6:f7:1d:51.

![image](https://github.com/user-attachments/assets/371ac1a8-6e64-44d1-9462-64ea23dd362d)

The IP address of the wireless host sending the TCP segment is 192.168.1.109. The destination IP address is 128.119.245.12.

### _8. Find the 802.11 frame containing the SYNACK segment for this TCP session. What are three MAC address fields in the 802.11 frame? Which MAC address in this frame corresponds to the host? To the access point? To the first-hop router? Does the sender MAC address in the frame correspond to the IP address of the device that sent the TCP segment encapsulated within this datagram?_

![image](https://github.com/user-attachments/assets/4194aeee-4909-4c6f-bf37-5d8e04d552d7)
The MAC address fields are:
- Source address: 00:16:b6:f4:eb:a8
- Destination address: 00:13:02:d1:b6:4f
- BSS ID: 00:16:b6:f7:1d:51

- The MAC address that corresponds to the wireless host is the destination address: 00:13:02:d1:b6:4f.
- The MAC address that corresponds to the access point is the BSS ID: 00:16:b6:f7:1d:51.
- The MAC address that corresponds to the first-hop router is the receiver address: 00:13:02:d1:b6:4f.

The sender MAC address of this particular TCP frame is the transmitter address: 00:16:b6:f7:1d:51. The sender IP address is 128.119.245.12 corresponds to the gaia.cs.umass.edu server in another network. The corresponding MAC address is the source address: 00:16:b6:f4:eb:a8. Hence, the sender MAC address in the frame does not correspond to the IP address of the device that sent the TCP segment encapsulated within this datagram.

## Association/Dissociation

### _9. What two actions are taken (i.e., frames are sent) by the host in the trace just after t=49, to end the association with the 30 Munroe St AP that was initially in place when trace collection began? (Hint: one is an IP-layer action, and one is an 802.11-layer action). Looking at the 802.11 specification, is there another frame that you might have expected to see, but don’t see here?_

We know that the IP address of the wireless host is 192.168.1.109 and the corresponding MAC is 00:13:02:d1:b6:4f.

![image](https://github.com/user-attachments/assets/0c2fc6a1-f733-4823-9560-c6826b9d0947)
At time after t=49, to end the association with 30 Munroe St, DHCP Release and de-authentication frames are sent. But there is no dissociation frame.

### _10. Examine the trace file and look for AUTHENICATION frames sent from the host to an AP and vice versa. How many AUTHENTICATION messages are sent from the wireless host to the linksys_ses_24086 AP (which has a MAC address of Cisco_Li_f5:ba:bb) starting at around t=49?_

![image](https://github.com/user-attachments/assets/b4ef8c75-ca1b-41c5-aac9-45b24435e223)
Sort the packets according to the Info column.

- Wireless host MAC address is 00:13:02:d1:b6:4f.
- linksys_SES_24086 AP MAC address is 00:18:39:f5:ba:bb.

Only host can send authentication messages to AP. None are sent from AP to the host. 15 authentication messages are sent from the host to the AP.

### _11. Does the host want the authentication to require a key or be open?_

![image](https://github.com/user-attachments/assets/6076e028-9cd7-49d8-b5ab-b8003b5bf0e5)
The authentication algorithm used is Open System. Any client that requests authentication by using this algorithm can pass the authentication. There is no need for any key.

### _12. Do you see a reply AUTHENTICATION from the linksys_ses_24086 AP in the trace?_

No. There is no reply for the authentication messages from the AP to the host.

### _13. Now let’s consider what happens as the host gives up trying to associate with the linksys_ses_24086 AP and now tries to associate with the 30 Munroe St AP. Look for AUTHENICATION frames sent from the host to and AP and vice versa. At what times are there an AUTHENTICATION frame from the host to the 30 Munroe St. AP, and when is there a reply AUTHENTICATION sent from that AP to the host in reply? (Note that you can use the filter expression “wlan.fc.subtype == 11and wlan.fc.type == 0 and wlan.addr == IntelCor_d1:b6:4f” to display only the AUTHENTICATION frames in this trace for this wireless host.)_

We know that the MAC address of 30 Munroe St is 00:16:b6:f7:1d:51.

![image](https://github.com/user-attachments/assets/b2705ecb-c61f-4efa-a9bc-02ba45c64a2b)
- At time t=63.168087 and t=63.169707, authentication frames are sent from host to 30 Munroe St.
- At time t=63.169071 and t=63.170692. reply is sent from 30 Munroe St AP to the host.

### _14. An ASSOCIATE REQUEST from host to AP, and a corresponding ASSOCIATE RESPONSE frame from AP to host are used for the host to associated with an AP. At what time is there an ASSOCIATE REQUEST from host to the 30 Munroe St AP? When is the corresponding ASSOCIATE REPLY sent? (Note that you can use the filter expression “wlan.fc.subtype < 2 and wlan.fc.type == 0 and wlan.addr == IntelCor_d1:b6:4f” to display only the ASSOCIATE REQUEST and ASSOCIATE RESPONSE frames for this trace.)_

Host MAC address is 00:13:02:d1:b6:4f. 30 Munroe St AP MAC address is 00:16:b6:f7:1d:51.

![image](https://github.com/user-attachments/assets/8ec9cd94-965a-42e8-85f7-cd53c3e00565)
- At time t=63.169910, associate request is sent from host to 30 Munroe St AP.
- At time t=63.192101, associate response is sent from AP to host.

### _15. What transmission rates is the host willing to use? The AP? To answer this question, you will need to look into the parameter’s fields of the 802.11 wireless LAN management frame._

![image](https://github.com/user-attachments/assets/5375b759-422b-4a97-a6a1-6f07db3427b1)

The host:
- Supported Rates 1(B), 2(B), 5.5(B), 11(B), 6(B), 9, 12(B), 18, [Mbit/sec]
- Extended Supported Rates 24(B), 36, 48, 54, [Mbit/sec]

![image](https://github.com/user-attachments/assets/4f0c610f-25e4-44e4-bd13-04cf10094da8)

The 30 Munroe St AP:
- Supported Rates 1(B), 2(B), 5.5(B), 11(B), [Mbit/sec]
- Extended Supported Rates 6(B), 9, 12(B), 18, 24(B), 36, 48, 54, [Mbit/sec]

## Other frame types

### _16. Our trace contains a number of PROBE REQUEST and PROBE RESPONSE frames. What is the sender, receiver and BSS ID MAC addresses in these frames? What is the purpose of these two types of frames?_

![image](https://github.com/user-attachments/assets/84689cb5-8d30-4320-a375-bf9227320d84)
There are two probe requests and two probe responses.

1.
- Probe request:
  - Source address: 00:13:02:d1:b6:4f
  - Destination address: ff:ff:ff:ff:ff:ff
  - BSS ID: ff:ff:ff:ff:ff:ff
- Probe response:
  - Source address: 00:16:b6:f7:1d:51
  - Destination address: 00:13:02:d1:b6:4f
  - BSS ID: 00:16:b6:f7:1d:51

2.
- Probe request:
  - Source address: 00:12:f0:1f:57:13
  - Destination address: ff:ff:ff:ff:ff:ff
  - BSS ID: ff:ff:ff:ff:ff:ff
- Probe response:
  - Source address: 00:16:b6:f7:1d:51
  - Destination address: 00:12:f0:1f:57:13
  - BSS ID: 00:16:b6:f7:1d:51
