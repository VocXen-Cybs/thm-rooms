# ***Reading PCAP Files*** 

How many packets are in the dns.cap file? 38
<img width="821" height="73" alt="2" src="https://github.com/user-attachments/assets/81cd1b70-40bc-47fb-ab82-e806af60ed53" />


     wc -l : can quickly identify how many packets are in the capture.


How many A records are in the capture? (Including responses) 6

<img width="806" height="354" alt="Screenshot 2026-01-27 165327" src="https://github.com/user-attachments/assets/6ca7a086-d8dc-43cd-95d8-d5b143feb098" />

    -Y : display filter.


Which A record was present the most? GRIMM.utelsystems.local

<img width="803" height="221" alt="Screenshot 2026-01-27 165807" src="https://github.com/user-attachments/assets/2187784b-4496-44c2-b30c-32584d6f31f9" />

    -T fields -e dns.qry.name : displays domain name.


#
# **DNS Exfil**

How many packets are in this capture? 125

<img width="657" height="75" alt="Screenshot 2026-01-27 175350" src="https://github.com/user-attachments/assets/59ee0d9d-c6b3-4f35-a669-87c9c8ad0f56" />


How many DNS queries are in this pcap? (Not responses!) 56
<img width="887" height="73" alt="Screenshot 2026-01-27 175429" src="https://github.com/user-attachments/assets/9939eedd-0138-45ed-af2a-f344a98f1dff" />


      "dns.flags.response == 0" : shows only the query.

What is the DNS transaction ID of the suspicious queries (in hex)? 0xbeef

<img width="612" height="46" alt="Screenshot 2026-01-27 175641" src="https://github.com/user-attachments/assets/4fb40324-b1ed-4bf6-9b66-e90bae45c760" />


<img width="1055" height="474" alt="Screenshot 2026-01-27 175714" src="https://github.com/user-attachments/assets/7c6f28f9-5590-43a1-bd10-400f3b2f4236" />


What is the string extracted from the DNS queries? MZWGCZ330RUDC427NFZV65BQ0VTWQX3XNF2GQMDVG5PXI43IGRZGWIL5


<img width="1053" height="543" alt="Screenshot 2026-01-27 175918" src="https://github.com/user-attachments/assets/329455a3-c5bd-4b0f-8716-027936ddf2ca" />

<img width="1052" height="546" alt="Screenshot 2026-01-27 180056" src="https://github.com/user-attachments/assets/3dc4228d-8cd5-42bb-8c07-b9af6ed76d21" />


      cut -d "." -f1 : cuts the period "." and specifies that we only want to keep only the first field from the split.

# What is the flag?
TO GET THE FLAG:
<img width="1053" height="96" alt="3" src="https://github.com/user-attachments/assets/9ec4a360-a81d-4657-9802-143d4d226361" />

      tr -d "\n" : removes newline characters from the final output, concatenating all results into a single line.


<img width="1062" height="585" alt="Screenshot 2026-01-27 180818" src="https://github.com/user-attachments/assets/04ab8673-5384-4dde-8a86-85f9eaf22652" />

