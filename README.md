# Reliable-Datagram-Protocol
## RDP sender and receiver implement reliable file transfer over UDP.

RDPS.c - sender code

RDPR.c - receiver code

Custom packet headers include:
- Magic Type (protocol)
- Type
- Seq 
- Ack #
- Payload
- Window size


SENDER:

1. File is broken down into packet size pieces, header is attached and packet is sent.
2. Sender always sends as many but no more than 5 packets in one go, these packets are stored in tosend[][] waiting ACK.
3. When ACK received, all packets with lower seq no are discarded, and replaced by newer packets.
4. These newer packets are then sent.

RECEIVER:

1. If seq number is in order, data is consumed straight away.
2. If seq number not in order, packet is stored in space[][] and window size decreased. Packet will be consumed in due time.




