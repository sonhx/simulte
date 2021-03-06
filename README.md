SimuLTE
=======

LTE user plane simulation model, compatible with the INET Framework.


Features
--------

General

- eNodeB and UE models
- Form-based configuration editor

PDCP-RRC

- Header compression/decompression
- Logical connection establishment  and maintenance 

RLC

- Multiplexing/Demultiplexing of MAC SDUs
- UM, (AM and TM testing) modes

MAC

- RLC PDUs buffering
- HARQ functionalities (with multi-codeword support)
- Allocation management
- AMC
- Scheduling Policies (MAX C/I, Proportional Fair, DRR)

PHY

- Heterogeneous Net (HetNets) support: Macro, micro, pico eNbs
- Channel Feedback management
- Dummy channel model
- Realistic channel model with
  - cell interference
  - path-loss
  - fast fading
  - shadowing 
  - (an-isotropic antennas - work in progress)

Other

- X2 communication support
- (Relay support - work in progress)
- Distributed Antenna System - DAS (Testing)

Applications

- VoIP
- Gaming
- Trace Based traffic


Limitations
-----------

- only the radio access network is modeled, the EPC network is not 
  (in the model eNodeB directly connects to the internet, there's no 
  explicit S-GW and P-GW, no GTP tunneling etc.)
- User Plane only (Control Plane not modeled)
- FDD only (TDD not supported)
- no EPS bearer support – note: a similar concept, "connections", has 
  been implemented, but they are neither dynamic nor statically 
  configurable via some config file
- radio bearers not implemented, not even statically configured radio 
  bearers (dynamically allocating bearers would need the RRC protocol, 
  which is Control Plane so not implemented)
- handovers not implemented (no X2-based handover, that is; S1-based 
  handover would require an S-GW model)

You might also have a look at the 4GSim project (http://github.com/4gsim/4Gsim)
which concentrates on simulating other aspects of LTE, namely,
control plane and backhaul.


Using the configuration editor
------------------------------

SimuLTE also contains a form-based configuration editor to edit the most 
often used simulation parameters. To use it, right-click an Ini file, and choose
'Open With | SimuLTE Configuration Editor' from the context menu. Try it on 
'simulations/demo/gui.ini'.
