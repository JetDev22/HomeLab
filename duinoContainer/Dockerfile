# Get latest Ubuntu image
FROM ubuntu:latest

# Update the system
RUN apt-get update && apt-get upgrade -y

# Install duino miner and get dependencies
RUN apt-get install python3 python3-pip git python3-pil python3-pil.imagetk -y
RUN git clone https://github.com/revoxhere/duino-coin
RUN cd duino-coin && python3 -m pip install -r requirements.txt

# Run duino miner when container is running
CMD cd duino-coin && python3 PC_Miner.py