# Module viewpoint #
## Overview ##
- krátký okec o čem to je

## Decomposition viewpoint ##
### Presentation ###

### Domain ###

### Data Access ###

## Usage viewpoint ##

For greater clarity, we split the usage viewpoint into three more detailed parts.

### Equipment ###

[PDF version](img/EquipmentUsageViewpoint.pdf)

![Image description.](img/EquipmentUsageViewpoint.png)

This viewpoint shows dependencies among modules used when the user wants to get data related to the equipment.

Submodules from the UI module use the Equipment Services module, specifically the HTTP connector submodule which after ~~?calls or uses?~~ List equipments, Get actual state or Get detail information submodules. Those submodules then use the Equipment submodule in the Model module, which in turn uses the Equpment gateway submodule in the Data Access module. Equipment Services module also uses the Authorization service module, which then uses the User module. 

> Information about the user can be recieved from the database containing data about users (e.g. user credentials). Information about the equipment can be recieved from the database containing data about equipment. In case when data about the related equipment is not in the database, the Data Access submodule can request them directly from the application via Equipment API.

### Reservation ###

[PDF version](img/ReservationUsageViewpoint.pdf)

![Image description.](img/ReservationUsageViewpoint.png)

This viewpoint shows dependencies among modules used when the user wants to get data related to the reservations. It has basically the same structure as the viewpoint above. 

Submodules from the UI module use the Reservation Services module, specifically the HTTP connector submodule which after ~~?calls or uses?~~ Show or Create submodules, which then use the Reservation submodule in the Model module, which in turn uses the Reservation gateway submodule in the Data Access module. The Create module also ~~"is-allowed-to-use" or uses~~ the User submodule in the Model module (because the reservations are created for specific users). Reservation Services module also uses the Authorization service module, which then uses the User module.

> The Reservation Services provides two functions – one which shows current reservations for given equipment and another which allows the creation of new reservations 
> The Create service is also the only one which directly interact with the User model because the reservations are created for specific users. 

### Examination ###

[PDF version](img/ExaminationUsageViewpoint.pdf)

![Image description.](img/ExaminationUsageViewpoint.png)

This viewpoint shows dependencies among modules used when the user wants to get data related to the examinations. 

Submodules from the UI module use the Examination Services module, specifically the HTTP connector submodule which after ~~?calls or uses?~~ List examinations, Get or Get examination detail submodules. Those submodules then use the Examination submodule in the Model module, which in turn uses the Examination gateway submodule, which "is-allowed-to-use" the Equipment gateway (in the case when data are not found in the database). Examination Services module also uses the Authorization service module, which then uses the User module. 

> Public API sends request to appropriate examination service. Services work with model for examination and user through an Authorization service. User information will be got through user gateway from external database. Examination data will be got through examination gateway from application database. If examination detail cannot be yet found in the application database, data access layer will connect to Equipment API through Equipment gateway. 
