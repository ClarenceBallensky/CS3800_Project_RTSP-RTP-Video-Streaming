# RTSP/RTP Video Streaming
Implemented an RTSP/RTP-based video streaming client with support for control signaling, state management, and real-time packet handling.

## Features
* RTSP request handling (SETUP, PLAY, PAUSE, TEARDOWN)
* RTP packet decoding and video frame reconstruction
* Real-time video streaming over UDP
* Client-side state management
* Synchronization between RTSP control flow and RTP data stream

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
- Create a new datagram socket to receive RTP packets from the server
- Set the timeout value of the socket
- Bind the socket to the address using the RTP port given by the client 

### RtpPacket.py
encode
- Fill the header bytearray with RTP header fields
- Store the constructed header in the object
- Get the payload from the argument

## How to Run
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

