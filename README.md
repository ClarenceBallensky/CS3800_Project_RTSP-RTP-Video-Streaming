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

### RtpPacket.py
encode
- Fill the header bytearray with RTP header fields
- Store teh constructed header in the object
- Get the payload from the argument

## Setup
- 2 Windows PowerShell terminals
`cd C:\Users\prize\.vscode\CS3800_Project_RTSP-RTP-Video-Streaming`

### Server
`python Server.py 8554`
<img width="1068" height="56" alt="image" src="https://github.com/user-attachments/assets/45eeeb64-2d07-4b41-857c-42cbf65907d5" />
### Client 
`python ClientLauncher.py 127.0.0.1 8554 5005 movie.Mjpeg`
<img width="1487" height="66" alt="image" src="https://github.com/user-attachments/assets/d7413350-1fa2-42a9-8cf3-f7ae2c1ed930" />

