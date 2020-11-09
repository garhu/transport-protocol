Approach:
First we realized that with the given code, we needed to move away from json and find someway to easily send bytes on the network. We found the struct library would be the best approach and changed that as the method to send data. After that, we implemented a set approach to track duplication of messages. Then, we implemented a simple try and go approach of sending packets. We realized that it would be the easiest way, and would be very reliable but not high preformance if there was a slow network. We tried optimizing this, but couldn't. Also, because we realized we had no way to gaurentee the EOF packet, we hard coded a multiple sending of the packet and EOF ack.

Challenges:
Our implementation was simple, but it struggles when the bandwith is limited. This was obvious when analyzing the last basic test. We changed our code, but couldn't succeed with making it work. We mainly tried using faster ways of sending messages or using a slower timeout. Also, we struggled with the options of implementation. Being allowed so many options to solve the problems associated with transport, we took a while to choose our desired implementation.

Testing:
We used netsim and nettest extensively. Also, nettest --live was very good when we had errors in compiling. Setting netsim to slower bandwiths helped us see where we went wrong with certain things.
