# Tratamento de erros

O tratamento de erros é um aspecto importante da filosofia do clean code, pois ajuda a garantir que o programa continue funcionando de maneira correta mesmo em situações inesperadas ou excepcionais.

Existem várias maneiras de tratar erros no código, e muitas delas dependem do idioma de programação que está sendo usado e das convenções de estilo de código adotadas pela equipe de desenvolvimento. No entanto, existem algumas dicas gerais que podem ajudar a tratar erros de maneira eficiente e limpa:

- Use try-catch para tratar erros: Muitas linguagens de programação oferecem uma estrutura de try-catch que permite tratar erros de maneira fácil e organizada. Com essa estrutura, você pode escrever código que pode gerar um erro em um bloco "try", e especificar o que deve ser feito em caso de um erro no bloco "catch". Isso permite que o programa continue funcionando mesmo em caso de erro.
- Trate erros específicos de maneira apropriada: Quando um erro ocorre, é importante tratá-lo de maneira apropriada e fazer o que for necessário para garantir que o programa continue funcionando de maneira consistente. Isso pode incluir coisas como encerrar o programa de maneira limpa, mostrar uma mensagem de erro ao usuário ou tentar recuperar o programa de alguma maneira.
- Evite tratar erros de forma genérica: Evite simplesmente ignorar erros ou tratá-los de maneira genérica sem considerar o contexto específico em que ocorreram. Isso pode levar a problemas futuros e tornar o código mais difícil de entender e manter.
- Documente os erros que você está tratando: Documente os erros que você está tratando e explique por que você está tomando determinadas ações para lidar com eles. Isso pode ajudar outras pessoas a entender o código e a manter o código de maneira mais eficiente no futuro.
- Use logs para rastrear erros: Use logs para rastrear erros e entender o que está acontecendo no programa. Isso pode ajudar a identificar problemas e solucioná-los mais rapidamente.
- Teste o código para identificar erros: É importante testar o código para identificar erros e garantir que o programa esteja funcionando corretamente. Isso pode ajudar a evitar problemas no futuro.

Em resumo, o tratamento de erros no clean code envolve usar estruturas como try-catch para tratar erros de maneira organizada,


# Exemplo não coeso
Aqui está um exemplo de tratamento de erro sem coesão em PHP:

```
<?php

try {
    $result = executeOperation();
    if (!$result) {
        throw new Exception('Erro ao realizar a operação');
    }
} catch (Exception $e) {
    // Trata o erro
    logError($e->getMessage());
    sendEmailToAdmin('Erro no sistema', $e->getMessage());
    showErrorMessageToUser('Ocorreu um erro inesperado. Por favor, tente novamente mais tarde.');
}

?>
```

Nesse exemplo, o tratamento de erro tem várias responsabilidades diferentes, como logar o erro, enviar um email para o administrador e mostrar uma mensagem de erro para o usuário. Isso pode deixar o código difícil de ler e difícil de manter, já que há várias coisas acontecendo no mesmo bloco de tratamento de erro. Além disso, se a lógica de tratamento de erro precisar ser alterada por algum motivo, pode ser difícil saber exatamente o que precisa ser modificado.

# Exemplo coeso
Aqui está uma sugestão de como refatorar o código para torná-lo mais coeso:

```
<?php

try {
    $result = executeOperation();
    if (!$result) {
        throw new Exception('Erro ao realizar a operação');
    }
} catch (Exception $e) {
    // Trata o erro
    $errorHandler = new ErrorHandler();
    $errorHandler->logError($e->getMessage());
    $errorHandler->sendEmailToAdmin('Erro no sistema', $e->getMessage());
    $errorHandler->showErrorMessageToUser('Ocorreu um erro inesperado. Por favor, tente novamente mais tarde.');
}

?>
```

Nesse exemplo, o tratamento de erro é mais coeso porque cada responsabilidade é delegada para um método específico da classe ErrorHandler. Isso ajuda a manter o código mais organizado e fácil de ler e facilita a manutenção do código, já que é mais fácil saber exatamente o que cada método está fazendo. Além disso, se a lógica de tratamento de erro precisar ser alterada por algum motivo, basta modificar o método relevante na classe ErrorHandler.