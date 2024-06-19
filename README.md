# DockerWordPress


> Passo a Passo para Rodar o Projeto

Pre Requisitos: 
  - Ter o WSL ou Ubuntu instalado na maquina.
  - Ter o Docker e o Docker Compose instalado no WSL/Ubuntu.
  - Ter o Git instalado na máquina

# Comandos para executar no terminal:

Crie o diretório desejado para o projeto e entre na pasta, Ex:
`mkdir wordpress`
`cd wordpress`

Clone o projeto dentro do diretório criado anteriormente e entre na pasta após o git carregar:
`git clone https://github.com/Kainak/DockerWordPress`
`cd DockerWordPress`

Crie o diretório config
`mkdir config`

Crie os arquivos vazios
`touch ./config/wp_php.ini`
`touch ./config/pma_php.ini`
`touch ./config/pma_config.php`

Crie o diretório wp-app:
`mkdir wp-app`

Crie um arquivo wp-config.php vazio
`touch ./wp-app/wp-config.php`

Crie e edite o arquivo .env
`nano .env`

Copie o conteúdo do arquivo .env.example que está aqui no repositório ou a seguir:
`WORDPRESS_DB_NAME=natan
WORDPRESS_DB_USER=natan
WORDPRESS_DB_PASSWORD=natan
MYSQL_ROOT_PASSWORD=natan
WP_REDIS_HOST=redis
WP_REDIS_PORT=6379
WP_REDIS_MAXTTL=900
WP_REDIS_KEY_SALT=test-salt`

- Cole no arquivo .env, alterando a senhas e nomes de usuário WORDPRESS E MYSQL conforme julgar necessário.
- Não recomendo alterar as linhas quer começarm em WP_REDIS pois isso impacta no projeto futuramente.
- Salve e feche o arquivo: Pressione CTRL+X, depois Y e ENTER para salvar e sair.
- OBS: Não é recomendado compartilhar o arquivo .env pois tem dados sesíveis.

Execute o Docker Compose
`sudo docker-compose up -d` para WSL
`sudo docker-compose up -d` para WSL2

Aguarde os arquivos serem inseridos no volume. Após isso:
- Acesse `http://localhost:8080/` para iniciar o WordPress
- Selecione a Linguagem
- Informe o Nome da Página, o nome do usuário, senha e e-mail válido e confirme;
- Informe Login e senhas cadastrados na pagina anterior

- O Wordpress terá as configurações para iniciar normalmente. Agora vamos ao Redis:
  ` cd wp-app`
  `sudo nano wp-config.php`
- Abrirá um editor de texto. Insira na linha de cima à "/* That's all, stop editing! Happy publishing. */"
`define('WP_REDIS_HOST', 'redis');
define('WP_REDIS_PORT', '6379');`

# Prontinho!

- Acesse http://localhost:8080/ - Vá na aba lateral equerda-> Plugins -> Botão Adicionar Plugin -> Perquise por "Redis Object Cache" e clique em "Instalar Agora" na primeira opção da pesquisa, e em seguida "Ativar"
- Acesso ao banco de dados: http://localhost:9092/index.php?route=/
  > A senha é a que foi criada no arquivo .env.
- Acesso ao Prometheus: http://localhost:9090/

Boa sorte!

