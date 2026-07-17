# BankX - Proyecto de Microservicios Bancarios

Este repositorio centraliza la documentación y los recursos necesarios para ejecutar el proyecto **BankX**, desarrollado como parte del **Bootcamp de Microservicios**.

Además de contener la infraestructura Docker (`docker-compose.yml`), este repositorio incluye las colecciones de Postman y los diagramas utilizados para documentar la solución.

---

# Arquitectura

La solución está basada en una arquitectura de microservicios desarrollada con **Java 17** y **Spring Boot WebFlux**, utilizando:

- API Gateway
- Eureka Server
- MongoDB
- Redis
- Apache Kafka
- JWT
- Docker
- OpenAPI (Swagger)

Cada microservicio posee su propia base de datos, siguiendo el patrón **Database per Service**.

---

# Contenido del repositorio

Este repositorio contiene los recursos necesarios para ejecutar y validar el proyecto.

```text
bank-infra/
│
├── docker-compose.yml
├── README.md
│
├── postman/
│   ├── BankX.postman_collection.json
│   └── BankX.postman_environment.json
│
└── diagrams/
    ├── architecture.drawio
    ├── architecture.png
    ├── customer-sequence.drawio
    ├── account-sequence.drawio
    ├── credit-sequence.drawio
    ├── movement-sequence.drawio
    ├── debit-card-sequence.drawio
    └── yanki-sequence.drawio
```

### Recursos

- **docker-compose.yml**: Orquestación de todos los microservicios.
- **postman/**: Colecciones y ambientes para validar las APIs.
- **diagrams/**: Diagramas de arquitectura y diagramas de secuencia desarrollados en Draw.io.
- **README.md**: Guía para la instalación y ejecución del proyecto.

---

# Requisitos

Antes de ejecutar el proyecto asegúrese de tener instalado:

- Java 17
- Maven 3.9 o superior
- Docker Desktop
- Docker Compose
- Git

---

# Clonar los repositorios

Crear una carpeta de trabajo:

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

Al finalizar, la estructura deberá quedar de la siguiente manera:

```text
bank-project/
│
├── bank-infra/
│   ├── docker-compose.yml
│   ├── README.md
│   ├── postman/
│   └── diagrams/
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

> **Importante:** Todos los repositorios deben ubicarse al mismo nivel para que Docker pueda localizar correctamente los Dockerfile utilizados por el archivo `docker-compose.yml`.

---

# Construcción de los microservicios

Antes de iniciar los contenedores es necesario generar el archivo **JAR** de cada microservicio.

Ingresar a cada proyecto y ejecutar:

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

Este proceso generará el archivo JAR dentro de la carpeta **target**, el cual será utilizado por Docker para construir la imagen correspondiente.

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

Para comprobar que todos los servicios están ejecutándose correctamente:

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

# Pruebas con Postman

Una vez iniciados los microservicios, importar en Postman los archivos ubicados en la carpeta:

```text
postman/
```

- BankX.postman_collection.json
- BankX.postman_environment.json

Estas colecciones permiten validar las funcionalidades implementadas por todos los microservicios del proyecto.

---

# Diagramas

La documentación técnica del proyecto incluye:

- Diagrama de arquitectura de la solución.
- Diagramas de secuencia de cada microservicio.

Todos ellos se encuentran en la carpeta:

```text
diagrams/
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
| Apache Kafka | 9092 |

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
- Docker Compose
- Maven
- OpenAPI (Swagger)
- JUnit 5
- Mockito
- JaCoCo
- Checkstyle

---

# Repositorios del proyecto

Puedes acceder a todos los repositorios desde nuestra organización en GitHub:
[**Ver todos los repositorios en Mis-Proyectos-Backend**](https://github.com/orgs/Mis-Proyectos-Backend/repositories)

Lista de servicios:

- [bank-infra](https://github.com/Mis-Proyectos-Backend/bank-infra)
- [customer-service](https://github.com/Mis-Proyectos-Backend/customer-service)
- [account-service](https://github.com/Mis-Proyectos-Backend/account-service)
- [credit-service](https://github.com/Mis-Proyectos-Backend/credit-service)
- [movement-service](https://github.com/Mis-Proyectos-Backend/movement-service)
- [debit-card-service](https://github.com/Mis-Proyectos-Backend/debit-card-service)
- [yanki-service](https://github.com/Mis-Proyectos-Backend/yanki-service)
- [api-gateway](https://github.com/Mis-Proyectos-Backend/api-gateway)
- [eureka-server](https://github.com/Mis-Proyectos-Backend/eureka-server)

> **Nota:** Estos repositorios se encuentran configurados como publicos temporalemnte. Si al intentar acceder a los enlaces visualiza un error, por favor notifíqueme para proceder a invitarlo como colaborador a la organización o realizar el cambio de visibilidad necesario para su revisión.

---

# Notas

- Cada microservicio cuenta con su propio repositorio Git, conforme a los lineamientos del Bootcamp.
- Cada microservicio dispone de su propio Dockerfile para la construcción de su imagen.
- La infraestructura completa del proyecto se despliega utilizando Docker Compose desde este repositorio.
- Las colecciones de Postman permiten validar las APIs desarrolladas.
- Los diagramas de arquitectura y secuencia forman parte de la documentación técnica del proyecto.
- Los contratos OpenAPI de cada microservicio se encuentran dentro de sus respectivos repositorios.

---

# Autor

**Danitza Chino Villalba**

Backend Developer | Java | Spring Boot | Microservices