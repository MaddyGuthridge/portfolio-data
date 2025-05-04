# Flapi

Flapi is a remote control system for the digital audio workstation FL Studio.
It works by interfacing with FL Studio's MIDI Controller Scripting API, sending
system-exclusive MIDI messages which are then processed by a Python server
running within FL Studio.

This framework allows for advanced control over FL Studio, which can be used to
build applications that offer advanced control over almost all aspects of FL
Studio.

## Protocol design

When building Flapi, I designed a protocol for bidirectional communication between the Flapi server, running within FL Studio's isolated scripting environment and Python clients. This was an interesting challenge due to the numerous design constraints of the interface.

* FL Studio's Python environment makes use of [PEP 578 Audit Events](https://docs.python.org/3/library/audit_events.html) to minimise the attack surface of scripts running within FL Studio. As such, network and socket connections, file-system access and the spawning of subprocesses are all disabled. As such, all communication in the protocol is done through system-exclusive MIDI messages.
* The Windows MIDI API [requires applications to pre-allocate a buffer](https://learn.microsoft.com/en-us/windows/win32/api/mmeapi/nf-mmeapi-midiinaddbuffer) for incoming MIDI messages, meaning that messages that are too large are either ignored, or (in poorly-written applications) cause a buffer overflow. To work with most software, the messages cannot exceed 1024 bytes in length, and so the protocol defines a chunking system where a Flapi message can be split across an arbitrary number of MIDI messages.
* While my code provides a server and a simple Python client, I wanted the project to be accessible to other software, for example, if another developer wished to create a remote control interface using C++. As such, the protocol is designed to be mostly language-agnostic, with the ability for clients to register custom code to be executed server-side, allowing for deeper integration and improved performance.

Within these constraints, I created and refined a clearly-defined protocol for the project to use, demonstrating my design skills and ability to work in situations with complex requirements.