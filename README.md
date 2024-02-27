# System Update and Certificate Management Script

This script is designed to facilitate system administrators and IT professionals in managing system updates and searching for certificates within a networked environment. It's structured to provide a straightforward and interactive user experience, guiding the user through different functionalities based on their input.

## Features

### 1. System Information Display

Upon execution, the script displays the current operating system version and the domain membership status. This feature is crucial for ensuring that the script is being run in the correct environment and that the machine is properly configured within its network.

### 2. Software Update Check

This feature allows users to check for pending software updates and the last performed update and upgrade actions. It's designed to help maintain system security and efficiency by ensuring that all software is up-to-date.

### 3. Certificate Search

The certificate search functionality enables users to locate machine certificates within a specified directory. This is particularly useful in environments where machine authentication and encryption are critical.

## Script Usage

```bash
bash ./system_cert_management.sh

Detailed Functionality
System Information Display

bash

# Display OS version
echo "Operating System:"
lsb_release -d | cut -f2

# Check domain information
echo "Domain Information:"
domain_info=$(realm list | awk '/domain-name:/ {print $2}')
if [ -n "$domain_info" ]; then
    echo "Machine is on the '$domain_info' domain"
else
    echo "Machine is not joined to any domain"
fi

Software Update Check

The script asks the user if they wish to check for software updates. If selected, it checks for the last sudo update and upgrade, providing the user with the option to proceed with these actions.
Certificate Search

This section prompts the user to enter details for the certificate search, including choosing a site and specifying a machine name. The script then performs an LDAP search based on the provided parameters and displays any found certificates along with their details.
Code Snippet (Example)

Here, you would include a simplified, generic version of the code that showcases a snippet of the script functionality. For instance, the initial menu prompt:

bash

echo "Welcome to the System Management Script."
echo "1. Check for software updates"
echo "2. Search for AD certificates"
read -p "Enter your choice (1 or 2): " user_choice

And a brief explanation of how the choice is handled.
Conclusion

This script is a versatile tool for system administration, offering essential functionalities for maintaining system integrity and security. It is designed with usability in mind, providing a clear and interactive user experience.


