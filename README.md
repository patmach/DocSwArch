# Documentation #
## Roadmap ##
- obsah dokumentace
- tabulka, jak má který stakeholder používat tuto dokumentaci
- nejsem si jistý, jestli je tato sekce nutná (bylo to v přednášce, ale řekl bych že se to spíš týká až větších projektů)

## Equipment Monitoring System overview ##
### Purposes of the system ###
Medical monitoring devices are some of the most important  pieces of equipment in a health  care  facility. Without  reliable monitoring equipment  we  could  easily miss a piece of significant  information.

Monitoring system allows to ease  identify, tracking and monitoring equipment and keep  the  information  inside  them  secure.
### Functional requirements ###
- ***Equipment tracking*** - the system keeps track of medical devices connected to the hospital network and is able to fetch their information via API.
- ***Equipment overview*** - all tracked devices are shown in the overview with their current state.
-  ***Equipment detail*** - further details about medical device such as location and its state are available for the system users.
- ***Reservation system*** - any medical device can be reserved in different time slots, each device has chronological list of reservations shown in the device detail.
- ***Examination history*** - the system maintains history of all examination results made on tracked medical device and makes it available to the user as part of the device detail.
 - ***Authorization levels*** - user access to medical devices must be authorized
 
### Stakeholders/users ###
Following people are directly or indirectly involved in this system:

 - ***Hospital management*** - is  interested in the  statistics - how  frequently  is  the  equipment  used and how  often  is  broken. Also needs to know  which  employee  uses  which  equipment and how  many 
   examinations  every  employee  performed.
 - ***Doctor*** - get quicker  access to examinations  results, have  better  overview of equipments and their state.
 - ***Nurse*** - know  reservations on equipment, create  reservations, see  equipment state.
 - ***Patient*** - wants to be  sure  that  the  examination  data are stored  securely  but are also  available  for  the  medical  staff.
- ***Development team***  - individuals  working  together to deliver  the  final  product, they  need as much  details as possible to successfully  implement  the  system.
- ***Product owner*** - responsible  for  the  product  resulting  from  the  work of  the  Development Team, also  working  with  the  manager to determine  what  features  will  be in the  product  release.
- ***Maintenance team*** - people  maintaining  the  whole  infrastructure of the  system, they are responsible  for  system  accessibility
- ***IT technician*** -  maintain and configure  hardware and database, provide a support  from a database  side

### Constraints ###
Not all medical devices are automatically connected to the network and tracked by the system. New devices are manually added to the infrastructure by IT technicians.

Access to the system is restricted to authenticated users only.

### Technical details ###
System uses the hospital's central user database for authentication and authorization (may also possibly use some central auth service used across all hospital IT systems).

Already fetched information such as examination results are always stored to the system database, but in case of database problems, direct communication with devices over network is used to get the required information. Works also vice-versa if devices are not reachable.

## Viewpoints ##
### Documentation of viewpoints ###
- v této dokumentaci se zaměřujeme na dva viewpointy - Module a C-and-C
- popis toho, jak jsou dokumentované (opět si nejsem jistý, jak moc je to tu nutné)

### Module viewpoint ###
[Module viewpoint](viewpoints/moduleViewpoint.md)

### Component and connector viewpoint ###
[Component and connector viewpoint](viewpoints/cacViewpoint.md)