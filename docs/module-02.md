# Network Models

Network models are frameworks for data organisation, 
helping us understand how data moves through devices
within a network. There are two available models,
OSI (Open Systems Interconnection) and 
TCP/IP (Transmission Control Protocol/Internet Protocol).


## Protocol Layering

### Protocol

A protocol is a set of rules that the sender and receiver agree on so that they can understand each other.
For simple communication, one protocol is enough, 
but nowadays with complex communication (computers have many processes running needing data, etc.), 
we need to layer different protocols together in order to redirect and transform data for appropriate needs.
This is called **protocol layering/modularity**.

### Model Layers

Each layer contains several protocols, 
responsible for translating data into different forms.

<figure style="height:50%; width:50%">
``` mermaid
flowchart TB
    subgraph TCP/IP Protocol Suite
        AA[Application]
        TT[Transport]
        NN[Network]
        DD[Data link]
        PP[Physical]
    end

    subgraph OSI
        A[Application]
        P[Presentation]
        S[Session]
        T[Transport]
        N[Network]
        D[Data Link]
        P[Physical]
    end
```
</figure>

### Addressing

Layers in the protocols correspond to a part in an *address*.
For TCP/IP, we have

<figure markdown>
| packet name | layer | address | example | 
| ----------- | ----- | ------- | ------- |
| message     | application | names | `www.bcit.ca` |
| segment </br> user datagram | transport | port numbers | http (port 80) |
| packet </br> datagram | network | logical address | your IP |
| frame | data link | link-layer addresses | MAC ID | 
| bits  | physical layer | -- | -- |
</figure>

## More on the TCP/IP Protocol Suite

TCP/IP Protocol Suite has five layers (1), each of which is responsible for:  
1. **Application**: Enabling user access to the network (2).  
2. **Transport**: Delivers the entire message between *processes*.
   In an address, this would be the port.  
3. **Network**: Delivers packet between *hosts*.  
4. **Data link**: Delivers frames from one station to the next
   without errors. Has two sublayers: 
   Data Link Control (DLC) for framing, error detection and correction (3) of frames/bits
   and Medium Access Control (MAC), where the physical hardware address (4) and medium access
   control resides.  
5. **Physical**: Coordinates functions for bit transmission over a medium.
   Responsible for bit representation and encoding types.  
{ .annotate }

1. Note that there is a difference between TCP/IP model and the TCP/IP Protocol Suite,
   akin to an abstract idea and its implementation.

2. HTTP, FTP, SMTP, `telnet`, etc.

3. See [Hamming Codes](appendix.md/#hamming-codes) 
   and [Signal-to-noise ratio](https://en.wikipedia.org/wiki/Signal-to-noise_ratio). 

4. Most devices nowadays have two MAC addresses, one for Wi-Fi, and another for Bluetooth. 

!!! warning "The "Physical" in TCP/IP"

    We can think of the "Physical" here as physical properties
    that is used to represent information rather than the actual
    medium the information travels through.

!!! note "Chronologics of the two models"
    
    I think in class, Dr. Huang implied that OSI was based on TCP/IP,
    along the lines of

    > OSI's application, presentation and session layers were merged
    > into the single TCP/IP application layer.

    I don't know the basis of this, but Wikipedia says that 
    [TCP/IP](https://en.wikipedia.org/wiki/Internet_protocol_suite) (1960s) came
    before [OSI](https://en.wikipedia.org/wiki/OSI_model) (1970s).

