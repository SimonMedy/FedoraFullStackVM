# FedoraFullStackVM

### Fullstack Development Environment on Fedora

This repository provides a pre-configured virtual machine (VM) built using **VirtualBox** and the **Fedora Workstation 40** distribution for full-stack web development. The VM comes with several development tools and services pre-installed and configured for ease of use. Below are the key features and instructions on how to use it.

## Installed Software and Tools

- **Docker**: Container platform for running services.
- **Docker Compose**: To easily manage multi-container Docker applications.
- **PHP**: Backend development language.
- **Node.js & npm**: JavaScript runtime and package manager for frontend development.
- **Python**: Installed for any use you want.
- **Symfony**: PHP framework for web applications.
- **Angular**: Javascript framework for frontend development.
- **React**: Another popular frontend library and ready to use with npx and npm.
- **MariaDB**: Relational database server.
- **phpMyAdmin**: Web interface for managing MariaDB databases.
- **Portainer**: Web-based interface to manage Docker containers (Similar to Docker Desktop).
- **Postman**: API testing tool for debugging and developing APIs.
- **Visual Studio Code**: A Code editor installed with **38 essential extensions** ready for web and full-stack development.

_Note: Both **MariaDB** and **phpMyAdmin** are containers that were installed with the docker-compose file located here : **/home/yxtomix/Dev/MariaDB-Container**._

## Download

- [Fedora 40 FullStack Dev Environment VM](https://kdrive.infomaniak.com/app/share/1186372/6cc63ecc-4dae-44d5-91b9-6c523b5b35bd)

## Access to Tools

- **Portainer**: Accessible via **ZenBrowser**. Use it to manage Docker containers visually.
- **phpMyAdmin**: Also accessible via **ZenBrowser** for database management.

Both tools can be accessed locally within the VM. Simply open **ZenBrowser**, the pre-installed web browser.

## Default Credentials

For all services that require authentication (Session password, sudo, Portainer, etc.), the default password is: @Motdepasse1234

The password for **MariaDB / phpMyAdmin** is likely either : **userpassword** or **rootpassword**

Please make sure to change to **change the default passwords** to secure your environment once set up.

## How to Use

### Installation

- **Virtualization Software**: You will need a virtualization software like [VirtualBox](https://www.virtualbox.org/).
- **Virtual Machine**: You will need the virtual machine (.ova file) - _[Download here](https://kdrive.infomaniak.com/app/share/1186372/6cc63ecc-4dae-44d5-91b9-6c523b5b35bd)_
- **Import the Virtual Machine**: Import the **_.ova_** file into **VirtualBox** or any virtualization software you want.
- **Virtual Machine Settings**: You can modify the resources allocated to the VM, such as CPU, RAM, and storage, according to your needs. To do this, go to **VirtualBox > Settings** and adjust the **System**, **Display**, or **Storage** tabs.

After all these steps, you can start the virtual machine.

### Setup and Configuration

After importing and starting the virtual machine, you may want to adjust some settings to fit your preferences. Here are a few suggestions:

- **Language**: By default, the language is set to English(US). You can change it in **Settings > System > Region & Language**.
- **Keyboard Layout**: By default, the keyboard layout is set to English(US). You can change it in **Settings > Keyboard**.
- **Screen Resolution**: You can adjust the resolution to fit your monitor for better display quality. In Fedora, go to **Settings > Displays** and choose the resolution that suits you best.
- **Check for Fedora Updates**: You can check for updates for Fedora in **Settings > Updates**.**
- **Update Packages**: It is recommended to ensure all installed packages are up to date. To do this, open a terminal and run the following commands:
  ```bash
  sudo dnf update
  ```
- **VirtualBox Guest Additions**: If you're using **VirtualBox**, it's recommended to install the **Guest Additions** to improve the integration between your host and the VM. This will enable features like better mouse integration, shared clipboard, and folder sharing between the host and the virtual machine. You can install them by selecting **Devices > Insert Guest Additions CD Image** from the VirtualBox menu when the VM is running, then follow the on-screen instructions in the terminal.
- **3D Acceleration**: You can also try to activate 3D acceleration in **VirtualBox > Settings > Display** if it works on your end. This will improve the performance of the virtual machine.

Once you've customized the VM to your liking, you're ready to start working!

### Start coding

Now that your machine is ready, you can go to this directory: **_/home/yxtomix/Dev/_**\
This is where you can create your projects and develop them. This is also where the docker-compose configuration for the containers is located.

To start coding, open the **Visual Studio Code** application and create anything you want. Feel free to modify any extensions or install new ones to suit your needs.

### Starting Docker Services

By default, everything is ready for development upon start up. Docker will automatically start with the containers.\
If the containers are not running, all you need to do is to run this command in a terminal where the docker-compose.yaml file is located:

```bash
docker compose up -d
```

_Note: If the `docker compose` command is not found, try `docker-compose` instead._\
_Another note: If you encounter permission issues, you may need to prefix the command with sudo._

### Access phpMyAdmin

- Open ZenBrowser and you will see [phpMyAdmin](http://localhost:8080) at the top, or go to http://localhost:8080 in any browser to access [phpMyAdmin](http://localhost:8080).

### Managing Containers with Portainer

- [Portainer](http://localhost:9443) is also accessible via ZenBrowser. Simply open ZenBrowser and you will see [Portainer](http://localhost:9443) at the top or go to http://localhost:9443 in any browser to access it.

### How to stop the containers

If you want to stop the containers, you can run this command in the same directory of the docker-compose file **(_/home/yxtomix/Dev/MariaDB-Container_)**:

```bash
docker compose down
```

By default, the containers will not stop until you stop them yourself. Even after the machine is shut down and restarted they will still be running or start automatically.\
You can delete this option / line in both the mariadb and phpmyadmin configs to avoid this behavior:

```yaml
restart: unless-stopped
```

And after that, remember to run the docker-compose file again to update the configuration.

## Customization

All installed tools are customizable, and you are free to configure them according to your needs. For example, the Node.js or PHP versions can be upgraded or modified to fit your project requirements.\
If you want, you can edit the configuration of the containers too. The docker-compose file is located here **_/home/yxtomix/Dev/MariaDB-Container/docker-compose.yaml_**

## Future Improvements

Feel free to download my VM and modify it to add more tools or configurations. This environment is designed to be a solid foundation for web and full-stack development.

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
