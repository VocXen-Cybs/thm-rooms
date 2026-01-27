***Reading PCAP Files*** 
#
How many packets are in the dns.cap file? 38
<img width="810" height="766" alt="Screenshot 2026-01-27 165210" src="https://github.com/user-attachments/assets/21e76eff-2d97-48c0-b507-5f3a4e57adbb" />

     wc -l : can quickly identify how many packets are in the capture.


How many A records are in the capture? (Including responses) 6
<img width="821" height="767" alt="Screenshot 2026-01-27 165327" src="https://github.com/user-attachments/assets/449f9979-8a52-4d77-be64-62afc533d4fe" />

    -Y : display filter.


Which A record was present the most? GRIMM.utelsystems.local
<img width="813" height="767" alt="Screenshot 2026-01-27 165807" src="https://github.com/user-attachments/assets/fd613547-0199-4028-b930-86ede36999cc" />

    -T fields -e dns.qry.name : displays domain name.


#
**DNS Exfil**
#
How many packets are in this capture? 125
<img width="657" height="101" alt="Screenshot 2026-01-27 175350" src="https://github.com/user-attachments/assets/73e45941-5684-4379-9cfe-0f30e00c0028" />

How many DNS queries are in this pcap? (Not responses!) 56
<img width="887" height="100" alt="Screenshot 2026-01-27 175429" src="https://github.com/user-attachments/assets/435e9bdc-d252-4a56-9331-b4839593303f" />

      "dns.flags.response == 0" : shows only the query.

What is the DNS transaction ID of the suspicious queries (in hex)? 0xbeef
<img width="612" height="46" alt="Screenshot 2026-01-27 175641" src="https://github.com/user-attachments/assets/df47492c-8c8e-485a-a946-39651a903b3f" />
<img width="1055" height="522" alt="Screenshot 2026-01-27 175714" src="https://github.com/user-attachments/assets/a392041c-5fdb-45a5-b256-c102a07c2ef4" />



What is the string extracted from the DNS queries? MZWGCZ330RUDC427NFZV65BQ0VTWQX3XNF2GQMDVG5PXI43IGRZGWIL5
<img width="1053" height="574" alt="Screenshot 2026-01-27 175918" src="https://github.com/user-attachments/assets/90f0579f-0a97-4bc4-a957-d1826290bb55" />


<img width="1052" height="569" alt="Screenshot 2026-01-27 180056" src="https://github.com/user-attachments/assets/1d94d00f-8952-4491-856e-c8aaf6c42684" />

      cut -d "." -f1 : cuts the period "." and specifies that we only want to keep only the first field from the split.

What is the flag?
TO GET THE FLAG:
<img width="1053" height="154" alt="Screenshot 2026-01-27 180309" src="https://github.com/user-attachments/assets/552cb43c-3fee-4524-9618-6e3a50a76f46" />

      tr -d "\n" : removes newline characters from the final output, concatenating all results into a single line.

<img width="1062" height="585" alt="Screenshot 2026-01-27 180818" src="https://github.com/user-attachments/assets/1b370809-8167-4d77-8ae8-5f8398c82c80" />
