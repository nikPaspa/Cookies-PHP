# CRUD de Cookies em PHP
Este repositório contém um pequeno exemplo de como criar, ler, alterar e deletar cookies utilizando PHP. A aplicação se baseia em um único script chamado cookies.php que manipula o cookie nome de acordo com o parâmetro req enviado via GET.

## Pré-requisitos
* **Servidor web com suporte a PHP (por exemplo, XAMPP, WampServer ou o servidor embutido do PHP).**
* **PHP 5.4+ (ou superior).**
## Como executar
**Coloque o arquivo cookies.php em seu servidor web.**

Pode ser no diretório padrão de seu servidor local (por exemplo, htdocs no XAMPP ou www no WampServer).

**Inicie o servidor (se ainda não estiver rodando).**

* **Se estiver usando o XAMPP, basta abrir o painel de controle e iniciar o Apache.**
* **Se quiser usar o servidor embutido do PHP, rode no terminal, dentro do diretório onde está o cookies.php:**
```
php -S localhost:8000
```
*Em seguida, acesse http://localhost:8000/cookies.php (ou a porta do seu servidor, caso seja diferente).*

**Use o parâmetro req para executar as ações:**

* **Criar: http://localhost/cookies.php?req=1**
* **Ler: http://localhost/cookies.php?req=2**
* **Alterar: http://localhost/cookies.php?req=3**
* **Deletar: http://localhost/cookies.php?req=4**

*Nos exemplos acima, http://localhost ou http://localhost:8000 pode variar conforme o servidor configurado e a porta em uso.*

## Descrição das Funções
* **Criar: Define o cookie nome com valor "Nikolas" e expiração de 100 segundos.**
* **Ler: Lê e exibe o valor do cookie nome.**
* **Alterar: Muda o valor do cookie nome para "Angelica".** *Sem tempo de expiração definido, ele será um session cookie (somente dura enquanto o navegador estiver aberto).*
* **Deletar: Define o cookie nome para expirar em time() - 1, ou seja, um momento no passado, invalidando-o.**
## Observações Importantes
* **Cabeçalhos e echo:** Em PHP, recomenda-se definir cookies antes de enviar qualquer saída ao navegador. Neste exemplo, algumas strings como "Criar", "Ler" etc. são exibidas antes de setcookie(). Dependendo da configuração do servidor ou do output buffering, isso pode funcionar ou causar erros. Se tiver problemas, mova as chamadas setcookie() para antes do echo.
* **Validade do Cookie:** Você pode modificar o tempo de expiração (terceiro parâmetro de setcookie) conforme sua necessidade.
* **Segurança:** Para casos de uso mais robustos, considere parâmetros adicionais de segurança em setcookie(), como secure, httponly, samesite, entre outros.

### Exemplo de uso:
Acesse no navegador:

* **Criar:** http://localhost/cookies.php?req=1

*Output esperado: Criar + Cookie criado.*

* **Ler:** http://localhost/cookies.php?req=2

*Output esperado: O valor do cookie, por padrão Nikolas.*

* **Alterar:** http://localhost/cookies.php?req=3

*Output esperado: Alterar + Cookie alterado para Angelica.*
* **Deletar:** http://localhost/cookies.php?req=4

*Output esperado: Deletar + Cookie apagado.*
