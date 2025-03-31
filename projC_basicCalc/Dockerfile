# Use an official lightweight Ubuntu base image
FROM ubuntu:22.04

# Set a non-interactive mode to avoid prompts during installation
ENV DEBIAN_FRONTEND=noninteractive

# Install required dependencies: JDK, Maven, Git, and cleanup to reduce image size
RUN apt update && apt install -y \
    openjdk-17-jdk \
    maven \
    git \
    && rm -rf /var/lib/apt/lists/*

# Set JAVA_HOME (important for Maven builds)
ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
ENV PATH="${JAVA_HOME}/bin:${PATH}"

# Set default working directory inside the container
WORKDIR /app

# Default command: Show versions to verify setup
CMD ["/bin/bash"]
