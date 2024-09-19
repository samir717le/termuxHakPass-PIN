## termuxHakPass-PIN
A Script For Termux That use ADB To Unlock Locked Android Phone Using USB | ⚠️  educational purposes only

## Install
# Depends 
-- Termux
-- Termux:api
-- Android Tools
-- Bash
-- PIN list
-- USB/ADB
--
# Test
not tested 
# Install
```
pkg update && pkg upgrade

pkg install git android-tools termux-api -y

git clone https://github.com/samir717le/termuxHakPass-PIN.git
cd termuxHakPass-PIN
chmod +x hakpass.sh
bash hakpass.sh -h
```
## direct install 
```
pkg update && pkg upgrade

pkg install git android-tools termux-api -y

git clone https://github.com/samir717le/termuxHakPass-PIN.git
cd termuxHakPass-PIN
mv hakpass $PREFIX/bin/
chmod +x $PREFIX/bin/hakpass
cd ..
mv termuxHak* .hakpass
hakpass -h
