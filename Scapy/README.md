# Bi0s Scapy

### Biz44e : 

```
from scapy.all import *

f=rdpcap('bizz.pcap')
b = ''

for i in f[ICMP]:
	if len(i) == 3528:
		b+=str(i)[329:-1]
	if len(i) == 3526:
		b+=str(i)[411:-1]
	if len(i) == 3524:
		b+=str(i)[451:-1]
	
with open("final.zip", "wb") as g:
	g.write(bytes.fromhex(b))
	g.close()
```

### Its My Pal :

```
from scapy.all import *

f=rdpcap('1.pcap')
b=''

for i in f[ICMP]:
    if i[IP].src == "192.168.1.200":
        b+=str(i)[0:0]
	    b+=str(i)[42:]

with open("final.zip", "w") as g:
    g.write(b)
    g.close()
```

### Orcish :

```
from scapy.all import *

f=rdpcap('data.pcap')
b=''

for i in f[ICMP]:
    if i[IP].src == "10.136.255.127":
	#0020 offset and 2 in position => 20 + 2 = 22
	#Convert hex 22 to bytes.
	# U will get 34 bytes.

        b+=str(i)[34] 

with open("final.gif", "w") as g:
    g.write(b)
    g.close()
```
