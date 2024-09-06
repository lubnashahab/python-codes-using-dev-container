# python-codes-using-dev-container
A project to set the goals of a programmer
Here’s a step-by-step guide on running Python code using a Dev Container:

### Prerequisites
- **Docker**: Ensure Docker is installed and running on your machine.
- **VS Code**: Visual Studio Code should be installed along with the **Remote - Containers** extension.

### Steps to Run Python Code in a Dev Container:

1. **Install Docker**:
   - Download and install Docker from [Docker's official site](https://www.docker.com/get-started).
   - Verify installation by running `docker --version` in the terminal.

2. **Install VS Code**:
   - Download and install Visual Studio Code from [VS Code's official site](https://code.visualstudio.com/).

3. **Install Remote - Containers Extension in VS Code**:
   - Open VS Code.
   - Go to Extensions (`Ctrl+Shift+X`).
   - Search for "**Remote - Containers**" and install the extension.

4. **Set Up Your Project Directory**:
   - Create a folder for your project. For example:
     ```bash
     mkdir my-python-project
     cd my-python-project
     ```

5. **Create a `devcontainer.json` File**:
   - Inside your project folder, create a `.devcontainer` folder.
     ```bash
     mkdir .devcontainer
     ```
   - Inside `.devcontainer`, create a `devcontainer.json` file with the following content:
     ```json
     {
       "name": "Python Dev Container",
       "image": "python:3.9",  // You can specify any Python version
       "extensions": [
         "ms-python.python",
         "ms-python.vscode-pylance"
       ]
     }
     ```

6. **Create a `Dockerfile` (Optional)**:
   - If you need to install additional packages or dependencies, create a `Dockerfile` inside `.devcontainer`:
     ```Dockerfile
     FROM python:3.9

     # Install any dependencies
     RUN pip install --upgrade pip
     ```

7. **Open the Project in VS Code**:
   - Open the project folder in VS Code (`File > Open Folder`).
   - VS Code will prompt you to open the folder in a container.
     - Click **Reopen in Container**.

8. **Running Python Code in the Dev Container**:
   - Once the container starts, you can open any Python file and run it inside the container.
   - To run a Python file:
     - Open the terminal in VS Code (`Ctrl + \` or go to `Terminal > New Terminal`).
     - Run the Python file:
       ```bash
       python your_script.py
       ```

9. **Customizing the Dev Container (Optional)**:
   - You can add more configuration, such as mounting volumes, installing additional packages, or running commands after the container starts.
   - Modify the `devcontainer.json` or `Dockerfile` based on your needs.

10. **Shutting Down the Container**:
    - To stop the container, you can either close VS Code or run:
      ```bash
      docker ps  // to list running containers
      docker stop <container_id>  // stop the container using the ID from the list
      ```

This setup allows you to run Python code in a fully isolated development environment using a containerized Python installation.