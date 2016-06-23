
Introduction
===============

This APP is based on Google BLE sample, [Android BluetoothLeGatt][1]. Its target is to create one monitoring APP 
for those people that are out on bail. 

There is a wristband on people's hand and communicates with this APP via BLE connection. 
When the connection is lost for some specified period or RSSI is lower than some specified level, the APP
will be in the alarm mode, where ring/voice notifications are generated from the phone and messages are 
sent to the security center.

Also the battery level info and wristband integrity info will be sent to the APP periodically. In cases of 
low battery and wristband is broken, the alert messages will be sent to the security center.

This APP is able to collecting location info from various cell phone technologies, e.g. WIFI, GPS, GSM,
The collected location info will be sent to the security center in a specified period.

This APP is able to prevent uninstalling and manually shut-down by people. If the phone is powered off or 
out of power, the security center will raise alerts after some specified timeout due to periodic communication 
between phone and the security center is lost.

[1]:https://github.com/googlesamples/android-BluetoothLeGatt

Development Stages
===================================

Stage One
------------

- BLE scan & connection with the specified wristband (by BTADDR);
- RSSI readback and connection lost alert (phone locally);
- battery level readback and low voltage alert (phone locally);
- phone local alert by highlighted text, ring/voice;

Stage Two
--------------

- periodic communication with the security center (protocol TBD);
- collecting location info from WIFI, GPS, GSM, and report them to the security center periodically;
- alerts are sent to the security center;
- phone low battery alert;
- the security center alter due to periodic communication lost;

Stage Three
-------------

- wristband broken alert;
- security enhancement between wristband and phone/APP;
- The APP can work in the background, so two power saving modes to be considerred.
    - Doze power saving mode
    - App standby power saving mode

License
==========

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements.  See the NOTICE file distributed with this work for
additional information regarding copyright ownership.  The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License.  You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the
License for the specific language governing permissions and limitations under
the License.
