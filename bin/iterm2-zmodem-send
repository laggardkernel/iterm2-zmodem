#!/usr/bin/env bash
# vim: fdm=marker foldlevel=0 sw=2 ts=2 sts=2

FILE=`osascript -e 'tell application "iTerm" to activate' -e 'tell application "iTerm" to set thefile to choose file with prompt "Choose a file to send"' -e "do shell script (\"echo \"&(quoted form of POSIX path of thefile as Unicode text)&\"\")"`

if [[ -z "$FILE" ]]; then
  echo " Cancelled"
  # Send ZModem cancel
  echo -e \\x18\\x18\\x18\\x18\\x18
  sleep 1
  echo
  echo " # Cancelled transfer"
else
  "${HOMEBREW_PREFIX:-/usr/local}/bin/sz" "$FILE" -e -b
  sleep 1
  echo
  echo " # Received $FILE"
fi
