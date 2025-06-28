Ecommerce/
│
├── docker-compose.yml
├── Ecommerce_BE/        # Django backend
│   ├── Dockerfile
│   └── ...
├── Ecomm_FE/            # React frontend
│   ├── Dockerfile
│   └── ...


2. Clone the repository
### git clone <repo-url>
### cd Ecommerce

2. Build and run Docker containers
### docker-compose up --build

### This will:

Build backend and frontend Docker images

### Set up PostgreSQL DB

### Run Django app on localhost:8000

### Serve React frontend on localhost:3000

3. Apply Django Migrations
Once containers are up, in a new terminal:

### docker exec -it backend python manage.py migrate

4. Create Django superuser (for admin access)
### docker exec -it backend python manage.py createsuperuser
### Then go to http://localhost:8000/admin and log in.

5. Access the App
### Frontend: http://localhost:3000

### Backend API: http://localhost:8000

### Admin Panel: http://localhost:8000/admin

### Common Dev Commands
```
# Restart containers
docker-compose restart

# Rebuild after code changes (if not live-mounted)
docker-compose up --build

# Backend shell
docker exec -it backend python manage.py shell

# PostgreSQL shell
docker exec -it db psql -U postgres -d ecommerce
```
✅ Notes
Backend volume is mounted: changes to code are reflected live (if using runserver)

For frontend, you must rebuild (--build) if your Dockerfile uses a static npm run build (as in Nginx setup)

### POSTMAN API Link
https://winter-sunset-629160.postman.co/workspace/Satish~13d9b3a3-5955-4b9b-8c98-c74b61e4c258/collection/17833650-8131d8f6-e8ee-4007-8446-c7f9864a9336?action=share&source=copy-link&creator=17833650



