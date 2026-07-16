# BankX - Infraestructura Docker

Este repositorio contiene la infraestructura Docker del proyecto **BankX**, incluyendo el archivo `docker-compose.yml` necesario para desplegar todos los microservicios de la solución.

---

# Requisitos

Antes de ejecutar el proyecto, asegúrese de tener instalado:

- Java 17
- Maven 3.9 o superior
- Docker Desktop
- Docker Compose
- Git

---

# Clonar los repositorios

Crear una carpeta de trabajo, por ejemplo:

```bash
mkdir bank-project
cd bank-project
```

Clonar los siguientes repositorios dentro de la carpeta **bank-project**:

- bank-infra
- customer-service
- account-service
- credit-service
- movement-service
- debit-card-service
- yanki-service
- api-gateway
- eureka-server

Al finalizar, la estructura del proyecto deberá quedar de la siguiente manera:

```text
bank-project/
│
├── bank-infra/
│   ├── docker-compose.yml
│   └── README.md
│
├── customer-service/
├── account-service/
├── credit-service/
├── movement-service/
├── debit-card-service/
├── yanki-service/
├── api-gateway/
└── eureka-server/
```

> **Importante:** Todos los repositorios deben ubicarse al mismo nivel para que Docker pueda encontrar correctamente los Dockerfile definidos en el archivo `docker-compose.yml`.

---

# Construcción de los microservicios

Antes de iniciar los contenedores, es necesario generar el archivo **JAR** de cada microservicio.

Ingresar a cada uno de los siguientes proyectos y ejecutar:

```bash
mvn clean package -DskipTests
```

Microservicios:

- customer-service
- account-service
- credit-service
- movement-service
- debit-card-service
- yanki-service
- api-gateway
- eureka-server

Este proceso generará el archivo JAR dentro de la carpeta **target**, el cual será utilizado por Docker para construir la imagen de cada microservicio.

---

# Levantar la infraestructura

Ubicarse en el repositorio **bank-infra**:

```bash
cd bank-infra
```

Construir las imágenes e iniciar todos los contenedores:

```bash
docker compose up -d --build
```

---

# Verificar los contenedores

Para comprobar que todos los servicios se encuentran en ejecución:

```bash
docker ps
```

---

# Detener la infraestructura

Para detener todos los contenedores:

```bash
docker compose down
```

---

# Servicios disponibles

| Servicio | Puerto |
|----------|---------|
| API Gateway | 8080 |
| Customer Service | 8081 |
| Account Service | 8082 |
| Credit Service | 8083 |
| Movement Service | 8084 |
| Debit Card Service | 8086 |
| Yanki Service | 8087 |
| Eureka Server | 8761 |
| MongoDB | 27017 |
| Redis | 6379 |
| Kafka | 9092 |

---

# Tecnologías utilizadas

- Java 17
- Spring Boot
- Spring WebFlux
- Spring Data MongoDB
- MongoDB
- Redis
- Apache Kafka
- Spring Cloud Gateway
- Eureka Server
- JWT
- Docker
- Maven
- OpenAPI (Swagger)
- JUnit 5
- Mockito
- JaCoCo

---

# Notas

- Cada microservicio cuenta con su propio repositorio Git, conforme a los lineamientos del Bootcamp.
- Cada microservicio dispone de su propio Dockerfile para la construcción de su imagen.
- La infraestructura se despliega utilizando Docker Compose desde el repositorio **bank-infra**.
- La validación funcional de las APIs puede realizarse mediante las colecciones de Postman correspondientes.

---

# Autor

**Danitza Chino Villalba**

Backend Developer | Java | Spring Boot | Microservices