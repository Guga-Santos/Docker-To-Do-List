# Boas-vindas ao repositório do projeto Docker Todo List!

Para realizar o projeto, atente-se a cada passo descrito a seguir, e se tiver qualquer dúvida, nos envie por _Slack_! #vqv 🚀

Aqui você vai encontrar os detalhes de como estruturar o desenvolvimento do seu projeto a partir deste repositório, utilizando uma branch específica e um _Pull Request_ para colocar seus códigos.

# Termos e acordos

Ao iniciar este projeto, você concorda com as diretrizes do Código de Conduta e do Manual da Pessoa Estudante da Trybe.

# Entregáveis

<details>
  <summary><strong>🤷🏽‍♀️ Como entregar</strong></summary><br />

Para entregar o seu projeto você deverá criar um _Pull Request_ neste repositório.

Lembre-se que você pode consultar nosso conteúdo sobre [Git & GitHub](https://app.betrybe.com/course/4d67f5b4-34a6-489f-a205-b6c7dc50fc16/) e nosso [Blog - Git & GitHub](https://blog.betrybe.com/tecnologia/git-e-github/) sempre que precisar!!
</details>

<details>
  <summary><strong>👨‍💻 O que deverá ser desenvolvido</strong></summary><br />

Neste projeto você irá:

1. **_Conteinerizar_** aplicações;
1. Criar uma conexão entre elas;
1. Orquestrar seu funcionamento.

Temos uma aplicação full-stack neste repositório: um **aplicativo de tarefas**! Esta aplicação precisa ser conteinerizada para funcionar. Você deverá desenvolver os arquivos de configuração para cada frente específica: `Front-end`, `Back-end` e, no nosso caso, para um aplicativo de `teste` que valida se as aplicações estão se comunicando.

Você deverá criar as imagens para as aplicações e configurar essas imagens com o `docker-compose`.

Para isto, você irá utilizar uma série de comandos do `docker` com diferentes níveis de complexidade.

Cada comando deverá ser escrito em seu próprio arquivo.

Para isto, siga os seguintes passos:

1. Leia o requisito e crie um arquivo chamado `commandN.dc` no diretório `docker-commands`, onde `N` é o número do requisito. Por exemplo:

    ```text
    Requisito 1: ./docker/docker-commands/command01.dc
    Requisito 2: ./docker/docker-commands/command02.dc
    Requisito 3: ./docker/docker-commands/command03.dc
    ```
    **⚠️ É muito importante que os seus arquivos tenham exatamente estes nomes! ⚠️**


2. Escreva neste arquivo o comando do CLI *(Interface de Linha de Comando)* do Docker que resolve o requisito. Um exemplo de como vai ficar seu arquivo:

    ```dc
    docker network inspect bridge
    ```

Os arquivos principais do projeto estão na pasta `docker`, na raiz do projeto. Nela estão contidos:

1. Pasta `docker-commands`: onde ficarão os comandos exigidos pelos requisitos;
   - **⚠️ Importante: você deve assumir que essa é a pasta raiz para os comandos.**
   - Por exemplo, se você precisa referenciar um caminho em um comando, você deve assumir que sua pasta raiz esta partindo de `./docker`.
2. Pasta `todo-app`: onde fica a nossa **pseudo-aplicação**, que servirá como base para nossos `Dockerfile`s e `Compose`;
   - **⚠️ Essa aplicação conta com um [**README.md**](./docker/todo-app/README.md) próprio, que deve ser usado como referência na criação dos scripts!**

Quando for necessário fazer a orquestração das aplicações, o arquivo `docker-compose.yml` deverá ser criado na pasta `./docker`.

</details>

<details>
  <summary><strong>🗓 Data de Entrega</strong></summary><br />

* Este projeto é individual
* São `2` dias de projeto
* Data para entrega final do projeto: `25/05/2022 14:00`

</details>

# Orientações

<details>
  <summary><strong>📋︎ Sobre o avaliador</strong></summary><br />

**⚠️ Importante: ⚠️**

```text
Para que o avaliador funcione corretamente é importante que a instalação do 
Docker (vista no dia 1) seja feita corretamente.

Aqui também é importante que o seu usuário esteja no grupo `docker` (para que 
não haja a necessidade de rodar comandos utilizando o `sudo`)
```

O avaliador cria um **container especial** para executar a avaliação de `comandos`, `Dockerfiles` e `docker-compose`.

Esse container é temporário, portanto, ao começar ou terminar os testes locais, o avaliador remove automaticamente esse mesmo container, assim como seu volume associado.

O volume desse container mapeia a pasta `./docker/` do seu projeto, para dentro dele, ou seja, a raiz desse container vai conter as pastas `./docker-commands/`, `./todo-app/` e seu arquivo `./docker-compose.yml` quando estiver pronto.

Isso significa que, se pudéssemos olhar para dentro do container de avaliação, veríamos a seguinte estrutura:

```bash
.
├── docker-commands
└── todo-app
    ├── back-end
    │   └── *
    ├── front-end
    │   └── *
    └── tests
        └── *
```

Portanto, é importante entender que os comandos docker escritos em `command*.dc` estarão rodando dentro desse container especial (e não a partir da raiz do projeto, como em projetos anteriores).

Obs.: Caso o seu projeto esteja localizado em um diretório que contenha espaço no nome, os testes falharão (Exemplo: Projetos Trybe). Nesse caso basta mover o projeto de pasta ou renomeá-lo (Exemplo: Projetos-Trybe ou ProjetosTrybe). Isso acontece porque o comando docker usado nos testes irá entender que o espaço no nome significa que está passando algum tipo de opção ou complemento extra.

</details>

<details>
  <summary><strong>‼️ Antes de começar a desenvolver</strong></summary><br />

1. Clone o repositório
* `git clone git@github.com:tryber/sd-019-b-project-docker-todo-list.git`
* Entre na pasta do repositório que você acabou de clonar:
  * `cd sd-019-b-project-docker-todo-list`

2. Instale as dependências:
  * `npm install`

* Verifique se os testes estão executando:
  * `npm test` (os testes devem rodar e falhar)

3. Crie uma branch a partir da branch `master`

* Verifique que você está na branch `master`
  * Exemplo: `git branch`
* Se não estiver, mude para a branch `master`
  * Exemplo: `git checkout master`
* Agora, crie uma branch onde você vai guardar os commits do seu projeto
  * Você deve criar uma branch no seguinte formato: `nome-de-usuario-nome-do-projeto`
  * Exemplo:
    * `git checkout -b joaozinho-sd-019-b-project-docker-todo-list`

4. Adicione a sua branch com o novo `commit` ao repositório remoto

- Usando o exemplo anterior:
  - `git push -u origin joaozinho-sd-019-b-project-docker-todo-list`

5. Crie um novo `Pull Request` _(PR)_
* Vá até a página de _Pull Requests_ do repositório no GitHub: [docker-todo-list](https://github.com/tryber/sd-019-b-project-docker-todo-list/pulls)
* Clique no botão verde _"New pull request"_
* Clique na caixa de seleção _"Compare"_ e escolha a sua branch **com atenção**
* Clique no botão verde _"Create pull request"_
* Adicione uma descrição para o _Pull Request_ e clique no botão verde _"Create pull request"_
* **Não se preocupe em preencher mais nada por enquanto!**
* Volte até a [página de _Pull Requests_ do repositório](https://github.com/tryber/sd-019-b-project-docker-todo-list/pulls) e confira que o seu _Pull Request_ está criado

</details>

<details>
  <summary><strong>⌨️ Durante o desenvolvimento</strong></summary><br />

* ⚠ **PULL REQUESTS COM ISSUES NO DOCKERFILE-LINTER NÃO SERÃO AVALIADOS. É PRECISO RESOLVÊ-LAS ANTES DE FINALIZAR O DESENVOLVIMENTO!** ⚠

* Faça `commits` das alterações que você fizer no código regularmente;

* Lembre-se de atualizar o repositório remoto após um (ou alguns) `commits`;

* Os comandos que você utilizará com mais frequência são:
  1. `git status` _(para verificar o que está em vermelho - fora do stage - e o que está em verde - no stage)_
  2. `git add` _(para adicionar arquivos ao stage do Git)_
  3. `git commit` _(para criar um commit com os arquivos que estão no stage do Git)_
  4. `git push -u origin nome-da-branch` _(para enviar o commit para o repositório remoto na primeira vez que fizer o `push` de uma nova branch)_
  5. `git push` _(para enviar o commit para o repositório remoto após o passo anterior)_

</details>

<details>
  <summary><strong>🤝 Após terminar o desenvolvimento (opcional)</strong></summary><br />

Para **"entregar"** seu projeto, siga os passos a seguir:

* Vá até a página **DO SEU** _Pull Request_, adicione a label de _"code-review"_ e marque seus colegas
  * No menu à direita, clique no _link_ **"Labels"** e escolha a _label_ **code-review**
  * No menu à direita, clique no _link_ **"Assignees"** e escolha **o seu usuário**
  * No menu à direita, clique no _link_ **"Reviewers"** e digite `students`, selecione o time `tryber/students-sd-019-b`

Se ainda houver alguma dúvida sobre como entregar seu projeto, [aqui tem um video explicativo](https://vimeo.com/362189205).

</details>

<details>
  <summary><strong>🕵🏿 Revisando um pull request</strong></summary><br />

Use o conteúdo sobre [Code Review](https://course.betrybe.com/real-life-engineer/code-review/) para te ajudar a revisar os _Pull Requests_.

</details>

<details>
  <summary><strong>📜 Não se esqueça de consultar as documentações!</strong></summary><br />

⚠️ **Importante**:

Esse projeto tem como intuito te treinar para ter mais familiaridade com a documentação de aplicações, portanto, poderão haver alguns comandos ou atributos que não estão no course, mas que devem ser descritos no decorrer dos requisitos.

Nesses casos, é importante se atentar àquilo que o requisito pede e lembrar sempre de utilizar a [documentação oficial](https://docs-docker-com.translate.goog/engine/reference/commandline/cli/?_x_tr_sl=en&_x_tr_tl=pt&_x_tr_hl=pt-BR&_x_tr_pto=nui) do Docker para pesquisar detalhes sobre comandos.

Ao criar um Dockerfile para o nosso **pseudo-aplicativo**, seu `README` (`./docker/tests/README.md`) deve servir como "tradutor" para os passos de execução. Lembre-se de que o `Dockerfile` é como uma receita para execução dessas aplicações.

Aqui, também é importante a utilização do comando `--help` no CLI (`docker <comando> <subcomando> --help`), dado que para cada comando do docker, é possível aplicar subcomandos ou parâmetros, exemplo: `docker network --help`

</details>

<details>
  <summary><strong>🛠 Testes</strong></summary><br />

⚠ **É necessário ter o Docker instalado corretamente na sua máquina para rodar os testes locais**.

Todos os requisitos do projeto serão testados automaticamente por meio do Jest. Basta executar o comando abaixo:

```bash
npm test
```

Você pode rodar um arquivo de `test` por vez, exemplo:

```bash
npm test 01container
```
⚠ **Atenção:** ⚠
Não utilize a função `.only` ou `.skip` após o describe. Os testes precisam rodar por completo para que o projeto seja avaliado localmente.

</details>

<details>
  <summary><strong>🗣 Nos dê feedbacks sobre o projeto!</strong></summary><br />

Ao finalizar e submeter o projeto, não se esqueça de avaliar sua experiência preenchendo o formulário.
**Leva menos de 3 minutos!**

[FORMULÁRIO DE AVALIAÇÃO DE PROJETO](https://be-trybe.typeform.com/to/ZTeR4IbH)

⚠ **O avaliador automático não necessariamente avalia seu projeto na ordem em que os requisitos aparecem no readme. Isso acontece para deixar o processo de avaliação mais rápido. Então, não se assuste se isso acontecer, ok?**

</details>

<details>
  <summary><strong>🗂 Compartilhe seu portfólio!</strong></summary><br />

Você sabia que o LinkedIn é a principal rede social profissional e compartilhar o seu aprendizado lá é muito importante para quem deseja construir uma carreira de sucesso? Compartilhe esse projeto no seu LinkedIn, marque o perfil da Trybe (@trybe) e mostre para a sua rede toda a sua evolução.

</details>

# Requisitos obrigatórios do projeto

## Comandos docker

⚠ Lembre-se das instruções da seção [Entregáveis](#Entregáveis), especialmente no tópico `O que deverá ser desenvolvido`!

### 1. Crie um container em modo interativo, sem rodá-lo, nomeando-o como `01container` e utilizando a imagem `alpine` na versão `3.12`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command01.dc`.

#### Observações técnicas

- O container **não deve ser inicializado**, somente criado;
- O container deve estar preparado para acesso interativo.

#### Dicas

- Lembre-se que um parâmetro não é necessariamente aplicável a apenas um comando.

#### O que será testado

- O `nome` do container deve ser `01container`;
- O container deve usar a imagem `alpine` na versão `3.12`;
- O `status` do container deve ser `created`;
- O container **não deve** estar em execução após ter sido criado.

</details>

### 2. Inicie o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command02.dc`.

#### Observações técnicas

- O container `01container`, que acabou de ser criado e está parado, deve ser iniciado;
- Se o container tiver sido iniciado de modo interativo, ele deve se manter ativo ao iniciá-lo.
  
#### O que será testado

- O avaliador verificará se o container está parado;
- O avaliador executará o comando criado neste requisito;
- O container **deve** estar em execução.

</details>

### 3. Liste os containers filtrando pelo nome `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command03.dc`.

#### Dicas

- Praticamente todo comando de listagem no Docker possui uma forma de filtragem.

#### O que será testado

- O comando deve retornar uma lista contendo informações **apenas** do `01container`.

</details>

### 4. Execute o comando `cat /etc/os-release` no container `01container` sem se acoplar a ele

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command04.dc`.

#### Observações técnicas

- O container deve estar rodando e você deve ser capaz de **executar um comando** nesse container.

#### Dicas

- É possível fazer isso sem usar o comando `attach`.

#### O que será testado

- Que o comando retornará os dados corretos da `distro` no container:
  - `NAME="Alpine Linux"`
  - `ID=alpine`
  - `VERSION_ID=3.12`

</details>

### 5. Remova o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará os comandos nos arquivos `command05.dc` e `command03.dc`.

#### O que será testado

- O avaliador rodará o comando 5;
- O avaliador validará o processo com o comando 3.

</details>

### 6. Faça o download da imagem `nginx` com a versão `1.21.3-alpine` sem criar ou rodar um container

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command06.dc`.

#### O que será testado

  - Que a imagem correta foi baixada;
  - Que nenhum container foi iniciado para isso.

</details>

### 7. Rode um novo container com a imagem  `nginx` com a versão `1.21.3-alpine` em segundo plano nomeando-o como `02images` e mapeando sua porta padrão de acesso para porta `3000` do sistema hospedeiro

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command07.dc`.

#### O que será testado

  - Que o container foi iniciado corretamente;
  - Que é possível ter acesso ao container pelo endereço `localhost:3000`;
  - Que a página retorna o valor esperado.

</details>

### 8. Pare o container `02images` que está em andamento

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command08.dc`.

#### O que será testado

  - Que não há nenhum container ativo após seu comando.

</details>

## Dockerfile

**⚠️ As aplicações a seguir contam com um [**README.md**](./docker/todo-app/README.md) próprio, que deve ser usado como referência na criação dos scripts!**

### 9. Gere uma build a partir do Dockerfile do `back-end` do `todo-app` nomeando a imagem para `todobackend`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command09.dc`.

#### Dicas 

- O comando `ADD` do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.

#### O que será testado

- Se existe um arquivo `Dockerfile` em `./docker/todo-app/back-end/`:
  - O Dockerfile deve rodar uma imagem `node` utilizando a versão `14`;
    - Recomenda-se o uso da variante `-alpine`, pois ela é otimizada para desempenho;
    - Lembre-se de consultar o README do `todo-app` para validar os requisitos da aplicação.
  - Deve estar com a porta `3001` exposta;
  - Deve adicionar o arquivo `node_modules.tar.gz` a imagem;
  - Deve copiar todos os arquivos da pasta `back-end` para a imagem;
  - Ao iniciar a imagem deve rodar o comando `npm start`.
- Se ao *buildar* o Dockerfile o nome da imagem gerada é igual a `todobackend`.

</details>

### 10. Gere uma build a partir do Dockerfile do `front-end` do `todo-app` nomeando a imagem para `todofrontend`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command10.dc`.

#### Dicas

- O comando `ADD` do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.

#### O que será testado

  - Se existe um arquivo `Dockerfile` em `./docker/todo-app/front-end/`:
    - O `Dockerfile` pode rodar uma imagem `node` utilizando a versão `14`;
      - Recomenda-se o uso da variante `-alpine`, pois ela é otimizada para desempenho;
      - Lembre-se de consultar o README do `todo-app` para validar os requisitos da aplicação.
    - Deve estar com a porta `3000` exposta;
    - Deve adicionar o arquivo `node_modules.tar.gz` a imagem, de maneira que ele seja extraído dentro do `container`;
    - Deve copiar todos os arquivos da pasta `front-end` para a imagem;
    - Ao iniciar a imagem deve rodar o comando `npm start`;
  - Se ao *buildar* o `Dockerfile` o nome da imagem gerada é igual a `todofrontend`.

</details>

### 11. Gere uma build a partir do Dockerfile dos `testes` do `todo-app` nomeando a imagem para `todotests`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command11.dc`.

#### Dicas

- O comando `ADD` do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.

#### Observações técnicas

- A aplicação `todotests` só funciona corretamente se estiver dockerizada e dentro de uma rede docker configurada corretamente.

#### O que será testado

- Se existe um arquivo `Dockerfile` em `./docker/todo-app/tests/`:
  - O Dockerfile deve rodar a imagem `mjgargani/puppeteer:trybe1.0` para que os testes funcionem;
  - Deve adicionar o arquivo `node_modules.tar.gz` a imagem;
  - Deve copiar todos os arquivos da pasta `tests` para a imagem;
  - Ao iniciar a imagem deve rodar o comando `npm test`;
- Se ao *buildar* o Dockerfile o nome da imagem gerada é igual a `todotests`.

</details>

# Requisito bônus do projeto

## Docker-compose

### 12. Suba uma orquestração em segundo plano com o docker-compose de forma que `backend`, `frontend` e `tests` consigam se comunicar

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command12.dc`. Este comando pressupõe a existência do arquivo `./docker/docker-compose.yml`.

O `docker-compose` deve rodar na versão 3 ou superior.

#### Dicas

- Use as imagens já **"buildadas"** que foram executadas nos requisitos 9, 10 e 11 para a criação do compose;
- Consulte a documentação em `./docker/todo-app/README.md`;
- É possível adicionar e extrair arquivos `.tar.gz` no `Dockerfile` com apenas um comando.

#### O que será testado

##### tests

- O container de `todotests` deve ter como dependencia os containers `frontend` e `backend`;
- O nome do _service_ deverá ser `todotests`;
- Deve ter uma variável de ambiente `FRONT_HOST` que recebe como valor o nome do container do `frontend`
  - Lembrando que, dentro de uma rede docker, o host de um container é indentificado pelo seu nome.

##### front-end

- O container de `todofrontend` deve rodar na porta `3000`;
- O nome do _service_ deverá ser `todofront`;
- Deve ter como dependencia o container `backend`;
- Deve ter uma variável de ambiente `REACT_APP_API_HOST` que recebe como valor o nome do container do `backend`.
  - Lembrando que, dentro de uma rede docker, o host de um container é indentificado pelo seu nome.

##### back-end

- O container de `todobackend` deve rodar na porta `3001`;
- O nome do _service_ deverá ser `todoback`;

</details>
