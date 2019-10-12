# docker-websphere-liberty-sample
Exemplo de projeto java rodando em uma imagem websphere-liberty

# Pré requisitos
JDK 8+ instalada e configurada como variável de ambiente
MAVEN instalado e configurado como variável de ambiente
DOCKER instalado e rodando

# Compilando o projeto
Dentro do diretório bgs-hello-world/
mvn package
Isso fará com que o arquivo bgs-hello-world.war seja gerado na pasta target/, que está por sua vez configurada dentro do Dockerfile como parte do processo para geração da imagem.

# Fazendo o build da imagem
Dentro do diretório bgs-hello-world/
docker build -t bgs-hello-world .
Esse comando fará o build a partir do arquivo Dockerfile presente na pasta e gerará uma imagem com nome bgs-hello-world

# Consultando a imagem
docker images

# Rodando o container docker
docker run -d -p 80:9080 bgs-hello-world
Opção -d para rodar em background, deixando o terminal destravado e -p para expor a porta 9080 do container para a porta 80 da máquina localhost.
bgs-hello-world é o nome da imagem gerada no passo anterior.

# Verificando container rodando
docker ps

# Entrando no container para verificar a aplicação instalada ou checar os arquivos de log
docker exec -it {ID_CONTAINER} bash

# Verificando os logs
Após executar o comando anterior digitar os comandos abaixo:
cd logs
tail -50 messages.log

# Verificando a aplicação
cd /opt/ibm/wlp/usr/servers/defaultServer/dropins/

# Matando o container
docker kill {ID_CONTAINER}
