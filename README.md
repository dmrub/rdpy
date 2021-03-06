# RDPy
RDPy is a python script for auditing the security of a Remote Desktop
configuration.

This project borrows heavily from two related works:

- http://labs.portcullis.co.uk/application/rdp-sec-check/
- http://troels.arvin.dk/code/nagios/check_x224

RDPy started life as an attempt to avoid wrapping rdp-sec-check so that multiple
hosts could be scanned without interaction. It appears that rdp-sec-check now
supports a hosts file that solves this issue. The second reason for creating
RDPy was to learn a little more about the Remote Desktop protocol and have a
tool written in Python. Both of these goals were met (as evidenced by the 
extensive but highly unecessary comments in the source) and this project has
received little love since. It was originally written in 2013 but I've just now
gotten around to releasing it.

This project is being used for testing but is not guaranteed to be bug-free. If
you have any problems, feel free to open an issue.

# Example

~~~
# ./rdpy.py 192.0.2.1
Target:      192.0.2.1
Port:        3389 (default)
Host Status: UP

[+] Supported Protocols:
	Standard RDP Security
	TLS 1.0, 1.1 or 1.2 Security
	Hybrid (TLS + CredSSP) Security

[+] Supported Encryption Methods:
	40 Bit
	128 Bit
	56 Bit

[+] Supported Encryption Levels:
	Client Compatible

[+] Security Issues:
	NLA supported but not mandated DoS
	SSL supported but not mandated MitM
	Weak RDP encryption supported

[+] Server Messages:
	(None)

--------------------------------------------------

Total Hosts:     1
Listening Hosts: 1
~~~
