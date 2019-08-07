<a href="https://www.cortex-ia.co.uk/" target="_blank"><img src="https://github.com/CortexIATest/CTXImages/blob/master/Cortex-350-120.png" alt="Welcome to Cortex!" width="350" height="120" border="0"></a>

# CTX-Request-Handler
The request handler module should be used to manage incoming requests, from third party systems or internally from Cortex flows, which require queueing. The module offers:
* Request handler controller, which automatically saves requests and triggers them as soon as the specific queue requirements are met
* User interfaces to manage and monitor the requests queues

The queues that control the incoming requests can be configured in a variety of ways to cover for different requirements and scenarios:
* Traffic management
	* Incoming requests at any rate
	* Requests triggered as first-in-first-out
	* Maximum slots configured to ensure that only X requests run at each time
		* The queue maximum slots can be set to 0 to block the execution of requests. This can be used during maintenance periods.  

* Throttle management
	* Incoming requests at any rate
	* Requests triggered as first-in-first-out
	* Throttle time configured to guarantee a minimum execution time of T between executions start time
	* Possibility to set maximum slots so that only X requests run at each time
		* Even for throttle management cases the queue maximum available slots needs to be defined. If there is no limit, the maximum can be configured with a theorical non-reachable simultaneals request number (example: 10000). As for the traffic example, the maximum slots can be set to 0 to block the execution of requests.
		
* Sequence management
	* Queues also support sequence management, which means that specific requests only run if a previous request execution has finished.
	* This feature is independent of the queue the request belongs to, so each request in a sequencing scenario can belong to a different queue. The execution of each request will still satisfy both the sequence and queue requirements.


## Table of Contents
1) [Dependencies](#dependencies)
    * [Cortex Version](#cortex-version)
    * [OCIs](#ocis)
    * [Files](#files)
    * [Other](#other)
1) [Installation](#installation)
1) [How to use](#how-to-use)
1) [How you can contribute](#how-you-can-contribute)
1) [Versioning](#versioning)
1) [Licensing](#licensing)

## Dependencies
### Cortex Version
This version of the CTX-Request-Handler module was developed in Cortex v6.4.0. Some functionality may not be available in earlier verions of Cortex.

### OCIs
The CTX-Request-Handler module requires the following Cortex OCIs:
* Database

### Files
The CTX-Request-Handler module requires the following files:
* [CTX-Request-Handler Studio Package]()
* [Cortex-RequestHandler Database Install Script]()


## Installation
Details of how the module should be imported into Cortex can be found in the [Deployment Plan]().

## How to use
A detailed User Guide has been provided with instructions on how to use the module, available [here](). Configuration of each flow/subtask's inputs and outputs are detailed in notes on the flow/subtask workspace.

## How you can contribute
Unfortunately, we cannot offer pull requests at this time or accept any improvements.

## Versioning
The CTX-Request-Handler module has the following versions, starting with the most recent:

Version | Release | Functionality | Notes
------------ | ------------- | ----------- | -----------
v1.0 | 12/07/2019 | Request-Handler-Controller | Created
v1.0 | 12/07/2019 | Request-Handler-House-Keeping | Created
v1.0 | 12/07/2019 | Request-Handler-Restart-Queues | Created
v1.0 | 12/07/2019 | Request-Handler-Management-UI | Created
v1.0 | 12/07/2019 | Request-Handler-Monitoring-UI | Created

## Licensing
All functionality within this module is licensed under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0).

Copyright 2019 Cortex Limited

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
