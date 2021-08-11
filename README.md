# Traefik Localhost

- Crie uma rede chamada proxy

      $ docker network create proxy

- Execute o docker-compose.yml

      $ docker-compose up -d
      
- Execute o whoami para testar a rede

      $ docker run -d --name test --network proxy containous/whoami
           
### Links
- Dashboard Traefik: http://localhost:8080
- Whoami: http://test.docker.localhost/

      ### Os dominios .localhost sempre seguem o padrao [nomeContainer].docker.localhost
