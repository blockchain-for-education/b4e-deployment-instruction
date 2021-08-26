# B4E Deployment Instruction

##  Packages for actors of the system include:

- Docker compose [packages](/ministry) for Ministry 
- Docker compose [packages](/school) for University
- Docker compose [packages](/primary) for Primary School
- Docker compose [packages](/secondary) for Secondary School
- Docker compose [packages](student) for Student 
- Docker compose [packages](/verifier) for Verifier 

## Requirements

- Installed docker and docker-compose for deployment server
- Instruction : https://docs.docker.com/engine/install/

## Install

### 1. Install docker-compose file for Ministry
    
- [Package](/ministry)

#### 1.1 Requirement
  - SSL certificate for deployment domain 
#### 1.2 Install
#####1.2.1. Copy file private key and certificate for backend into
    /etc/letsencrypt/archive/ministry-backend.b4e.vn/privkey.pem
    /etc/letsencrypt/archive/ministry-backend.b4e.vn/fullchain.pem 
#####1.2.2. Copy file private key and certificate for frontend into
    /etc/letsencrypt/archive/ministry.b4e.vn/privkey.pem
    /etc/letsencrypt/archive/ministry.b4e.vn/fullchain.pem
#####1.2.3. Configure file .env
######Environment variables:

    B4E_VERSION=1.2.2
    MINISTRY_PEERS_IP=139.59.125.235

###### setup mongo superadmin account
    MINISTRY_MONGO_USERNAME=ministry
    MINISTRY_MONGO_PASSWORD=123456

###### web backend: jwt secret for authenticate user
    TOKEN_SECRET=QRA27XVAFD8A7FD6X
###### preset account for ministry
    MINISTRY_ACCOUNT_EMAIL=bgd@ministry.edu.vn
    MINISTRY_ACCOUNT_PASSWORD=12341234

#####1.2.4 Run file docker compose
    user@host$ docker-compose up

### 2. Install docker-compose file for University
- [Package](/school)
#### 2.1 Requirement
  - SSL certificate for deployment domain 
#### 2.2 Install
#####2.2.1. Copy file private key and certificate for backend into
    /etc/letsencrypt/archive/school-backend.b4e.vn/privkey.pem
    /etc/letsencrypt/archive/school-backend.b4e.vn/fullchain.pem 
#####2.2.2. Copy file private key and certificate for frontend into
    /etc/letsencrypt/archive/school.b4e.vn/privkey.pem
    /etc/letsencrypt/archive/school.b4e.vn/fullchain.pem
#####2.2.3. Configure file .env
######Environment variables:

    B4E_VERSION=1.2.2
    MINISTRY_PEERS_IP=139.59.125.235
    MY_SCHOOL_PEER_IP=139.59.125.235

###### setup mongo superadmin account
    MINISTRY_MONGO_USERNAME=school
    MINISTRY_MONGO_PASSWORD=123456

###### web backend: jwt secret for authenticate user
    TOKEN_SECRET=QRA27XVAFD8A7FD6X
###### preset account for university
    STAFF_ACCOUNT_EMAIL=bkhn@hust.edu.vn
    STAFF_ACCOUNT_PASSWORD=12341234

#####2.2.4 Run file docker compose
    user@host$ docker-compose up

### 3. Install docker-compose file for Primary School
- [Package](/primary)
- Install same as University

### 4. Install docker-compose file for Secondary School
- [Package](/secondary)
- Install same as University

### 5. Install docker-compose file for Student
- [Package](/student)
#### 5.1 Requirement
  - SSL certificate for deployment domain 
#### 5.2 Install
#####5.2.1. Copy file private key and certificate for backend into
    /etc/letsencrypt/archive/student-backend.b4e.vn/privkey.pem
    /etc/letsencrypt/archive/student-backend.b4e.vn/fullchain.pem 
#####5.2.2. Copy file private key and certificate for frontend into
    /etc/letsencrypt/archive/student.b4e.vn/privkey.pem
    /etc/letsencrypt/archive/student.b4e.vn/fullchain.pem
#####5.2.3. Configure file .env
######Environment variables:

    B4E_VERSION=1.2.2
    VALIDATOR_ENDPOINT=139.59.125.235:4004

###### setup mongo superadmin account
    MINISTRY_MONGO_USERNAME=student
    MINISTRY_MONGO_PASSWORD=123456

###### web backend: jwt secret for authenticate user
    TOKEN_SECRET=QRA27XVAFD8A7FD6X

#####5.2.4 Run file docker compose
    user@host$ docker-compose up

### 6. Install docker-compose file for Verifier
- [Package](/verifier)
- Install same as Student