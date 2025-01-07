# Vulhub Playground

Vulhub is an open-source collection of pre-built vulnerable Docker environments. No pre-existing knowledge of Docker is required; just execute two simple commands, and you have a vulnerable environment.

## Compatibility

Vulhub is compatible with Linux systems and Windows via WSL2. 

### For Windows Users:
If you are using Windows, you will need to install WSL2 to enable a Linux environment. Follow the instructions below:

#### Install WSL2 on Windows:

1. Enable the WSL feature:
   ```powershell
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```

2. Restart your computer.

3. Install the Linux kernel update package:
   Download and install the package from [here](https://aka.ms/wsl2kernel).

4. Set WSL2 as the default version:
   ```powershell
   wsl --set-default-version 2
   ```

5. Install a Linux distribution from the Microsoft Store (e.g., Ubuntu).

For detailed instructions, visit the [WSL2 Documentation](https://learn.microsoft.com/en-us/windows/wsl/install).

### For Linux Users:
If you are already using Linux, you can skip the WSL2 installation and proceed directly to the installation steps for Docker.

## Installation

### Install Docker on Ubuntu 22.04:

```bash
# Install the latest version of Docker
curl -s https://get.docker.com/ | sh

# Run Docker service
sudo systemctl start docker
```

Note: As of April 2022, Docker Compose is merged into Docker as a subcommand (Docker Compose V2). The Python version of `docker-compose` will be deprecated after June 2023. Vulhub will no longer require the installation of additional `docker-compose`, and all documentation will be updated to use the `docker compose` subcommand.

The installation steps of Docker and Docker Compose for other operating systems might be slightly different. Please refer to the [Docker documentation](https://docs.docker.com/) for details.

### Clone the Vulhub Repository

To get started, clone the Vulhub Labs repository:

```bash
git clone https://github.com/supdevinci/vulhub-labs.git
cd vulhub-labs
```

## Usage

This script provides an interactive way to select vulnerable software and CVEs to explore. Follow these steps:

1. Run the script in the terminal:

   ```bash
   chmod +x vulnerability_labs.sh
   ./vulnerability_labs.sh
   ```

2. You will be presented with a menu to select the software you want to test.

3. Once you select the software, you can choose the specific vulnerability (CVE) from the available options.

4. The script will launch the corresponding Docker environment and display the ports being used for the environment.

5. If there are port conflicts or any issues, the script will provide guidance on resolving them.

### Example Workflow

- Select the software from the main menu.
- Choose the specific CVE or subdirectory.
- The script will launch the environment and provide a list of URLs and ports for accessing the services.

### Important Notes

- Ensure that you have the required permissions to run Docker commands on your system.
- Use the environments responsibly and only for educational or testing purposes.

## Troubleshooting

If you encounter issues such as port conflicts:

- The script will detect the port conflict and provide the container name causing the issue.
- You can stop the conflicting container using:

  ```bash
  docker stop <container_name>
  ```

## Contributing

If you want to contribute to the Vulhub Playground, fork the repository and submit a pull request.

## Notice

1. To prevent permission errors, please ensure that the docker container has permission to access all files in the current directory.
2. Vulhub does not support running on machines with non-x86 architecture such as ARM for now.

## License

Vulhub is licensed under the MIT License. See [LICENSE](LICENSE) for the full license text.
