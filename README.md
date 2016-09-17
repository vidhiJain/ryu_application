# Ryu_application
Monitoring app with RYU SDN controller
## Setup Required
* SDN controller Ryu: Install All-in-one SDN App Development Starter VM from http://sdnhub.org/tutorials/sdn-tutorial-vm/
* Start mininet, say by 
```sudo mn --topo single,3 --mac --controller remote --switch ovsk``` or 
```sudo mn --topo tree,depth=2,fanout=5 --controller=remote --switch ovsk,protocols=OpenFlow13```
* Start Ryu Controller
```cd /home/ubuntu/ryu && ./bin/ryu-manager --verbose ryu/app/simple_switch_13.py ryu/app/ofctl_rest.py```
* Install Eventlet, a concurrent networking library for Python
```pip install eventlet```

## Run the application
When the python script concurrent_url_to_csv.py is run, it generates csv files about aggregate flow, port stats and flow stats  from the OpenFlow API about the simulated network through mininet and ryu-controller. This is never-ending script which periodically updates the network logs in respective csv files

## Further work
* Plot the generated csv files real-time web-based monitoring interface
