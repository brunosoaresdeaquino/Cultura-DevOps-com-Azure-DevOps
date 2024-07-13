# Cultura-DevOps-com-Azure-DevOps
Desafio Dio - Entendendo na Prática a Cultura DevOps com Azure DevOps
O Azure DevOps é um conjunto de ferramentas para desenvolvedores focadas no planejamento, colaboração e entregas. Ele pode ser integrado a outras ferramentas e serviços da Microsoft, como o Azure, para criar um pipeline de DevOps completo.

A cultura DevOps envolve cultura e colaboração em torno do gerenciamento do ciclo de vida de desenvolvimento de software. Ela visa aproximar as equipes de desenvolvimento e operações, gerando processos mais integrados e viabilizando a automação.

**Passos**

**1. Criar um Projeto no Azure DevOps**

- Acesse o Azure DevOps e crie um novo projeto.
- Nomeie seu projeto e selecione um modelo (por exemplo, "Projeto de Software").

**2. Configurar o Repositório Git**

- Crie um novo repositório Git local no seu computador.
- Adicione arquivos ao seu repositório e faça commit das alterações.
- Vincule seu repositório local ao repositório remoto do Azure DevOps.

**3. Criar um Pipeline de CI/CD**

- Crie um arquivo `azure-pipelines.yml` na raiz do seu projeto.
- Defina os estágios e tarefas do seu pipeline de CI/CD.
- Por exemplo, você pode definir um estágio de construção para compilar seu código, um estágio de teste para executar testes unitários e um estágio de implantação para implantar seu código em um servidor.

**4. Configurar o Pipeline de CI/CD (continuação)**

Aqui está um exemplo de um arquivo `azure-pipelines.yml`:

yaml

```
stages:
  - build
  - test
  - deploy

build:
  image: node:latest
  script:
    - npm install
    - npm run build

test:
  image: node:latest
  script:
    - npm test

deploy:
  image: nginx:latest
  script:
    - mv build/* /usr/share/nginx/html
```

**5. Executar o Pipeline de CI/CD**

- Faça push das alterações para o seu repositório remoto do Azure DevOps.
- O Azure DevOps iniciará automaticamente o pipeline de CI/CD.
- Você pode monitorar o progresso do pipeline no painel do Azure DevOps.

**6. Monitore e Melhore**

- Monitore os resultados do seu pipeline de CI/CD para identificar quaisquer problemas ou gargalos.
- Faça ajustes no seu pipeline conforme necessário para melhorar a eficiência e a qualidade.

## **Entendendo a Cultura DevOps com o Azure DevOps**

A cultura DevOps é uma abordagem que visa integrar o desenvolvimento de software com as operações, promovendo colaboração, automação e entrega contínua. O Azure DevOps é uma plataforma da Microsoft que oferece ferramentas para implementar práticas DevOps em projetos de desenvolvimento de software. Vamos explorar os principais conceitos e componentes do DevOps com foco no Azure DevOps.

**O que é DevOps?**

DevOps é uma filosofia que busca eliminar as barreiras entre desenvolvimento e operações, permitindo que equipes trabalhem juntas de forma mais eficiente. Em vez de silos separados, o DevOps promove a colaboração contínua, automação e feedback rápido.

**Por que o DevOps é necessário?**

O DevOps é necessário para superar os desafios enfrentados no desenvolvimento e implantação de software. Esses desafios incluem atrasos na entrega, erros frequentes, falta de visibilidade e dificuldade em manter a qualidade do código.

**Principais componentes do DevOps:**

1. **Planejamento Ágil e Gerenciamento de Projetos Lean**: Use práticas ágeis para planejar e gerenciar projetos de forma eficiente.
2. **Controle de Versão**: Utilize sistemas de controle de versão (como Git) para gerenciar e colaborar no código-fonte.
3. **Integração Contínua (CI)**: Automatize a compilação e testes do código sempre que houver alterações.
4. **Entrega Contínua (CD)**: Implante automaticamente o software em ambientes de teste e produção.
5. **Infraestrutura como Código (IaC)**: Gerencie a infraestrutura usando código, tornando-a mais previsível e escalável.
6. **Monitoramento e Registro em Log**: Colete dados telemétricos para entender o desempenho do software e identificar problemas.
7. **Aprendizado Validado**: Use dados para validar hipóteses e melhorar continuamente o processo.

**Exemplo prático:**

### Vamos criar um pipeline de CI/CD no Azure DevOps para um aplicativo web. Aqui estão os passos em módulos:

1. **Configuração do Projeto**: Crie um projeto no Azure DevOps e defina as configurações iniciais.
2. **Controle de Versão**: Configure um repositório Git para o código-fonte do aplicativo.
3. **Pipeline de CI**: Crie um pipeline de integração contínua para compilar, testar e gerar artefatos.
4. **Pipeline de CD**: Configure um pipeline de entrega contínua para implantar o aplicativo em um ambiente de teste.
5. **Monitoramento**: Configure métricas e alertas para monitorar o desempenho do aplicativo.

Com esses módulos, qualquer um estará no caminho para se tornar um especialista em DevOps com o Azure DevOps.

### Criando um exemplo de código para um pipeline de **Integração Contínua (CI)** usando o **Azure DevOps**. Neste exemplo, usaremos um aplicativo web simples em **Node.js**.

1. **Configuração Inicial**:
    - Crie um novo projeto no **Azure DevOps**.
    - Configure um repositório Git para o código-fonte do aplicativo.
2. **Pipeline de CI**:
    - Crie um arquivo chamado `azure-pipelines.yml` na raiz do seu repositório.
    - Adicione o seguinte conteúdo ao arquivo:

```
# azure-pipelines.yml

trigger:
- main

pool:
  vmImage: 'ubuntu-latest'

jobs:
- job: Build
  steps:
  - task: NodeTool@0
    inputs:
      versionSpec: '14.x'
    displayName: 'Install Node.js'
  - script: |
      npm install
      npm run build
    displayName: 'Build and Test'
  - task: PublishBuildArtifacts@1
    inputs:
      pathtoPublish: '$(Build.ArtifactStagingDirectory)'
      artifactName: 'drop'
    displayName: 'Publish Artifact'

```

1. **Explicação**:
    - O arquivo `azure-pipelines.yml` define o fluxo de trabalho do pipeline.
    - O gatilho (`trigger`) é configurado para executar o pipeline quando houver alterações no branch `main`.
    - A imagem da máquina virtual (`vmImage`) é definida como `ubuntu-latest`.
    - O job
        
        ```
        Build
        
        ```
        
        contém três etapas:
        
        - Instalação do Node.js.
        - Execução dos comandos `npm install` e `npm run build`.
        - Publicação dos artefatos gerados.
2. **Execução**:
    - Faça um commit no seu repositório.
    - O Azure DevOps detectará a alteração e executará o pipeline.
    - Verifique os logs para garantir que a compilação e os testes foram bem-sucedidos.

Lembre-se de adaptar esse exemplo ao seu projeto específico. O Azure DevOps oferece muitas opções para personalizar seus pipelines de CI/CD.

**Conclusão**

Neste projeto, criamos um projeto de DevOps completo com o Azure DevOps, incluindo um pipeline de CI/CD para compilar, testar e implantar nosso código. Ao adotar o DevOps com o Azure DevOps, podemos melhorar a colaboração, a eficiência e a qualidade do nosso desenvolvimento de software.
