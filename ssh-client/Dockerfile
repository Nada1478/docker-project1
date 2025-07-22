FROM ubuntu:latest

# Set working directory
WORKDIR /app

# Install SSH client and basic tools
RUN apt-get update && \
    apt-get install -y openssh-client iputils-ping net-tools && \
    apt-get clean

# Default command to keep the container running
CMD ["tail", "-f", "/dev/null"]

