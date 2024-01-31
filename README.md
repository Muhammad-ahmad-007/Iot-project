# Iot-project
IoT-project
In this project, we built a smart sensor device using the RIOT operating system. This device collects information about the environment, like temperature and pressure, and sends it securely to a central hub called an MQTT broker. This broker is set up to connect with mahmad, a cloud service. The data collected by the sensor can then be seen and analyzed using Grafana, a tool for visualizing information.

Repo Structure:
![image](https://github.com/Muhammad-ahmad-007/Iot-project/assets/59662097/8fcd8266-0e2a-4110-ad44-57a187f88f37)

Getting started:
Clone the repo: https://github.com/Muhammad-ahmad-007/Iot-project

Connecting to Grenoble SSH front-end:
$ scp -r <login>@grenoble.iot-lab.info


Experiment via Fit-lab=mahmad
Launched an experiment with three nodes, two m3 nodes, and one a8 node and launched an experiment. 

using RIOT environment we built border router firmware: source /opt/riot.source

Built border router firmware for M3 node with baudrate 500000 Note:
make ETHOS_BAUDRATE=500000 DEFAULT_CHANNEL=<channel> BOARD=iotlab-m3 -C examples/gnrc_border_router clean all

Flash Border Router Firmware Flash the border router firmware to the first M3 node (m3-1 in this case)
iotlab-node --flash examples/gnrc_border_router/bin/iotlab-m3/gnrc_border_router.elf -l grenoble,m3,<node-id>

Configure Border Router Network Choose an IPv6 prefix for the site (e.g., 2001:660:5307:3100::/56) Configure the network of the border router on m3- Propagate an IPv6 prefix with ethos_uhcpd.py

sudo ethos_uhcpd.py m3-<node-id> tap0 2001:660:5307:3100::1/56

Setup MQTT Broker and Mosquitto Bridge on A8 Node Now, in another terminal, SSH to the SSH frontend, and login into clone the mqtt_broker and mosquitto bridge configuration files in A8 shared directory. SSH into the A8 node
ssh root@node-a8-1

you can Check the global IPv6 address of the A8 node
ifconfig





some images for data visualization>
<img width="959" alt="iotdata" src="https://github.com/Muhammad-ahmad-007/Iot-project/assets/59662097/ce79887d-145d-4894-8ed0-9967b587a3d3">


<img width="959" alt="iotdbss" src="https://github.com/Muhammad-ahmad-007/Iot-project/assets/59662097/afede45a-6a3e-4710-875d-8ce07c8a01ea">


Node IoT

<img width="959" alt="nodeiot" src="https://github.com/Muhammad-ahmad-007/Iot-project/assets/59662097/9f3715c7-f1ac-453f-adf9-aa4066ec6b0d">



<img width="959" alt="gitbash" src="https://github.com/Muhammad-ahmad-007/Iot-project/assets/59662097/ead6a5f5-aef9-42e8-8b63-76c8764fd379">

Fit IoT lab

<img width="959" alt="fitiot" src="https://github.com/Muhammad-ahmad-007/Iot-project/assets/59662097/15e7e950-7615-4891-bff3-147a74afb826">


<img width="959" alt="fitlab" src="https://github.com/Muhammad-ahmad-007/Iot-project/assets/59662097/9a6de4f7-1c4d-49f4-8d29-3fb0dacf959c">









