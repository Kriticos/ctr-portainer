# ctr-portainer

Stack Docker responsável por prover uma instância Portainer para o laboratório BlackSkulp, permitindo gerenciar containers e stacks de forma centralizada.

## Pré-requisitos
- Docker e Docker Compose instalados
- Acesso ao repositório `ctr-portainer`
- Permissão para executar scripts na pasta do projeto

## 1. Configurar variáveis de ambiente
1. Crie o arquivo `.env` a partir do modelo:

   ```bash
   cp .env.example .env
   ```

2. Edite o `.env` e ajuste:
   - `BASE_DIR=/bskp-pro` (ou o caminho local que contém a pasta `stack`)
   - O caminho da pasta do container (`CONTAINER_PATH`) para apontar para `stack/ctr-portainer`
   - Demais variáveis conforme a necessidade do ambiente

## 2. Preparar estrutura de pastas
1. Entre na pasta do container:

   ```bash
   cd stack/ctr-portainer
   ```

2. Dê permissão ao script de preparação:

   ```bash
   chmod +x prepare.sh
   ```

3. Execute o script para criar a hierarquia de diretórios esperada pelo stack:

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
