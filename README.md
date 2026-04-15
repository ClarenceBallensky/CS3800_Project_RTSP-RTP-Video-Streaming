# RTSP/RTP Video Streaming
## My Contributions
### Client.py
sendRtspRequest
- For each button:
  - update the RTSP sequence number
  - write the RTSP request to be sent
  - keep track of the sent request
  
parseRtspReply
- For each sent request: update RTSP state

openRtpPort
- Create a new datagram socke to receive RTP packets from the server
- Set the timeout value of the socket
- Bind the socket to the address using the RTP port given by the client 

