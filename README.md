# RTSP/RTP Video Streaming
Implemented an RTSP/RTP-based video streaming client with support for control signaling, state management, and real-time packet handling.

## 🌟Features
* RTSP request handling (SETUP, PLAY, PAUSE, TEARDOWN)
* RTP packet decoding and video frame reconstruction
* Real-time video streaming over UDP
* Client-side state management
* Synchronization between RTSP control flow and RTP data stream

## ✏️My Contributions
### Client.py
sendRtspRequest
- For each button:
  - update the RTSP sequence number
  - write the RTSP request to be sent
  - keep track of the sent request
  
parseRtspReply
- For each sent request: update RTSP state

openRtpPort
- Create a new datagram socket to receive RTP packets from the server
- Set the timeout value of the socket
- Bind the socket to the address using the RTP port given by the client 

### RtpPacket.py
encode
- Fill the header bytearray with RTP header fields
- Store the constructed header in the object
- Get the payload from the argument

## ⚙️How to Run
Tested on Python version 3.14.4

**To begin:**
1. Clone this GitHub Repository
2. Open two terminals on your machine 
3. For each terminal: navigate to the project directory using the `cd` command 

### Run the Server
Terminal 1:
```python Server.py server_port```

### Run the Client
Terminal 2:
```python ClientLauncher.py server_host server_port RTP_port video_file```

**Argument descriptions:**
- `server_host`: IP address of the server (e.g., 127.0.0.1 for localhost)
- `server_port`: Port used for RTSP communication
- `rtp_port`: Port used to receive RTP packets
- `video_file`: Name of the video file (e.g., `movie.Mjpeg`)

**Note:** the movie.Mjpeg video file is included in this repository for ease of testing

## 💡What I Learned
This project strengthened my ability to debug distributed systems, particularly in a networking context where multiple components must work together seamlessly.

Key takeaways:
- **Systematic debugging:** Even when both the client and server appear to be running, issues can still occur in the data path (e.g., RTP packets not being received), requiring step-by-step isolation of the failure.
- **Environment and file dependencies:** Small setup issues—such as using the wrong working directory—can break functionality even when the code itself is correct.
- **Networking pitfalls:** Connectivity issues can stem from incorrect IP addresses, firewall restrictions, or the client and server not being on the same network.
- **Resource management:** Port-related errors often occur when previous processes are still running, which signifies the importance of properly shutting down sockets and cleaning up resources.

Overall, this project taught me that debugging networked applications requires careful attention to both code and system-level details.

