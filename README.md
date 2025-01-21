# ARM Cross Compile and Debug Example

## Step 1: Install Prerequisites
```bash
sudo apt update
sudo apt install -y build-essential cmake qemu-user qemu-system-arm gdb-multiarch gcc-aarch64-linux-gnu g++-aarch64-linux-gnu
```

### If you will not be statically linking your executable

```bash
sudo apt install -y libc6-arm64-cross
```

Also remove the line from the CMakeLists.txt  
```
set(CMAKE_EXE_LINKER_FLAGS "-static")
```

## Step 2: Build the executable

```bash
mkdir build
cd build
cmake ..
make
```

## Step 3: Run the executable

```bash
qemu-aarch64 ./hello_world
```

### If you did not statically link your executable

```bash
qemu-aarch64 -L /usr/aarch64-linux-gnu ./hello_world
```

## Step 4: Configure vscode

