# Earthquake Ethernet Inspector Low-Level Protocol

This protocol is used for communication between inspectors and middleboxes.

NOTE: the protocol is *not* used for orchestrator.

## ZeroMQ frame
    
    +------------------------------+
    |         JSON metadata        |
    +------------------------------+
    |         Ethernet Frame       |
    +------------------------------+


### JSON metadata
Middlebox -> Inspector:

 - `id`(int): Ethernet frame ID

Middlebox <- Inspector:

 - `id`(int): Ethernet frame ID
 - `op`(string): either one of {`accept`, `drop`, `modify`}. If `op` is not `modify`, the Ethernet Frame payload *must* be ignored.
 
