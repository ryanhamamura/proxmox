## Powertop Auto tune systemd Service
```sh
cat << EOF | sudo tee /etc/systemd/system/powertop.service
[Unit]
Description=PowerTOP auto tune

[Service]
Type=oneshot
Environment="TERM=dumb"
RemainAfterExit=true
ExecStart=/usr/sbin/powertop --auto-tune

[Install]
WantedBy=multi-user.target
EOF

systemctl daemon-reload
systemctl enable powertop.service
```

## CPU Governor Set to Powersave
Proxmox defaults the cpu governor mode to "performance" where the cpu clock speed is set to max. We want this to be in powersave. 

```sh
cat << EOF | sudo tee /etc/systemd/system/cpu-governor.service
[Unit]
Description=CPU Governor Type to Powersave

[Service]
Type=oneshot
Environment="TERM=dumb"
RemainAfterExit=true
ExecStart=echo "powersave" | tee /sys/devices/cpu/cpu*/cpufreq/scaling_governor

[Install]
WantedBy=multi-user.target
EOF

systemctl daemon-reload
systemctl enable powertop.service

```
