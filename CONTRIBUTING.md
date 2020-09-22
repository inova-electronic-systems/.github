# CONTRIBUINDO

## RECURSOS

Se você deseja contribuir para este projeto, certifique-se de
ler os seguintes recursos:

- [Coding Standards](https://github.com/inova-electronic-systems/coding-standard)
- [Code of Conduct](CODE_OF_CONDUCT.md)

## EXECUTANDO TESTES

Para executar testes:

- Clone o repositório. Clique no botão "Clonar ou baixar" no repositório
   para encontrar o URL e as instruções sobre clonagem.
- Instale dependências por meio do composer:

  ```console
  $ composer install
  ```

 Se você não tiver o `composer` instalado, faça o download em
  https://getcomposer.org/download/

- Execute os testes usando o comando "test" fornecido no `composer.json`:

  ```console
  $ composer test
  ```

Você pode ativar os testes condicionais com o arquivo `phpunit.xml`.
Para fazer isso:

- Copie o arquivo `phpunit.xml.dist` para` phpunit.xml`
- Edite o arquivo `phpunit.xml` para habilitar qualquer funcionalidade específica que você
   deseja testar, bem como fornecer valores de teste para utilizar.

## Execução de verificações Coding Standards (CS)

Primeiro, certifique-se de que instalou dependências por meio do composer, de acordo com o anterior
seção sobre a execução de testes.

Para executar cs-check:

```console
$ composer cs-check
```

Para tentar corrigir problemas comuns de CS automaticamente:

```console
$ composer cs-fix
```

O comando acima corrige qualquer problema de CS, execute novamente os testes para garantir
eles passam, e certifique-se de adicionar e confirmar as alterações após a verificação.

## Fluxo de trabalho recomendado para contribuições nesta organização

Seu primeiro passo é estabelecer um repositório público a partir do qual possamos
puxar seu trabalho para o repositório principal. Recomendamos usar
[GitHub] (https://github.com), pois é onde o componente já está hospedado.

1. Configure uma [conta GitHub] (https://github.com/join), se ainda não o fez
2. Bifurque o repositório usando o botão "fork" no canto superior direito do
   página inicial do repositório.
3. Clone o repositório do fork para seu ambiente localmente. Use o botão "Clonar ou baixar"
   acima da lista de códigos nas páginas de destino do repositório para obter a URL e
   instruções.
4. Navegue até o diretório onde você clonou o repositório.
5. Faça as alterações e rode o teste.
6. Sempre mantenha o codigo saudável.
7. Envie para o repositorio o seu fork criando um pull request.

### Manter-se atualizado

Periodicamente, você deve atualizar seu fork ou repositório pessoal para
corresponder ao repositório canônico. Supondo que você tenha configurado seu repositório local
pelas instruções acima, você pode fazer o seguinte:


```console
$ git checkout master
$ git fetch origin
$ git rebase origin/master
# OPCIONALMENTE, para manter seu controle remoto atualizado
$ git push {username} master:master
```

Se você está rastreando outros branchs - por exemplo, o branch "develop", onde
ocorre o desenvolvimento de novos recursos - você vai querer fazer as mesmas operações para esse
ramo; simplesmente substitua "develop" por "master".

Trabalhando em um patch

Recomendamos que você faça cada novo recurso ou correção de bug em um novo branch. Isso simplifica
a tarefa de revisão de código, bem como a tarefa de mesclar suas alterações no
repositório canônico.

Um fluxo de trabalho típico consistirá no seguinte:

1. Crie um novo branch local baseado em seu branch master ou de desenvolvimento.
2. Mude para sua nova branch local. (Esta etapa pode ser combinada com o
    etapa anterior com o uso de `git checkout -b`.)
3. Faça algum trabalho, comprometa-se, repita conforme necessário.
4. Envie o branch local para seu repositório remoto.
5. Envie uma solicitação de pull.

A mecânica desse processo é, na verdade, bastante trivial.

### Política de correção óbvia

Pequenas contribuições, como correção de erros ortográficos, onde o conteúdo é pequeno
o suficiente para não ser considerado propriedade intelectual, pode ser submetido sem
assinar a contribuição para o repositorio central.

Como regra geral, as mudanças são correções óbvias se não introduzirem nenhum novo
funcionalidade ou pensamento criativo. Assumindo que a mudança não afeta
funcionalidade, alguns exemplos comuns de correção óbvia incluem o seguinte:

- Correções de ortografia/gramática.
- Correção de digitação, espaço em branco e alterações de formatação.
- Limpe o comentário.
- Correções de bugs que alteram valores de retorno padrão ou códigos de erro armazenados em
   constantes.
- Adicionar ou alterar mensagens de exceção.
- Alterações em arquivos de 'metadados' como `.gitignore`,` composer.json`, etc.
- Mover arquivos de origem de um diretório para outro.

Sempre que você invocar a regra de "obvious fix", diga-o em sua mensagem de confirmação:

```console
$ git checkout -a -m "obvious fix"
```
