# TemplateForPlugin

Este projeto é um **template** para desenvolvimento de plugins Bukkit compatíveis com servidores Minecraft Beta 1.7.3. Ele facilita a estruturação do seu plugin, automatiza a build e a cópia do arquivo JAR gerado para a pasta de plugins do servidor, e usa Maven como sistema de build. É pensado especialmente para quem quer iniciar ou organizar projetos de plugins para servidores antigos com Java 8.

## Estrutura do Projeto

- `.devcontainer/`

  - `devcontainer.json`: Arquivo para configurar ambiente de desenvolvimento usando Docker/DevContainer. Inclui imagem baseada em Java 8 + Maven e monta a pasta do seu servidor Minecraft local na máquina virtual, facilitando testes e builds automáticos. _Altere a linha_ `source` _para a pasta do seu servidor_

- `src/main/java/com/blockycraft/meuplugin/MeuPlugin.java`

  - Exemplo de classe principal do plugin. O arquivo inicial possui estrutura básica para expansão.

- `src/main/resources/plugin.yml`

  - Arquivo de configuração do plugin. Define a classe principal, versão, autor e descrição do plugin, conforme especificação da Bukkit API.

- `pom.xml`

  - Arquivo de configuração Maven responsável por dependências, builds automáticas e cópia do JAR para a pasta correta do servidor.
  - Define como dependência principal o Bukkit 1.7.3-beta-SNAPSHOT a partir do repositório SpigotMC.
  - Configura build para Java 8 compatível.

- `.gitignore`

  - Ignora diretórios `target/` e `.vscode/` no versionamento.

- `.gitattributes`
  - Normaliza o final de linha para LF em arquivos de texto.

## Tutorial: Como usar o template

### 1. Pré-requisitos

- **Java 8** instalado.
- **Maven** instalado (ou utilize o DevContainer Docker já pronto).
- Pasta do servidor Minecraft Beta 1.7.3, incluindo o arquivo `server.jar`.
- IDE recomendada: Visual Studio Code ou IntelliJ IDEA.

### 2. Clonar o repositório

Clone o projeto em seu ambiente local:
`git clone https://github.com/andradecore/TemplateForPlugin.git`

### 3. Configurar o ambiente (opcional: DevContainer)

Caso use o DevContainer, certifique-se que a pasta do servidor Minecraft está no caminho exato especificado em `devcontainer.json`:

`"source": "C:\Users\Bernardo Andrade\Documents\BlockyCRAFT",`
`"target": "/minecraft-server"`

Altere se necessário para sua pasta local do servidor.

Abra o projeto no VSCode e use **Reabrir no Dev Container**.

### 4. Ajustar a classe principal

Renomeie e edite a classe `MeuPlugin.java` e o pacote conforme seu plugin. Mude o caminho também no `plugin.yml`:

**plugin.yml**

```
main: com.blockycraft.meuplugin.ClassePrincipal (caminho da classe principal)
version: 1.0
author: [Seu nome]
description: [Descrição do plugin]
```

### 5. Ajustar dependências e configuração do Maven

No `pom.xml`, confira os caminhos:

- O caminho relativo para o `server.jar` do Minecraft Beta 1.7.3
- Diretório de saída do plugin JAR (`/plugins` do servidor)

Edite conforme sua necessidade.

### 6. Compilar e instalar o plugin

Com o Maven instalado:
`mvn clean package`

O arquivo `.jar` será automaticamente copiado para a pasta de plugins do seu servidor, se configurado corretamente.

### 7. Testar no servidor

Inicie seu servidor Minecraft Beta 1.7.3. O plugin deverá estar disponível e carregado pelo Bukkit.

## Recomendações

- Mantenha uma estrutura de pacotes clara para cada plugin.
- Utilize o ambiente isolado do DevContainer para não poluir seu sistema.
- Documente cada funcionalidade nova no README ou no próprio código.

## Contato:

- Discord: https://discord.gg/tthPMHrP
