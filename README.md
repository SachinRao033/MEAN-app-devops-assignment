In this DevOps task, you need to build and deploy a full-stack CRUD application using the MEAN stack (MongoDB, Express, Angular 15, and Node.js). The backend will be developed with Node.js and Express to provide REST APIs, connecting to a MongoDB database. The frontend will be an Angular application utilizing HTTPClient for communication.  

The application will manage a collection of tutorials, where each tutorial includes an ID, title, description, and published status. Users will be able to create, retrieve, update, and delete tutorials. Additionally, a search box will allow users to find tutorials by title.

## Project setup

### Node.js Server

cd backend

npm install

You can update the MongoDB credentials by modifying the `db.config.js` file located in `app/config/`.

Run `node server.js`

### Angular Client

cd frontend

npm install

Run `ng serve --port 8081`

You can modify the `src/app/services/tutorial.service.ts` file to adjust how the frontend interacts with the backend.

Navigate to `http://localhost:8081/`

----
# MEAN CRUD App - DevOps Assignment

## Project Setup
- Follow original README instructions for local setup.
- Deploy: `docker-compose up -d` on VM.

## Deployment Instructions
1. Clone repo: `git clone <your-repo-url>`
2. On VM: `cd MEAN-app-devops-assignment/crud-dd-task-mean-app`
3. Run: `docker-compose up -d`
4. Access: http://<vm-ip>

## CI/CD
- GitHub Actions automates build, push, and deploy on push to `main`.

## Screenshots
- CI/CD Run: ![cicd](screenshots/cicd.png)
- Docker Build: ![build](screenshots/build.png)
- App UI: ![ui](screenshots/ui.png)
- Docker PS: ![docker-ps](screenshots/docker-ps.png)
- Nginx Config: ![nginx](screenshots/nginx.png)
- EC2 Security Group: ![ec2](screenshots/ec2.png)
