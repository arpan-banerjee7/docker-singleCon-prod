This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

# Developed using Docker for Windows running on WSL2 backend. So all the below steps are written as per that.

## Steps to run this project in Production Mode
1. Download and configure Docker
2. Navigate to the root directory of the project
3. **Run-** `docker build .`
4. **Run-** `docker run -p 8080:80 [the image id here]`

## Steps to run this project in Development Mode, with hot reloads using docker volumes
**When using WSL2 as a backend for Docker Desktop, the project should be created on or copied directly to the Linux file system. If the project is on the Windows file system, the volumes will likely not work. All docker commands should be run within WSL2 and not on Windows.**
1. To open your WSL2 operating system, type wsl in the Windows / Cortana Search Bar and click wsl.
2. In the WSL2 terminal change into your root user directory by running: `cd ~`
3. Run explorer.exe . to open up a file browser within WSL2.
4. Move the frontend project directory into the file browser window
5. Your project path should now look like this:  **/home/USER/frontend**
6. Using the WSL2 terminal build your Docker image as you typically would: `docker build -f Dockerfile.dev -t USERNAME:frontend .`
7. Using the WSL2 terminal, start and run a container. It is very important that you do not use a PWD variable as shown in the lecture video as this will not work. Use the `~` alias for the home directory or type out the full path:<br>
`docker run -it -p 3000:3000 -v /app/node_modules -v ~/frontend:/app USERNAME:frontend`<br>
or<br>
`docker run -it -p 3000:3000 -v /app/node_modules -v /home/USER/frontend:/app USERNAME:frontend`

















