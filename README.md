• Upadte & install base packages:

pkg update | pkg upgrade

pkg install -y nodejs git curl cmake make clang binutils

• Fix network interface (required):

cat >
 /data/data/com.termux/files/usr/bin/ifconfig << 'EOF'
#!/data/data/com.termux/files/usr/bin/sh
echo "lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536"
echo "        inet 127.0.0.1  netmask 255.0.0.0"
echo "        loop  txqueuelen 1000  (Local Loopback)"
EOF
chmod +x /data/data/com.termux/files/usr/bin/ifconfig

• Install OpenClaw:

npm install -g openclaw@latest
openclaw onboard

• Set your Gemini API key:

openclaw auth add google --key "YOUR_GEMINI_API_KEY"

• select modal
