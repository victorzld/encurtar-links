![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![Apache Maven](https://img.shields.io/badge/Apache%20Maven-C71A36?style=for-the-badge&logo=Apache%20Maven&logoColor=white)

# 🔗 Encurtador de Links

Um encurtador de URL's desenvolvido em **Java** com **Spring Boot**, que permite transformar links longos em versões curtas e fáceis de compartilhar. Utiliza **PostgreSQL** como banco de dados e está hospedado na nuvem com **Railway**.

As URL's encurtadas geradas têm **entre 5 e 10 caracteres**, garantindo unicidade e legibilidade.

## 🚀 Primeiros passos

Para utilizar a aplicação localmente, é necessário ter instalado em sua máquina:

- <a href="https://git-scm.com">Git</a>
- <a href="https://www.oracle.com/br/java/technologies/downloads/">JDK</a>
- **Recomendado**: <a href="https://www.jetbrains.com/pt-br/idea/">IntelliJ IDEA</a>

## 📌 Funcionalidades

- ✅ Encurtar uma URL
- ✅ Redirecionar usando código curto
- 🧠 Geração automática de códigos únicos

## 🧱 Diagrama

![Image](https://github.com/user-attachments/assets/502c230c-8976-47a5-8034-e651884fb899)

## 🧑‍💻 Tecnologias

- Java 21
- Spring Boot
- PostgreSQL
- Maven
- Railway (nuvem)

## 📥 Instalação Local

```bash
git clone https://github.com/victorzld/encurtar-links.git

cd encurtar-links

./mvnw spring-boot:run
```

- <p id="local-installation"> Configure o arquivo src/main/resources/application.properties com as informações do seu banco PostgreSQL:</p>

```bash
spring.datasource.url=jdbc:postgresql://<host>:<port>/<database>

spring.datasource.username=<seu_usuario>

spring.datasource.password=<sua_senha>

spring.jpa.hibernate.ddl-auto=update
```

## 🌐 Endpoints

| Método           | Endpoint                      | Descrição                                                                              |
| ---------------- | ----------------------------- | -------------------------------------------------------------------------------------- |
| <kbd>POST </kbd> | <kbd> /encurta-links</kbd>    | Recebe uma URL longa - [response details](#post-encurta)                               |
| <kbd>GET </kbd>  | <kbd> /r/{urlEncurtada}</kbd> | Recebe a url encurtada e redireciona para a url original - [response details](#get-encurta) |
|                  |

<h3 id="post-encurta">🔹 POST  /encurta-links</h3>

**Descrição**: Recebe uma URL longa e retorna um código curto.

**Request**:

```bash
{
    "urlOriginal": "https://www.exemplo.com.br/pagina-com-link-grande"
}
```

**Response**

```bash
{
    "id": 3,
    "urlLonga": "https://www.exemplo.com.br/pagina-com-link-grande",
    "urlEncurtada": "http://localhost:8080/a1B2c3"
    "urlCriadaEm": "2025-04-04T21:04:14.381287431"
}
```

<h3 id="get-encurta">🔹 GET  /r/{urlEncurtada}</h3>

**Descrição**: Redireciona para a URL original com base no código.

**Exemplo**:

```bash
    GET http://localhost:8080/a1B2c3
```

**Resposta esperada**:

- Redirecionamento automático para a URL origina: `https://www.exemplo.com.br/pagina-com-link-grande`

## 🛫 Instruções de Deploy na Railway

- 1. Acesse a <a href="https://railway.app" >Railway</a> e faça login.
- 2. Clique em “New Project” e escolha “Provision PostgreSQL”.
- 3. Após criar, copie as variáveis de conexão: host, database, username e password.
- 4. Caso não tenha feito, configure o arquivo application.properties como explicado na [seção](#local-installation) acima.

## Autor

Feito com 💚 por <a href="https://github.com/victorzld" >victorzld</a>

## Licença

<a href="/LICENSE" >MIT</a>
