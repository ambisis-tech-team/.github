# Ambisis Tech Team

**Ambisis tech bible**

Padrões de programação de cada projeto. Seguimos esses padrões para garantir um código de qualidade e fácil compreensão, além de evitar/adiar a necessidade de reescrever código.

**Regras:**

- Todo código deve ser formatado com um formatador definido para seu projeto (habilite o format on save do VSCODE).
- Nome de função e variável sempre em Camelcase com primeira letra minúscula. Exemplo: **convertDateBrToISO()**
- Nome de classes em Camelcase com primeira letra maiúscula. Exemplo: RaceCar
- Nome de arquivos e pastas sempre em letras minúsculas separado por underlines. Exemplo: my_folder/my_file.js (Exceto quando o padrão do framework for diferente, exemplo: **ZendFramework2**).
- Nome de constantes globais (apenas as constantes de arquivos de configuração .json ou .env) sempre em letras maiúsculas e separado por underlines. Exemplo: **APP_PORT**.
- Se tiver uma dúvida, problema difícil de resolver ou algum impedimento, compartilhe com o time.
- Todo arquivo de constantes globais (geralmente **configs.json** ou **.env**) não deve ser versionado pelo git (inclua esses arquivos no **.gitignore**). Além disso, sempre inclua um arquivo de sample que contenha um exemplo do formato esperado desses arquivos (**configs-sample.json**, **.env-sample**). Sempre que adicionar uma nova constante, inclua ela nesses arquivos **sample.**
- Todo novo repositório deve conter apenas letras minúsculas separado por underlines. Começando com “ambisis_”.

**Sugestões:**

- Evite comentários desnecessários, foque em nomes de variáveis e funções que expliquem o que fazem e para que servem, deixe para explicar no arquivo de documentação.
- Dê preferência para nomes em inglês para arquivos, variáveis, funções, constantes globais, etc.
- Lembre de documentar em um arquivo README.md as informações que podem ser úteis para outras pessoas interagindo com o repositório. Porém, seja sucinto e direto ao ponto, evite gastar muito tempo documentando.

**Prototipação / Diagramas:**

- Sempre que precisarmos criar um **recurso novo**, uma **feature com grandes impactos / esforços**, uma **tela nova** do zero, sempre fazer uma **prototipação** e/ou **diagrama de casos de usos**, utilizando respectivamente o [whimsical](https://whimsical.com/) e [draw.io](https://draw.io/).

**Especificações dos projetos:**

**Web:**

- Formatadores: php intelephense (.php e .phtml) / prettier (.js, .css)

**Services**

- Formatadores: prettier e ESLINT
- Sempre resolver os erros do ESLINT e evitar os warnings.
- Templates: [ambisis_service_template](https://docs.google.com/document/d/17MkoUkJxo4OKi4VcfjfhLWcVneocbjRZXxBe5lGLGz8/edit?usp=sharing)
- Documentação:
    - Incluir as rotas com breve descrição dos parâmetros necessários.
    - Incluir a porta
- Instalar dependências necessárias apenas para compilar o TS ou para testar em npm i [package] --save-dev
- Todo serviço deve ter pelo menos uma public-key ou private-key que deve ser enviada no header:
    - private-key contém 128 caracteres, é secreta e não deve ser exposta, apenas usada para comunicação interna entre os serviços.
    - public-key contém 16 caracteres, é pública, apenas serviços com intenção de serem acessados diretamente por uma aplicação front-end devem conter uma public-key.
    - Alguns serviços podem possuir tanto uma public-key, quanto uma private-key, de forma que possa ser acessada tanto por uma aplicação front-end quanto um por um serviço interno (porém o acesso por um serviço interno contém mais privilégios).
- Sempre que ocorrer um erro imprevisto, capturado por um try catch, escrever o erro no console, com “console.log(error)”

**Mobile**

- Formatadores: flutter

**AO CRIAR UMA TABELA NOVA NO BANCO DE DADOS, SEMPRE CRIAR A TRIGGER AFTER DELETE PARA INSERIR NA TABELA LOG_DELETE**
