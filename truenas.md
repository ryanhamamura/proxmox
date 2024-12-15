## Important TrueNAS VM Settings
### PCIe Passthrough of HBA card
```
1. Machine = q35
2. vIOMMU = virtio
3. Pass through raw PCI device (not mapped)
4. ROM-Bar = 0
5. PCI-Express = 1
```
