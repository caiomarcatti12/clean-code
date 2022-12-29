# Refatoração Tempestiva

A refatoração tempestiva é o processo de fazer alterações no código para torná-lo mais limpo, mais eficiente e mais fácil de entender e manter, sem afetar o comportamento ou a funcionalidade do código. A refatoração tempestiva é uma prática importante no clean code, pois ajuda a garantir que o código continue sendo limpo e de alta qualidade mesmo quando ele está sendo alterado ou evoluído.

A refatoração tempestiva é diferente da refatoração radical, que envolve fazer grandes alterações no código que podem afetar o comportamento ou a funcionalidade do código. A refatoração radical pode ser útil em alguns casos, mas também pode ser arriscada e deve ser feita com cuidado para evitar introduzir falhas ou regressões no código.

Para fazer refatoração tempestiva de maneira eficiente, é importante seguir algumas dicas, como:

- Usar testes de unidade: Os testes de unidade ajudam a garantir que o código esteja funcionando corretamente antes e depois da refatoração, o que ajuda a evitar introduzir falhas ou regressões no código.
- Fazer mudanças pequenas e incrementalmente: Ao invés de fazer grandes alterações de uma vez, é melhor fazer mudanças pequenas e incrementalmente, de modo que seja mais fácil identificar e corrigir qualquer problema que possa surgir.
- Documentar as alterações: Documente as alterações que está fazendo no código, especialmente se elas forem mais complexas ou significativas. Isso ajuda a tornar o código mais fácil de entender e manter.

# Como realizar uma refatoração
Identifique o código que precisa ser refatorado. Isso pode ser um trecho de código que está difícil de ler ou entender, ou que possui várias responsabilidades diferentes.

- Crie um branch separado para realizar a refatoração. Isso permitirá que você altere o código sem afetar o funcionamento atual do sistema.

- Faça as alterações necessárias para refatorar o código. Isso pode incluir reorganizar o código, remover redundâncias ou dividir o código em funções ou classes mais coesas.

- Teste o código refatorado para garantir que ele esteja funcionando corretamente.
- Publique as alterações no branch de refatoração.
- Crie um pull request para mesclar o branch de refatoração com o branch principal.
- Revise o código refatorado com outros desenvolvedores para garantir que ele esteja de acordo com as boas práticas de codificação.
- Mescle o branch de refatoração com o branch principal.
- Exclua o branch de refatoração.

# Pequeno exemplo (imagine que o código foi refatorado depois de pronto)
Aqui está um exemplo de como realizar uma refatoração tempestiva em PHP:

```
// Código antigo
function getUser($id)
{
    $query = "SELECT * FROM users WHERE id = $id";
    $result = mysqli_query($conn, $query);
    return mysqli_fetch_assoc($result);
}

```
O código acima foi escrito, testado, esta funcionando e atendeu a necessidade solicitada.

Agora vamos refatorar...
 
```
// Código refatorado
class UserRepository
{
    private $conn;

    public function __construct(mysqli $conn)
    {
        $this->conn = $conn;
    }

    public function getById(int $id): array
    {
        $query = "SELECT * FROM users WHERE id = $id";
        $result = mysqli_query($this->conn, $query);
        return mysqli_fetch_assoc($result);
    }
}

$userRepository = new UserRepository($conn);
$user = $userRepository->getById(123);
```

No código antigo, a função getUser é responsável por fazer a consulta ao banco de dados e retornar os dados do usuário. No entanto, essa função tem várias responsabilidades diferentes, o que pode deixar o código difícil de ler e difícil de manter.

Para refatorar o código de maneira tempestiva, criamos uma classe UserRepository que é responsável por fazer a consulta ao banco de dados

