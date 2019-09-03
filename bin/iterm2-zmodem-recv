#!/usr/bin/env bash
# vim: fdm=marker foldlevel=0 sw=2 ts=2 sts=2

FILE=`osascript -e 'tell application "iTerm" to activate' -e 'tell application "iTerm" to set thefile to choose folder with prompt "Choose a folder to place received files in"' -e "do shell script (\"echo \"&(quoted form of POSIX path of thefile as Unicode text)&\"\")"`

if [[ -z "$FILE" ]]; then
  echo " Cancelled"
  # Send ZModem cancel
  echo -e \\x18\\x18\\x18\\x18\\x18
  sleep 1
  echo
  echo " # Cancelled transfer"
else
  cd "$FILE"
  "${HOMEBREW_PREFIX:-/usr/local}/bin/rz" -E -e -b
  sleep 1
  echo
  echo " # Sent -> $FILE"
fi
