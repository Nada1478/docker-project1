FROM ubuntu:latest

# Install SSH server
RUN apt-get update && \
    apt-get install -y openssh-server && \
    mkdir /var/run/sshd

# Generate SSH host keys (optional - OpenSSH usually does this on first run)
RUN ssh-keygen -A

# Set root password (for testing only)
RUN echo 'root:rootpassword' | chpasswd

# Allow root login (not recommended in production)
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config

# Expose SSH port
EXPOSE 22

# Start SSH server when the container starts
CMD ["/usr/sbin/sshd", "-D"]
