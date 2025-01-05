<!-- markdownlint-disable first-line-heading -->
<p align="center">
  <img src=".github/assets/banner.png" alt="Vulhub" height="auto" />
  <p align="center">
    <a href="https://github.com/vulhub/vulhub/blob/master/LICENSE">
      <img src="https://img.shields.io/github/license/vulhub/vulhub.svg" alt="GitHub">
    </a>
    <a href="https://discord.gg/bQCpZEK">
      <img src="https://img.shields.io/discord/485505185167179778.svg" alt="Chat on Discord">
    </a>
    <a href="https://www.patreon.com/phith0n">
      <img src="https://img.shields.io/badge/sponsor-patreon-73d6a1.svg" alt="Backers and sponors on Patreon">
    </a>
    <a href="https://opencollective.com/vulhub#backer">
      <img src="https://img.shields.io/badge/backer-opencollective-f89a76.svg" alt="Backers and sponors on Opencollective">
    </a>
  </p>
</p>

# Vulhub Playground

Vulhub is an open-source collection of pre-built vulnerable Docker environments. No pre-existing knowledge of Docker is required; just execute two simple commands, and you have a vulnerable environment.

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
   ./vulhub_script.sh
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

## License

This project is licensed under the MIT License. See the LICENSE file for details.


## Notice

1. To prevent permission errors, please ensure that the docker container has permission to access all files in the current directory.
2. Vulhub does not support running on machines with non-x86 architecture such as ARM for now.


## License

Vulhub is licensed under the MIT License. See [LICENSE](LICENSE) for the full license text.
