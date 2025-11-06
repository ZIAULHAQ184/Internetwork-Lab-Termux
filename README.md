pkg update -y && pkg upgrade -y
termux-setup-storage -y || true
pkg install -y git curl wget vim nano clang make unzip zip
pkg install -y python nodejs php ruby perl
pkg install -y openssh nmap proot proot-distro tsu
pkg install -y x11-repo root-repo
pkg install -y openvpn
pkg install -y termux-api socat
pkg install -y iperf3 whois mtr dnsutils net-tools htop tshark traceroute
python -m pip install --upgrade pip
python -m pip install wheel setuptools requests flask
npm install -g corepack && corepack enable
ip addr show
ip route show
ss -tulpen
ping -c 4 8.8.8.8
ping -i 0.2 -c 50 google.com
traceroute google.com
dig +short example.com
nslookup example.com 8.8.8.8
curl --max-time 10 -I https://example.com
iperf3 -s
iperf3 -c <server_IP>
nmap -sS -Pn -T4 8.8.8.8
tcpdump -i any -n -c 50
tcpdump -i any -n -w capture_$(date +%F_%T).pcap
ip neigh show
iptables -L
nft list ruleset
whois example.com
mtr -rw google.com
curl ifconfig.me
ip route | grep default
pkill dhcpcd && dhcpcd &
alias netcheck='ip addr show && ip route show && ss -tulpen'
echo "alias netcheck='ip addr show && ip route show && ss -tulpen'" >> ~/.bashrc
source ~/.bashrc

