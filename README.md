
# Unitools

`unitools` is a cohesive collection of utility tools designed for Python 3, encapsulating various utility functions developed over the years. Given the absence of such tools in earlier times, `unitools` serves as a treasure trove for developers seeking a unified solution for various tasks.

## Installation

You can install `unitools` via pip:
```bash
pip install unitools
```


## Modules

`unitools` offers multiple modules, each tailored for a specific purpose. Below is a description of a few key modules:

### ICMPv4 Module

The `ICMPv4` module offers a way to generate and handle ICMP (Internet Control Message Protocol) echo requests, commonly known as "pings". It has been built to be cross-platform compatible, seamlessly operating on both Windows and Linux.

#### Features

- **Ping Utility**: Send ICMP echo requests and retrieve the response.
- **Dynamic Packet Creation**: Build ICMP packets on the fly based on the operating system.
- **Response Handling**: Decode ICMP responses and provide a structured representation.

#### Usage

```python
from unitools.ICMPv4 import Request

icmp_request = Request(address="8.8.8.8")
response = icmp_request.ping()

print(response)
```

#### Methods
-   **ping**: Initiates an ICMP request and awaits its response.
-   **create_socket**: Establishes the required socket for ICMP communication.
-   **create_icmp_packet**: Constructs the ICMP packet ready for transmission.
-   **send_on_socket**: Sends the constructed ICMP packet.

#### ICMPv4.Response

An inner class, `Response`, embodies the ICMP reply, furnishing details like the responder's IP address, byte size of the packet, round-trip time, and TTL (Time-to-Live).

### TCPv4 Module

The `TCPv4` module provides tools to check the reachability of TCP ports. It offers a "ping" on a TCP port and an extended ping functionality with multiple packets, delivering insights about the responsiveness and reliability of a TCP service.

#### Features
- **TCP Ping**: Test if a specific port on a host is reachable.
- **Extended TCP Ping**: Transmit multiple packets to ascertain the consistency and average response time.
- **Response Parsing**: Parse and present the ping responses in a structured manner.

#### Usage
```python
from unitools.TCPv4 import Request

# Initialize with target host and port
request = Request(host='example.com', port=80)

# Single TCP Ping
response = request.tcp_ping()
print(response)

# Extended TCP Ping with 5 packets
responses = request.tcp_ping_extended(ping_count=5)
print(responses)
```

#### Methods

-   **tcp_ping**: Send a TCP request to the provided host and port and await its response.
-   **tcp_ping_extended**: Transmits multiple TCP pings and collates the responses.

#### TCPv4.Response & TCPv4.Responses

`Response` captures the outcome of a single TCP ping, detailing if the port was reachable and the latency. `Responses`, on the other hand, aggregates results from the extended ping, offering insights like average latency and packet loss percentage.

## Contribute

Contributions to `unitools` are always welcome. Feel free to submit pull requests or raise issues.

## License
[MIT License](https://github.com/MrTwister96/unitools/blob/main/LICENSE)