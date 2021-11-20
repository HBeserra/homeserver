# Servidor DNS Local

Pose ser utilizado para fornecer domínios para serviços de uso interno, recomendo utilizar apenas com subdomínios de sua propiedade devido a questões de segurança.

Redirecione o servidor dns primario do seu rotedor para o ip do servidor e o secundario para o google(8.8.8.8), cloudflare(1.1.1.1) ou o seu servidor dns de preferência.

Adicione os domínios internos e endereços IP dos servidores a `dnsmasq.conf`.

Por padrão o cache esta ativado o que pode melhorar a conexão local consideravelmente dependendo da distancia para o servidor dns.

### Build e execução

`docker build --pull --rm -f "Dockerfile" -t homeserver_dns:latest "."` 

`docker run --rm -p 53:53/udp --name="dns_server"  homeserver_dns:latest` 