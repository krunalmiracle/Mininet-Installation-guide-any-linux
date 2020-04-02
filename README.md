# krunalmiracle-gmail.com
#Mininet Installation on Linux
Installation method for to Run Mininet on any linux with python modules implementation for newbies, which i was too when i didn't knew how to install mininet properly and ketp getting errros such as MININET not found, MININET not able to run cause OVS-Switch not found, controller not found, python module not found.
Follow the Mininet Installation guide made by me, if anyone finds something wrong message me. Follow the Guide below or download the Text file.
Install Any Linux Version
Mount the VirtualBox Tools CD for Correct Resolution
Terminal Commands
    cd /media/USERNAME/VBox_GAs_6.1.4
    sudo su
    sudo apt install build-essential dkms linux-headers-$(uname -r)
    sudo sh ./VBoxLinuxAdditions.run
    sudo reboot
Update & Upgrade Linux
    sudo apt-get update
    sudo apt-get upgrade
We Install git Tool
    sudo apt-get git
Mininet Installation
    sudo su
    cd /home/USERNAME
    git clone git://github.com/mininet/mininet
    cd mininet/
  Shows mininet availaible versions
    git tag
  Install specific version of mininet
    git checkout -b 2.2.2
    cd /mininet/util/
  Install all the tools in mininet
    sudo ./install.sh -a
  Shows any extra tool, availaible to install
    sudo ./install.sh -h
  Install Extra Tools requiered to run mininet like python,xterm, ssh, iperf,etc...
    sudo apt-get install -y git gcc make socat psmic xterm ssh iperf iproute telnet python-setuptools cgroup-bin ethtool htlp2man pyflaes pylint pep8
  Repair Mininet Installatio, mainly due to test controller being renamed from ovs-controller
    sudo cp /usr/bin/ovs-testcontroller /usr/bin/ovs-controller
  Installing Net tool
    sudo apt-get install net-tools
  Adding Mininet Module to python
    cd /home/USERNAME/mininet
    sudo python setup.py install
  Test Mininet
    sudo mn
WireShark Installation if haven't got already installed
    sudo add-apt-repository universe
    sudo apt install WireShark
  Reconfiguring Wireshark so any user can capture packets
    #Remember to say yes to allow wireshark to capture on non user
    sudo dpkg-reconfigure wireshark-common
  Test Wireshark
    sudo wireshark
Capture Packets from mininet need to launch it using this Commands
  #Preffered
    sudo wirehsark &
  #If the above doesn't capture mininet interfaces
    sudo wireshark &>/dev/null &
