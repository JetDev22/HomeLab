# Get latest ubuntu image
FROM ubuntu:latest

# Get system up to date
RUN apt-get update && apt-get upgrade -y

# Install dependencies, download xmrig and build it
RUN apt-get install git build-essential cmake libuv1-dev libssl-dev libhwloc-dev -y
RUN git clone https://github.com/xmrig/xmrig.git
RUN mkdir xmrig/build
RUN cd xmrig/build && cmake ..
RUN cd xmrig/build && make -j$(nproc)

# Start miner when container is running
CMD cd xmrig/build && ./xmrig --threads=4 -o gulf.moneroocean.stream:10128 -u 4AXu5n8HTUiUqw41V5RYauHnqWoTJtiRgWmpaUDYrcciCoUTuh4ZqmsEFb1t2YDetQhFk46DuZTXSY2nBMe57zFz2BDjJZK -p DockerMiner