# Traefik Localhost

- Crie uma rede chamada proxy

      $ docker network create proxy

- Execute o docker-compose.yml

      $ docker-compose up -d
      
- Execute o whoami para testar a rede

      $ docker run -d --name test --network proxy containous/whoami
      
### Usando Traefik com outro projeto docker-compose
- Adicionar os Labels dentro do servico

      labels:
        - "traefik.enable=true"
        - "traefik.docker.network=proxy"
        - "traefik.http.routers.retina.rule=Host(`nome-container.docker.localhost`)"
        - "traefik.http.routers.nome-container.entrypoints=web"

- Adicionar a rede proxy na área networks do seu serviço
- Declarar que a rede proxy será externa. Exemplo:
 
      networks:
        proxy:
          external: true 
           
### Links
- Dashboard Traefik: http://localhost:8080
- Whoami: http://test.docker.localhost/

      ### Os dominios .localhost sempre seguem o padrao [nomeContainer].docker.localhost
