# ctr-portainer

Stack Docker responsável por prover uma instância Portainer, permitindo gerenciar containers e stacks de forma centralizada.


## Pré-requisitos
- [Docker e Docker Compose](https://docs.docker.com/engine/install/)
- Permissão para executar scripts na pasta do projeto

## 1. Configurar variáveis de ambiente
1. Crie o arquivo `.env` a partir do modelo:

   ```bash
   cp .env.example .env
   ```

2. Edite o `.env` e ajuste:
   - Conforme a necessidade do ambiente

## 2. Preparar estrutura de pastas
1. Dê permissão ao script de preparação:

   Acesse a pasta do container e digite

   ```bash
   chmod +x prepare.sh
   ```

2. Execute o script para criar a hierarquia de diretórios esperada pelo stack:

   ```bash
   ./prepare.sh
   ```

## 3. Subir o stack
Depois de configurar e preparar tudo, suba os serviços com o Docker Compose:

```bash
docker compose up -d
```

## 4. Acesso ao Portainer
- URL: `https://<IP>:9443`
- No primeiro acesso, defina um usuário e senha fortes
- Garanta que a porta 9443 esteja liberada no firewall

## Manutenção rápida
- Atualizar imagens: `docker compose pull && docker compose up -d`
- Ver logs: `docker compose logs -f`
- Parar stack: `docker compose down`
