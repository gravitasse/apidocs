EthernetPM Model Objects
=============================================================

*config/EthernetPM*
------------------------------------

- Multiple objects of this type can exist in a system.

+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| **PARAMETER NAME** | **DATA TYPE** |        **DESCRIPTION**         | **DEFAULT** |        **VALID VALUES**        |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| Resource **[KEY]** | string        | Resource identifier            | N/A         | StatUnderSizePkts,             |
|                    |               |                                |             | StatOverSizePkts,              |
|                    |               |                                |             | StatFragments,                 |
|                    |               |                                |             | StatCRCAlignErrors,            |
|                    |               |                                |             | StatJabber, StatEtherPkts,     |
|                    |               |                                |             | StatMCPkts, StatBCPkts,        |
|                    |               |                                |             | Stat64OctOrLess,               |
|                    |               |                                |             | Stat65OctTo126Oct,             |
|                    |               |                                |             | Stat128OctTo255Oct,            |
|                    |               |                                |             | Stat128OctTo255Oct,            |
|                    |               |                                |             | Stat256OctTo511Oct,            |
|                    |               |                                |             | Stat512OctTo1023Oct,           |
|                    |               |                                |             | Statc1024OctTo1518Oct          |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| IntfRef **[KEY]**  | string        | Interface name of port         | N/A         | N/A                            |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| PMClassBEnable     | bool          | Enable/Disable control for     | true        | N/A                            |
|                    |               | CLASS-B PM                     |             |                                |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| PMClassCEnable     | bool          | Enable/Disable control for     | true        | N/A                            |
|                    |               | CLASS-C PM                     |             |                                |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| HighAlarmThreshold | float64       | High alarm threshold value for |      100000 | N/A                            |
|                    |               | this PM                        |             |                                |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| HighWarnThreshold  | float64       | High warning threshold value   |      100000 | N/A                            |
|                    |               | for this PM                    |             |                                |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| LowAlarmThreshold  | float64       | Low alarm threshold value for  |     -100000 | N/A                            |
|                    |               | this PM                        |             |                                |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| LowWarnThreshold   | float64       | Low warning threshold value    |     -100000 | N/A                            |
|                    |               | for this PM                    |             |                                |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+
| PMClassAEnable     | bool          | Enable/Disable control for     | true        | N/A                            |
|                    |               | CLASS-A PM                     |             |                                |
+--------------------+---------------+--------------------------------+-------------+--------------------------------+



*FlexSwitch CURL API Supported*
------------------------------------

	- GET By Key
		 curl -X GET -H 'Content-Type: application/json' --header 'Accept: application/json' -d '{<Model Object as json-Data>}' http://device-management-IP:8080/public/v1/config/EthernetPM
	- GET By ID
		 curl -X GET http://device-management-IP:8080/public/v1/config/EthernetPM/<uuid>
	- GET ALL
		 curl -X GET http://device-management-IP:8080/public/v1/config/EthernetPM?CurrentMarker=<x>&Count=<y>
	- UPDATE(PATCH) By Key
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/EthernetPM
	- UPDATE(PATCH) By ID
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/EthernetPM<uuid>


*FlexSwitch SDK API Supported:*
------------------------------------



- **GET**


::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getEthernetPM(Resource=resource, IntfRef=intfref)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **GET By ID**


::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getEthernetPMById(ObjectId=objectid)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'




- **GET ALL**


::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getAllEthernetPMs()

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'




- **UPDATE**

::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.updateEthernetPM(Resource=resource, IntfRef=intfref, PMClassBEnable=pmclassbenable, PMClassCEnable=pmclasscenable, HighAlarmThreshold=highalarmthreshold, HighWarnThreshold=highwarnthreshold, LowAlarmThreshold=lowalarmthreshold, LowWarnThreshold=lowwarnthreshold, PMClassAEnable=pmclassaenable)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **UPDATE By ID**

::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.updateEthernetPMById(ObjectId=objectidPMClassBEnable=pmclassbenable, PMClassCEnable=pmclasscenable, HighAlarmThreshold=highalarmthreshold, HighWarnThreshold=highwarnthreshold, LowAlarmThreshold=lowalarmthreshold, LowWarnThreshold=lowwarnthreshold, PMClassAEnable=pmclassaenable)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'
