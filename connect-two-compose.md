Connect two seperate docker-compose.

First thing we need to create network, this is where two docker-compose going to connect.

Make sure to create a network with:

```
docker network create <network-name>
```

Then specify the network on each docker-compose

Fisrt compose:
```
version: "3.5"

services:
  postgres:
    container_name: postgres
    image: postgres
    restart: unless-stopped
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: admin
      PGDATA: /data/postgres
    volumes:
      - "./data/pg:/data/postgres"
    ports:
      - "5432:5432"
    networks:
      - solanaland-network

  pgadmin:
    container_name: pgadmin
    image: dpage/pgadmin4
    restart: unless-stopped
    environment:
      PGADMIN_DEFAULT_EMAIL: postgres@digiteer.dev
      PGADMIN_DEFAULT_PASSWORD: admin
      PGADMIN_CONFIG_SERVER_MODE: 'False'
    volumes:
      - "./data/pgadmin/lib:/root/.pgadmin"
    ports:
      - 5050:80
    depends_on:
      - postgres
    networks:
      - solanaland-network

volumes:
  data:

networks:
  solanaland-network:
    external:
      name: solanaland-network
```

Second compose:
```
version: "3.1"

services:
  web:
    container_name: ror-starter
    image: digiteer/heroku-ror:2.7.3
    ports:
      - "3000:3000"
    environment:
      RAILS_ENV: development
    volumes:
      - ./:/app/user
    networks:
      - solanaland-network
    extra_hosts:
      host.docker.internal: host-gateway

networks:
  solanaland-network:
    external:
      name: solanaland-network
```

References:
[docker network](https://docs.docker.com/compose/how-tos/networking/)
