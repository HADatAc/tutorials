## Installing `docker`

The installation of the `docker` depends on the machine's Operational System.

### Ubuntu

Before installing Docker Engine for the first time on a new host machine, you must set up the Docker repository. Afterward, you can install and update Docker from the repository.

1. Set up Docker's apt repository.
   \`\`\`bash
   sudo apt-get update
   sudo apt-get install ca-certificates curl
   sudo install -m 0755 -d /etc/apt/keyrings
   sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
   sudo chmod a+r /etc/apt/keyrings/docker.asc
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME")stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   sudo apt-get update
   \`\`\`
2. Install the Docker packages
   \`\`\`bash
   sudo apt-get install docker docker-compose
   \`\`\`
3. [OPTIONAL] Manage Docker as a non-root user on Linux
   If you don't want to preface the docker command with sudo, create a Unix group called docker and add users to it. When the Docker daemon starts, it creates a Unix socket accessible by members of the `docker` group. On some Linux distributions, the system automatically creates this group when installing Docker Engine using a package manager. In that case, there is no need for you to manually create the group.

\`\`\`bash
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
\`\`\`

To test, type the command `docker run hello-world` on the terminal.

### Windows and macOS

To install `docker` on Windows or macOS, follow the official `docker` tutorials:

- [Windows](https://docs.docker.com/desktop/install/windows-install/)
- [macOS](https://docs.docker.com/desktop/install/mac-install/)
