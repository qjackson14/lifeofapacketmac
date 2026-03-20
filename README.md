<p align="center">

</p>


<h2>Video Demonstration</h2>

- ### [YouTube: Day 12 Life of a Packet MAC Addresses](https://www.youtube.com/watch?v=rj6F-HQ_MOE)

<h2>Environments and Technologies Used</h2>

- Jeremy's IT Lab Youtube Channel
- Cisco Packet Tracer
  

  
<h2>Operating Systems Used </h2>

- Cisco IOS


<h2>Step-by-Step</h2>

<b>🧪 Step 1: Analyze Packet from PC1 → PC4 (Different Networks)</b>

1. Understand the Scenario

Source: PC1 (192.168.1.1)

Destination: PC4 (192.168.3.1)

Key Rule:

IP addresses = DO NOT change

MAC addresses = change at each hop

2. Segment A: PC1 → SW1

Identify source MAC:

PC1’s MAC address

Identify destination MAC:

Default gateway (R1 G0/0 interface)

3. Segment B: SW1 → R1

MAC addresses remain the same as Segment A

Switch behavior:

Does NOT modify MAC addresses

Only forwards frames

4. Verify Using Commands
On PC1:

Run:

ipconfig /all

Record MAC address

On R1:

Enter:

enable

show interface g0/0

Record MAC address

5. Use Simulation Mode

Send initial ping:

ping 192.168.3.1

Send second ping (after ARP completes)

Switch to simulation mode

Inspect frame:

Confirm:

Source MAC = PC1

Destination MAC = R1 G0/0

6. Segment C: R1 → R2

Source MAC:

R1 G0/1

Destination MAC:

R2 G0/0

Verify:

On R1:

show interface g0/1

On R2:

show interface g0/0

Check simulation “OUT” layer

7. Segment D: R2 → R3

Source MAC:

R2 G0/1

Destination MAC:

R3 G0/0

Verify:

On R2:

show interface g0/1

On R3:

show interface g0/0

8. Segment E & F: R3 → SW2 → PC4

Source MAC:

R3 G0/1

Destination MAC:

PC4

Key Concept:

Destination network is directly connected

Router sends frame directly to final device

Verify:

On R3:

show interface g0/1

On PC4:

ipconfig /all

Check simulation (IN and OUT layers)

🧪 Step 2: Analyze Packet from PC1 → PC3 (Same Network)

1. Understand the Difference

Source: PC1

Destination: PC3 (same subnet)

Key Rule:

No default gateway used

Direct communication

2. Identify MAC Addresses

Source MAC:

PC1

Destination MAC:

PC3

3. Verify MAC Address of PC3

On PC3:

ipconfig /all

4. Test Connectivity

From PC1:

ping 192.168.1.3

Run again after ARP completes

5. Use Simulation Mode

Send ping again

Inspect frame at switch

Confirm:

Source MAC = PC1

Destination MAC = PC3

Note:

Switch does NOT change MAC addresses

🧠 Key Concepts to Remember
1. IP vs MAC Behavior

IP addresses = End-to-end (never change)

MAC addresses = Change at each hop

2. Default Gateway Rule

Different network → send to router (gateway)

Same network → send directly to destination

3. Switch Behavior

Learns MAC addresses

Forwards frames

Does NOT modify MAC addresses

4. Router Behavior

Removes old frame

Re-encapsulates with:

New source MAC (its interface)

New destination MAC (next hop)

5. ARP Process

Required before communication

First ping may fail due to ARP resolution

✅ Practice Tip

When answering MAC address questions:

Always ask:

Is the destination local or remote?

Who is the next hop?

Which interface is sending?
