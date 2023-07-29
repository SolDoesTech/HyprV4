#!/bin/bash

get_pwr() {
    PWR=$(asusctl profile -p | sed s:'Active profile is'::)
}

get_pwr

if [ $PWR == Balanced ]; then
    text="󰾅"
    tooltip="Balanced"
elif [ $PWR == Performance ]; then
    text="󰓅"
    tooltip="Performance"
elif [ $PWR == Quiet ]; then
    text="󰾆"
    tooltip="Quiet"
fi

echo '{"text": "'$text'", "tooltip": "'$tooltip'"}'

if [[ "$1" == "next" ]]; then
    asusctl profile -n; pkill -SIGRTMIN+8 waybar
    get_pwr
    notify-send -h string:x-canonical-private-synchronous:sys-notify -u low "$PWR Power Profile"
fi