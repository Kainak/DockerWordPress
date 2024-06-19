# DockerWordPress


> Passo a Passo para Rodar o Projeto

Pre Requisitos: 
  - Ter o WSL ou Ubuntu instalado na maquina.
  - Ter o Docker e o Docker Compose instalado no WSL/Ubuntu.

# Comandos para executar no terminal:
> Crie o diretório desejado para o projeto e entre na pasta, Ex:
`mkdir wordpress`
`cd wordpress`

> Crie o diretório config
`mkdir config`

> Crie os arquivos vazios
`touch ./config/wp_php.ini`
`touch ./config/pma_php.ini`
`touch ./config/pma_config.php`

> Crie o diretório wp-app:
`mkdir wp-app`

> Crie um arquivo wp-config.php vazio
`touch ./wp-app/wp-config.php`

> Crie e edite o arquivo .env
`nano .env`

> Cole o conteúdo do .env.exemplo e altere a senha conforme julgar ncessário:
`DB_NAME='<nome do banco de dados>'
DB_USER='Usuario do Banco'
DB_PASSWORD='senha'
DB_ROOT_PASSWORD=Senha do root do banco`

> Vá para o diretório onde está o docker-compose.yml
`cd /opt/staks/wordpress`

> Execute o Docker Compose
`sudo docker-compose up -d`

> Aguarde os arquivos serem inseridos no volume. Após isso:
- Acesse `http://localhost:9092/` para iniciar o WordPress
- Informe o Nome da Página, o nome do usuário, senha e e-mail válido e confirme;
- Informe Login e senhas cadastrados na pagina anterior

- O Wordpress terá as configurações para iniciar normalmente. Agora vamos ao Redis:
- 


- Acesse ``

cd /var/www/html

