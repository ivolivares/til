To configure and install Bluethoot devices (like Apple Keyboard) in Ubuntu, first install:

    sudo apt-get install bluez python-gobject python-dbus

Then set keyboard discoverable

Get the mac address of the bluetooth device
    hcitool scan

Create new device
    sudo bluez-simple-agent hci0 [XX:XX:XX:XX:XX:XX]
   
   which will hopefully return somthing like
     DisplayPasskey (/org/bluez/537/hci0/..., [PIN = 123456])
   else:
     $ sudo bluez-simple-agent hci0 XX:XX:XX:XX:XX:XX repair
   start over

Enter those numbers on your bluetooth device and confirm with return

Set device as trusted:
    sudo bluez-test-device trusted XX:XX:XX:XX:XX:XX yes

Connect to device:
    sudo bluez-test-input connect XX:XX:XX:XX:XX:XX
