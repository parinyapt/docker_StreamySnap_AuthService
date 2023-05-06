# Run StreamySnap Auth Service with Docker Compose

## Getting Started
#### Step 1: Add Environment Variable on .env file
```env
DB_ROOT_PASSWORD=
DB_USERNAME=
DB_PASSWORD=
DB_NAME=
BACKEND_PORT=
DB_PORT=
PHPMYADMIN_PORT=
NETWORK_NAME=
```
or
```bash
cp .env.template .env
```

#### Step 2: Create Docker Network
```bash
docker network create {NETWORK_NAME}
```

#### Step 3: Set Service Environment Variable in docker-compose.yml
```yml
TZ: Asia/Bangkok
DATABASE_TABLE_PREFIX: streamysnap_authservice_
APP_NAME: StreamySnap Auth Service
APP_BASE_URL: http://auth.prinpt.com
JWT_SIGN_KEY_AUTHSESSION: AUTHSESSION123456789
JWT_SIGN_KEY_TEMPORARYTOKEN: TEMPORARYTOKEN123456789
JWT_SIGN_KEY_ACCESSTOKEN: ACCESSTOKEN123456789
JWT_SIGN_KEY_REFRESHTOKEN: REFRESHTOKEN123456789
```
note: TZ is timezone that refer to [List of tz time zones](https://go.dev/src/time/zoneinfo_abbrs_windows.go)

#### Step 3: Run Docker Compose
```bash
docker-compose up -d
```

> By Parinya Termkasipanich