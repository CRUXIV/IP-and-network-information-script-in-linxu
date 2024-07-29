# IP-and-network-information-script-in-linxu


# Network Information Script

This repository contains a bash script for displaying network information on Linux systems. The script shows all IP addresses associated with network interfaces, provides details about the current network, and displays the routing table.

## How to Use the Script

To set up and use the network information script, follow these instructions:

1. Create a new file named `network_info.sh`:

    nano network_info.sh

2. Copy and paste the following content into `network_info.sh`:

    #!/bin/bash

    # Display all IP addresses
    echo "IP Addresses:"
    ip -br address show | awk '{print $1, $3}'

    echo ""

    # Display the current network
    echo "Current Network Information:"
    nmcli -f NAME,DEVICE,STATE connection show --active

    # Optionally, show the routing table to see the default gateway
    echo ""
    echo "Routing Table:"
    ip route show

3. Save the file and exit the editor:
    - Press `Ctrl + X`
    - Press `Y` to confirm saving
    - Press `Enter` to exit

4. Change the file permissions to make the script executable:

    chmod +x network_info.sh

5. Execute the script to display network information:

    ./network_info.sh

### Explanation of the Script

- **IP Addresses**: Lists all IP addresses associated with network interfaces.
- **Current Network**: Shows active network connections and their states.
- **Routing Table**: Displays the routing table, including default gateway information.

## License

This project is licensed under the MIT License.

## Contact

For any questions or issues, please contact [your-email@example.com].
