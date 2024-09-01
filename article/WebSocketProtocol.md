# WebSocket Protocol Lifecycle

![alt text](https://github.com/pachouri/Architecture-and-System-Design/blob/main/diagram/Websocket.gif?raw=true)

**1\. Connection Establishment (Handshake)**

\- The client initiates a connection by sending an HTTP request to the server with the "Upgrade: websocket" header, indicating the desire to switch the protocol from HTTP to WebSocket.

\- The server responds with an HTTP 101 status code, indicating that the protocol is being switched to WebSocket.

\- Both the client and server perform a handshake to confirm the WebSocket connection is established.

**2\. Data Transmission**

\- Once the connection is established, the client and server can exchange data in full-duplex mode. This means data can be sent and received simultaneously.

\- Data frames (messages) are exchanged between the client and server. These frames can be text, binary, or control frames.

\- The connection remains open and active as long as both the client and server continue to communicate.

**3\. Ping/Pong Frames**

\- To ensure the connection is still alive, either the client or server can send a "ping" frame.

\- The receiving end responds with a "pong" frame, confirming that the connection is still active.

**4\. Connection Closure**

\- Either the client or server can initiate the closing handshake by sending a "close" frame, indicating the desire to terminate the connection.

\- The receiving party acknowledges by sending a "close" frame in response.

\- After the acknowledgment, the connection is considered closed, and both parties can release any resources associated with the WebSocket connection.

**5\. Connection Termination**

\- After the connection is closed, both the client and server stop sending and receiving data.

\- Any remaining data frames that were not sent or received before the close frame may be lost unless handled explicitly.

\- The WebSocket connection lifecycle ends with the termination of the connection.

# WebSocket Protocol: where to use

The WebSocket protocol is best used in scenarios where real-time, low-latency, and bi-directional communication between a client and server is required. Here are some situations where WebSocket is ideal:

**1\. Real-Time Applications**

\- Chat Applications : WebSocket enables instant messaging, making it perfect for chat apps where users need to send and receive messages in real time.

\- Online Gaming : Multiplayer games require real-time communication for actions like player moves and game state updates.

\- Collaborative Tools : Applications like Google Docs, where multiple users are editing a document simultaneously, benefit from real-time updates.

**2\. Live Data Feeds**

\- Financial Market Data : Stock prices, forex rates, and other financial instruments require real-time updates that WebSocket can efficiently deliver.

\- Sports Scores : WebSocket can push live sports scores and updates to users as events happen.

\- News Feeds : Real-time news updates, including breaking news and live reporting, can be streamed to users via WebSocket.

**3\. IoT (Internet of Things)**

\- Device Monitoring : IoT devices often need to send real-time data, such as sensor readings, to a central server for monitoring and control.

\- Home Automation : WebSocket allows real-time control and status updates for smart home devices.

**4\. Notifications**

\- Push Notifications : WebSocket can be used to send push notifications to clients as soon as an event occurs, such as an incoming message or an alert.

\- Server Alerts : Real-time alerts from servers about system status, warnings, or errors can be delivered using WebSocket.

**5\. Streaming Data**

\- Live Video/Audio Streaming : For applications like live broadcasting or peer-to-peer video/audio communication, WebSocket can be used to manage the stream and control messages.

\- Real-Time Analytics : Dashboards that display live analytics, such as website traffic or system metrics, can use WebSocket to receive data continuously.

**6\. Low-Latency Applications**

\- Financial Trading Platforms : Trading platforms where milliseconds matter require low-latency data exchange, which WebSocket can provide.

\- Remote Control Applications : Applications where users need to control remote devices in real time, such as drones or robots, can benefit from the low latency of WebSocket.
