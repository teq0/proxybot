# proxybot
Script to set env vars etc on OSX based on proxy settings for current network interface. It assumes the local proxy (usually cntlm) is at 127.0.0.1:3128
Note that this a bash/zsh script without the .sh suffix so that it can be run as an executable.

This is a simplified and customised version of https://github.com/kontrafiktion/proxy-settings-osx

## Usage
Put proxybot somewhere in your $PATH, then while in a terminal do

`source proxybot`

You can force setting or unsetting the proxy by using --set or --unset e.g.

`source proxybot --unset`

## Git and Maven
Proxybot also updates your global git and maven settings.
For git is just uses the command line, but for maven you need two copies of your maven settings, one with proxy settings enabled and one without, called ~/.m2/settings_w_proxy.xml and ~/.m2/settings_wo_proxy.xml.

TODOs
 - it doesn't currently check whether the maven files exist, so if you don't use maven it will display an error. The script needs to either check for the existence of these files, or, preferably, edit the m2.settings file in place using sed (or something).
 - read CNTLM settings from environment variables


