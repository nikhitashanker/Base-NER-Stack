# Base Docker Stack

A simple [Docker](https://www.docker.com/) stack composed of [Node.js](https://nodejs.org/), [ExpressJS](https://expressjs.com/), and [React](https://reactjs.org/) using [Docker Compose](https://docs.docker.com/compose/reference/overview/)



## Overview

UCLA SWE's event portal. Coming Soon!



## Documentation

Hosted on GitHub Pages at TODO: [Swagger](https://swagger.io/docs/)? http://apidocjs.com/example/?



## Built With

- [React](https://reactjs.org/): JS library for building UIs

- [Node.js](https://nodejs.org/en/): JS run-time environment

- [ExpressJS](https://expressjs.com/): Web application framework for Node.js

- [Postgres](https://www.postgresql.org/): Open source relational database

- [Nginx](https://www.nginx.com/): Web server and reverse proxy

- [AWS](https://aws.amazon.com/) [EC2](https://aws.amazon.com/ec2/)/[Elastic Container Service](https://aws.amazon.com/ecs/): Deploys Docker containers



## Global Dependencies

 - General Dev Dependencies
    - Homebrew [install](https://brew.sh/)
    - Xcode Developer Tools (Mac)
       - `xcode-select --install`
    - Yarn [install](https://yarnpkg.com/en/docs/install)
    - Optional: Postgres [install](https://www.postgresql.org/)
 - Stack Dependencies
    - Docker [install](https://docs.docker.com/engine/installation/) and run daemon
      - Should include [Docker-Compose](https://docs.docker.com/compose/install/) in install
    - Node [install](https://nodejs.org/en/)
    - Create React App [install](https://github.com/facebookincubator/create-react-app)



## Stack Commands

- Run the stack
```bash
$ docker-compose up --build
```

- Stop the stack
  - In same terminal tab that we ran stack, Ctrl+C or: 
```bash
$ docker-compose down
```



## Architecture

- More specific READMEs are located in `client/` and `server/`.

| Component            | Service   | Container | Tech                   |
| -------------------- | --------- | --------- | ---------------------- |
| Client               | Client    | client    | React                  |
| Companies API/Server | Companies | companies | Node, Express          |
| Events API/Server    | Events    | events    | Node, Express          |
| Users API/Server     | Users     | users     | Node, Express          |
| Database             | Database  | -         | AWS RDS for PostgreSQL |

 - Client: React

   - The client service builds the React app and serves it with a simple Nginx server.
   - Run the stack:
     - Client in `client/` is available at [http://localhost:8081](http://localhost:8081)

- Server: ExpressJS

   - The server service runs your Express app for the Events and Users APIs.
   - Run the stack:
     - Companies server in `server/companies/` is available at [http://localhost:3001](http://localhost:3001) 
     - Events server in `server/events/` is available at [http://localhost:3002](http://localhost:3002) 
     - Users server in `server/users/` is available at [http://localhost:3003](http://localhost:3003)

- Database: PostgreSQL

   - TODO: Set up with [AWS RDS for PostgreSQL](https://aws.amazon.com/rds/postgresql/)



## Testing

TODO: [Codcept](http://codecept.io/), [TestCafe](https://github.com/DevExpress/testcafe)?



## References

- https://mherman.org/blog/developing-microservices-node-react-docker/
- https://github.com/mattpauldavies/nerp
- https://stackoverflow.com/questions/3370334/difference-between-acceptance-test-and-functional-test
- https://expressjs.com/en/guide/using-template-engines.html
- https://stackoverflow.com/questions/46872922/broken-c-std-libraries-on-macos-high-sierra-10-13/47401866
- https://medium.freecodecamp.org/expose-vs-publish-docker-port-commands-explained-simply-434593dbc9a3
- https://yarnpkg.com/en/docs/cli/run
- https://stackoverflow.com/questions/37929173/significance-of-port-3000-in-express-apps
- https://ux.stackexchange.com/questions/4752/search-vs-filter-what-is-the-difference
- https://stackoverflow.com/questions/27613724/need-to-create-an-api-doc-for-an-existing-application-written-with-nodejs-expres
- https://github.com/swagger-api/swagger-node
- https://swagger.io/swagger/media/blog/wp-content/uploads/2017/02/Documenting-An-Existing-API-with-Swagger-2.pdf
- https://stackoverflow.com/questions/26515473/writing-an-api-doc-for-swagger
- https://github.com/OAI/OpenAPI-Specification/tree/master/examples/v3.0
- https://scotch.io/tutorials/document-your-already-existing-apis-with-swagger
- https://www.reddit.com/r/docker/comments/8e9nj4/should_i_use_multiple_postgres_containers/
- https://stackoverflow.com/questions/38762709/one-or-multiple-databases-per-docker-container
- https://www.reddit.com/r/docker/comments/8tkq2v/one_database_container_for_everything_or_a/
