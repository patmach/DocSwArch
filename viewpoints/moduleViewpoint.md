# Module viewpoint #
## Overview ##
- krátký okec o čem to je

## Decomposition viewpoint ##
### Presentation ###

### Domain ###

### Data Access ###

## Usage viewpoint ##
### Equipment ###

[PDF version](img/EquipmentUsageViewpoint.pdf)

![Image description.](img/EquipmentUsageViewpoint.png)

This viewpoint shows how the system should be structured as a set of code units when the user wants to see information about the equipment. Public APIs send a request to the corresponding examination service, which then comunicates with the Data Access Layer through the Model.  

In case the user requires some data about the equipment, he must be first authorized (via Authorization service).  

Information about the user can be recieved from the database containing data about users, via a HTTP response (e.g. user credentials). Information about the equipment can be recieved from the database containing data about equipment (via a HTTP response). In case data about the related equipment is not in the database, the Data Access submodule can request them directly from the application via Equipment APIs.

### Reservation ###

[PDF version](img/ReservationUsageViewpoint.pdf)

![Image description.](img/ReservationUsageViewpoint.png)

### Examination ###

[PDF version](img/ExaminationUsageViewpoint.pdf)

![Image description.](img/ExaminationUsageViewpoint.png)
