# CRIANDO AMBIENTES REAIS COM DOCKER 
- DevOps: preocupação em como integrar uma aplicação existente em servidores online, garantindo consistência em ambientes diversos.
- O uso de containers é necessário para empacotar o código e também as dependências, para que tudo necessário para rodar a aplicação esteja concentrado em um local só e evitando que dependências externas do servidor possam atrapalhar o processo de funcionamento.

- Para usar o docker em sua aplicação, precisamos criar um Dockerfile, um arquivo de instruções que automatiza o deploy. Neste projeto, o interessante é criarmos um container a partir de uma imagem Python com mínimas libs instaladas. Recomendação: usar imagens do Alpine por serem mais leves.
    - Além do Dockerfile, é interessante que tenha um .dockerignore para evitar que arquivos que pesados e não essenciais entrem no container (venv, node_modules, ...)

- Comandos para executar o container:
    - Buildar: `docker build -t [tag] .`
    - Executar (após o build): `docker run [porta:porta]`

# AUTOMATIZANDO DO BUILD AO DEPLOY
- O Docker Compose é uma ferramenta extremamente útil para automatizar o processo de gerar e subir um container, sendo escrita em YAML e permitindo grande controle aos profissionais de DevOps.
- O código está escrito no `docker-compose.yml`.
- Comando para executar o compose: `docker compose up [-d, opcional]`.

## ACTIONS
- Ferramenta do GitHub onde podemos automatizar a geração de imagens Docker. Podemos definir para que, assim que um commit for feito à branch principal, sejam rodadas pipelines para gerar uma imagem, rodar testes unitários, analisar percentuais de cobertura do projeto e mais.
- Uma boa prática (e também convenção) é utilizar labels `MAJOR` ou `MINOR` pra marcar uma versão da sua aplicação.
