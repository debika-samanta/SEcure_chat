# Secure Chat Application

This project involves creating a peer-to-peer secure chat application using DTLS 1.2 and UDP protocols. The application enables secure communication between two peers, Alice and Bob, in a way similar to HTTPS but in a peer-to-peer paradigm. The project also includes tasks related to secure communication, downgrade attacks, and active MITM attacks.

## Features

- Peer-to-peer chat using DTLS 1.2 and UDP
- Handshake and secure communication setup
- Session resumption using session tickets
- Downgrade and MITM attack simulations
- Certificate handling and verification

## Prerequisites

- C/C++ Development Environment
- OpenSSL
- Wireshark (for capturing Pcap traces)
- `tcpdump` (for capturing Pcap traces)
- Basic understanding of DTLS and TLS

## Setup and Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/secure-chat-app.git
cd secure-chat-app
```

TASK 1: How to create keys and certificates
	STEP 1: Commands given in the report to create the keys, csr's, ceritificates, verification for Root CA, Int CA, Alice, Bob
                                                                        _________________________________________________
                                                                       |                                                 |
                                                                       |  NOTE- Execute these Commands on LOCALMACHINE   |
                                                                       |_________________________________________________|


TASK 2: How to execute secure_chat_app_localhost.cpp

	STEP 1 Open two terminals in the source folder "secure chat

	STEP 2 Compile the code using the command 
		g++ -o secure_chat_app_localhost secure_chat_app_localhost.cpp -lssl -lcrypto

	STEP 3 Execute the server By using the command 
		./secure_chat_app -s

	STEP 4 Execute the client By using the command
		./secure_chat_app -c bob1



---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



                                                                        _______________________________________
                                                                       |                                       |
                                                                       |  NOTE- Execute these Commands on VM   |
                                                                       |_______________________________________|

TASK 2: How to execute secure_chat_app.cpp

	STEP 1 Open two terminals in the source folder "secure chat

	STEP 2 Compile the code using the command 
		g++ -o secure_chat_app secure_chat_app.cpp -lssl -lcrypto

	STEP 3 Execute the server By using the command 
		./secure_chat_app -s

	STEP 4 Execute the client By using the command
		./secure_chat_app -c bob1


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



TASK 3:	
	
	STEP 1: Poison the DNS :-  bash ~/poison-dns-alice1-bob1.sh

	STEP 2: on TRUDY container
			to compile the code
			by Using 	g++ secure_chat_interceptor.cpp -o secure_chat_interceptor -lssl -lcrypto

	STEP 3: on TRUDY container
			to compile the code
			by Using	./secure_chat_interceptor -d alice1 bob1

	STEP 4: execute the server on BOB container
 			by Using 	./secure_chat_app -s

	STEP 5: execute the server on BOB container
 			by Using 	./secure_chat_app -c bob1



---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

TASK 4:
	
	STEP 1: Poison the DNS :-  bash ~/poison-dns-alice1-bob1.sh

	STEP 2: on TRUDY container
			to compile the code
			by Using 	g++ secure_chat_active_interceptor.cpp -o secure_chat_active_interceptor -lssl -lcrypto

	STEP 3: on TRUDY container
			to compile the code
			by Using	./secure_chat_active_interceptor -m alice1 bob1

	STEP 4: execute the server on BOB container
 			by Using 	./secure_chat_app -s

	STEP 5: execute the server on BOB container
 			by Using 	./secure_chat_app -c bob1


