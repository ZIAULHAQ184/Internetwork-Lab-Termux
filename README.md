pkg update -y && pkg upgrade -y
termux-setup-storage -y || true

# Basic Termux packages / dev tools
pkg install -y git curl wget vim nano clang make unzip zip

# Languages / runtimes (Termux python provides pip)
pkg install -y python nodejs php ruby perl

# Network / linux helpers (Termux-specific)
pkg install -y openssh nmap proot proot-distro tsu

# Repos & OpenVPN (if you need GUI/X or openvpn)
pkg install -y x11-repo root-repo
pkg install -y openvpn

pkg install -y termux-api
pkg install -y socat

# Python packages (use pip from Termux python)
python -m pip install --upgrade pip
python -m pip install wheel setuptools requests flask

# npm global: corepack (optional)
npm install -g corepack && corepack enable
----------------------------------------

# 1️⃣ IP address aur interfaces check karo
ip addr show

# 2️⃣ Routing table dekho (default gateway + connected routes)
ip route show

# 3️⃣ Network sockets / services check karo
ss -tulpen

# 4️⃣ Ping test Google DNS (connectivity test)
ping -c 4 8.8.8.8

# 5️⃣ Trace route ka path dekhne ke liye (network hops)
traceroute google.com

# 6️⃣ DNS resolution test (domain to IP)
dig +short example.com
nslookup example.com 8.8.8.8

# 7️⃣ Network mapping / port scanning (basic discovery)
nmap -sS -Pn -T4 8.8.8.8

# 8️⃣ Live packet capture (analyze network traffic)
tcpdump -i any -n -c 50

# 9️⃣ Neighbor discovery (ARP table)
ip neigh show

# 🔟 Continuous ping test (performance check)
ping -i 0.2 -c 50 google.com
