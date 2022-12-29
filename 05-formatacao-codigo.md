# Formatação de código fonte

A formatação do código fonte é um aspecto importante da filosofia do clean code, pois ajuda a tornar o código mais fácil de ler e entender. 

A formatação inclui coisas como o uso de espaços em branco, tabulações e quebras de linha para organizar o código de maneira lógica e clara.

Existem muitas maneiras de formatar o código fonte, e muitas delas dependem da linguagem de programação que está sendo usado e das convenções de estilo de código adotadas pela equipe de desenvolvimento. 

No entanto, existem algumas dicas gerais que podem ajudar a manter o clean code e bem formatado:

- Mantenha as linhas de código curtas: Evite escrever linhas de código muito longas, pois isso pode tornar o código mais difícil de ler e entender. Em vez disso, tente quebrar o código em linhas mais curtas e mais fáceis de ler.
- Use espaços em branco para separar elementos do código: Use espaços em branco para separar elementos do código, como variáveis, funções e operadores. Isso ajuda a tornar o código mais fácil de ler e entender.
- Use tabulações ou espaços em branco para indentar o código: Indentar o código (colocar espaços em branco ou tabulações no início de uma linha) ajuda a destacar diferentes níveis de blocos de código e a tornar o código mais fácil de ler.
- Use comentários para explicar partes complexas do código: Se houver partes do código que possam ser difíceis de entender, adicione comentários para explicar o que está acontecendo e por que o código está sendo escrito de determinada maneira.

Em resumo, a formatação do código fonte é importante no conceito de clean code porque ajuda a tornar o código mais fácil de ler e entender. Algumas dicas gerais incluem manter as linhas de código curtas, usar espaços em branco para separar elementos do código, indentar o código e usar comentários para explicar partes complexas do código.


# Exemplo de uma formatação não coesa

```
<?php

class MyClass{

public function doSomething(){
    $result = executeOperation();
    if (!$result) {
    throw new Exception('Erro ao realizar a operação');
    }

return $result;
}

public function doSomethingElse(){
    $result = executeOtherOperation();
    if (!$result) {
    throw new Exception('Erro ao realizar a outra operação');
    }

    return $result;
}

public function handleError(Exception $e){
    logError($e->getMessage());
    sendEmailToAdmin('Erro no sistema', $e->getMessage());
    }
}

$myClass = new MyClass();

$result1 = $myClass->doSomething();
$result2 = $myClass->doSomethingElse();
$myClass->handleError($e);

?>
```

Essa formatação de código tem alguns problemas de coesão. Primeiro, a classe está fazendo muitas coisas diferentes: ela tem duas funções diferentes e uma função de tratamento de erros. Além disso, a formatação do código não é consistente: as chaves de abertura e fechamento estão em linhas diferentes em cada função e a indentação não é consistente. Isso pode deixar o código mais difícil de entender

# Trazendo coesão para a formatação
Aqui está um exemplo de formatação de código coesa em PHP:

```
<?php

class MyClass
{
    public function doSomething(): bool
    {
        $result = executeOperation();
        if (!$result) {
            throw new Exception('Erro ao realizar a operação');
        }

        return $result;
    }

    public function doSomethingElse(): bool
    {
        $result = executeOtherOperation();
        if (!$result) {
            throw new Exception('Erro ao realizar a outra operação');
        }

        return $result;
    }

    public function handleError(Exception $e): void
    {
        logError($e->getMessage());
        sendEmailToAdmin('Erro no sistema', $e->getMessage());
    }
}

$myClass = new MyClass();

try {
    $result1 = $myClass->doSomething();
    $result2 = $myClass->doSomethingElse();
} catch (Exception $e) {
    $myClass->handleError($e);
}

```

Essa formatação de código é mais coesa porque é consistente e facilita a leitura do código. As chaves de abertura e fechamento estão sempre na mesma linha e a indentação.