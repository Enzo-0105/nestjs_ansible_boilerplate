# NestJS Boilerplate Configuration

This project provides an Ansible playbook to configure a NestJS boilerplate application. The playbook sets up the environment, installs necessary dependencies, and configures PostgreSQL and RabbitMQ. Additionally, it sets up Nginx as a reverse proxy and configures logging for the application.

## Prerequisites

- Ansible installed on your control machine.
- Access to the target machine with sudo privileges.
- Internet connection to download required packages and dependencies.

## Playbook Variables

- `app_user`: The user that will run the application (default: `hng`).
- `app_dir`: The directory where the application will be deployed (default: `/opt/stage_5b`).
- `app_port`: The port on which the application will run (default: `3000`).
- `repo_url`: The URL of the Git repository containing the application code.
- `repo_branch`: The branch of the Git repository to clone.
- `pg_user`: The PostgreSQL user for the application.
- `pg_db`: The PostgreSQL database for the application.
- `rabbitmq_user`: The RabbitMQ user for the application.
- `rabbitmq_password`: The RabbitMQ user password (generated using Ansible lookup plugin).

## Playbook Tasks

1. **Create application user**: Creates the user that will run the application with sudo privileges.
2. **Ensure application directory exists**: Creates the application directory with appropriate permissions.
3. **Remove existing content**: Removes any existing content in the application directory.
4. **Clone repository**: Clones the application code from the specified Git repository.
5. **Install PostgreSQL**: Installs PostgreSQL and its dependencies.
6. **Start and enable PostgreSQL service**: Ensures PostgreSQL service is running and enabled on boot.
7. **Generate PostgreSQL password**: Generates a random password for the PostgreSQL user.
8. **Create PostgreSQL setup script**: Creates a script to configure PostgreSQL user and database.
9. **Run PostgreSQL setup script**: Executes the PostgreSQL setup script to configure the database.
10. **Remove PostgreSQL setup script**: Deletes the PostgreSQL setup script after execution.
11. **Install RabbitMQ**: Installs RabbitMQ server.
12. **Enable RabbitMQ management plugin**: Enables the RabbitMQ management plugin.
13. **Start and enable RabbitMQ service**: Ensures RabbitMQ service is running and enabled on boot.
14. **Check if RabbitMQ user exists**: Checks if the RabbitMQ user already exists.
15. **Create RabbitMQ user**: Creates the RabbitMQ user if it does not exist.
16. **Set RabbitMQ user permissions**: Configures permissions for the RabbitMQ user.
17. **Ensure /var/secrets directory exists**: Creates the directory to store credentials.
18. **Save PostgreSQL credentials**: Saves the PostgreSQL credentials to a file.
19. **Save RabbitMQ credentials**: Saves the RabbitMQ credentials to a file.
20. **Install nvm**: Installs Node Version Manager (nvm).
21. **Install Node.js using nvm**: Installs Node.js using nvm.
22. **Verify Node.js installation**: Verifies the installation of Node.js.
23. **Set up environment variables**: Configures environment variables for the application.
24. **Install Nginx**: Installs Nginx web server.
25. **Configure Nginx reverse proxy**: Configures Nginx as a reverse proxy for the application.
26. **Enable Nginx site**: Enables the Nginx site configuration.
27. **Restart Nginx**: Restarts the Nginx service to apply changes.
28. **Create log directory**: Creates the directory for application logs.
29. **Start application**: Starts the application using Node.js.
30. **Configure logging for application**: Configures logging for the application.

## Usage

1. Clone this repository:

    ```bash
    git clone https://github.com/yourusername/yourrepository.git
    cd yourrepository
    ```

2. Update the playbook variables in `main.yml` as needed.

3. Run the playbook:

    ```bash
    ansible-playbook -i inventory main.yml
    ```

## Logs

- Application logs are stored in `/var/log/stage_5b/out.log`.
- Error logs are stored in `/var/log/stage_5b/error.log`.

## Contributing

Feel free to fork this repository and make changes. Pull requests are welcome.

## License

This project is licensed under the MIT License.

