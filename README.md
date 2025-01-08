# ccminer8thread
Based on: https://github.com/Oink70/CCminer-ARM-optimized & https://github.com/Darktron/ccminer
for 8 thread luckypool

Install latest arm64-v8a Termux: https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk

Proceed with installation, configuration & compilation:

Installing clang and dependencies:

yes | pkg update && pkg upgrade -y
yes | pkg install libjansson build-essential clang binutils git -y

Fix environment & clone repo:

cp /data/data/com.termux/files/usr/include/linux/sysctl.h /data/data/com.termux/files/usr/include/sys
git clone https://github.com/yudagitu/ccminer8thread.git
cd ccminer
chmod +x build.sh configure.sh autogen.sh start.sh

Edit Arch & Cores:

nano configure.sh

Compile ccminer:

CXX=clang++ CC=clang ./build.sh

Change your pools, address, and miner name with:
nano config.json

Finally run the miner with:
~/ccminer/start.sh
