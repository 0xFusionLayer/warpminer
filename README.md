# WarpMiner

## Download

You can download the pre-built binaries from our **Releases** page. Choose the appropriate version for your operating system.

## Performance Testing

```bash
./warpminer -mock -all
```

## Show OpenCL devices informations

```bash
./warpminer -info -all
```

This will display all available OpenCL devices with their indices:
```
Available OpenCL devices:
[1] NVIDIA GeForce RTX 3080 (Vendor: NVIDIA Corporation)
[2] AMD Radeon RX 6800 (Vendor: Advanced Micro Devices)
...
```

## Device Selection

You can choose specific devices to mine with using the `-devices` or `-d` flag:

```bash
# Use specific devices (e.g., devices 1 and 3)
./warpminer -devices "1,3"
# or use the short option
./warpminer -d 1,3

# Use all available devices (default behavior)
./warpminer
```

## Solo mining

**Run a FusionLayer client with mining feature enabled**
```
./fxl -ws -mine -miner.etherbase=0x123...fff
```
Replace 0x123...fff with your own address.

**Run the miner**
```bash
./warpminer
```
The default pool address is ws://127.0.0.1:8546.

## Pool Mining
```bash
./warpminer -user=username -pass=password -pool=wss://pool-address.com:port
```
Replace `user, pass, pool` with your actual values provided by the mining pool.

## Compile from source

**Requirements**

linux
```bash
sudo apt install ocl-icd-opencl-dev opencl-headers
```

**Clone the repository and build the miner**
```bash
git clone https://github.com/0xFusionLayer/warpminer
cd warpminer
go build .
```
