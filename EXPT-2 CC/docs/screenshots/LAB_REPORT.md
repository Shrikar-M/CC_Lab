# Dockerized Python Flask Application

## 1. Aim

To package a simple Python Flask web application into a Docker image and run it locally in a Docker container using Docker Desktop.

## 2. Objectives

- Verify Docker installation and run the Docker `hello-world` test image.
- Create a Flask application and record its dependency.
- Build a Docker image using a Dockerfile.
- Run the Flask application inside a Docker container using port mapping.
- Verify the Docker image, container status, and application response.

## 3. Requirements

- Windows computer with Docker Desktop installed and running
- Windows PowerShell
- Python
- Flask
- Dockerfile
- Web browser for testing the application at `http://localhost:5000`

## 4. Software and Technologies Used

| **Software / Technology** | **Purpose** |
| ------------------------- | ----------- |
| Windows | Operating system |
| PowerShell | Terminal used to execute commands |
| Docker Desktop | Local Docker environment |
| Docker | Container and image management |
| Python 3.12 slim | Docker base image |
| Flask | Python web framework |
| Web Browser | Used to access the Flask application |

## 5. Project Structure

```text
EXPT-2 CC/
├── app.py
├── requirements.txt
├── Dockerfile
├── README.md
├── LICENSE
└── docs/
    ├── LAB_REPORT.md
    └── screenshots/
        ├── 01_Docker_Version_Verification.png
        ├── 02_Docker_Hello_World_Test.png
        ├── 03_Creating_Docker_Project.png
        ├── 04_Flask_Application_app_py.png
        ├── 05_Python_Requirements_File.png
        ├── 06_Dockerfile_Creation.png
        ├── 07_Verifying_Project_Files.png
        ├── 08_Docker_Image_Build.png
        ├── 09_Docker_Image_Verification.png
        ├── 10_Docker_Container_Status.png
        ├── 11_Docker_Container_Running.png
        └── 12_Flask_Application_Browser.png
