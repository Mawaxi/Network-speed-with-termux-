#!/bin/bash

# Install speedtest-cli if not already installed
pkg install speedtest-cli -y

# Run speed test
echo "Running speed test..."
speedtest-cli --simple

# Get download speed
download_speed=$(speedtest-cli --simple | grep Download | awk '{print $2}')

# Get upload speed
upload_speed=$(speedtest-cli --simple | grep Upload | awk '{print $2}')

# Get ping
ping=$(speedtest-cli --simple | grep Ping | awk '{print $2}')

# Display results
echo "Network Speed Test Results:"
echo "---------------------------"
echo "Download Speed: $download_speed"
echo "Upload Speed: $upload_speed"
echo "Ping: $ping ms"
# Network-speed-with-termux-
