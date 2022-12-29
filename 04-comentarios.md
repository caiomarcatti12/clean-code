# Podemos utilizar comentários?

Sim, os comentários podem ser um elemento importante do clean code, desde que sejam usados de maneira apropriada. Os comentários são linhas de código que são ignoradas pelo interpretador ou compilador, mas que são incluídas no código para fornecer explicações ou contexto adicionais. Eles podem ser muito úteis para ajudar outras pessoas a entender o que o código está fazendo e por que ele está sendo escrito de determinada maneira.

No entanto, é importante usar comentários de maneira moderada e evitar sobrecarregar o código com comentários desnecessários. 

Comentários devem ser usados para explicar coisas que não são óbvias no código e que podem ajudar outras pessoas a entender o que está acontecendo. Eles não devem ser usados para explicar coisas que já estão claras no código ou para simplesmente preencher espaço.

Ao usar comentários, é importante seguir algumas regras básicas:

- Mantenha os comentários curtos e diretos: Os comentários devem ser concisos e diretos, sem enrolação.
- Faça comentários relevantes: Os comentários devem ser relevantes para o código e fornecer contexto ou explicações úteis.
- Mantenha os comentários atualizados: Se você fizer alterações no código, não se esqueça de atualizar os comentários para que eles continuem sendo relevantes e precisos.
- Use uma linguagem clara e concisa: Os comentários devem ser fáceis de ler e entender, sem jargão ou linguagem técnica desnecessária.

Em resumo, os comentários podem ser uma ferramenta útil no conceito de clean code, desde que sejam usados de maneira moderada e apropriada para fornecer contexto e explicações úteis sobre o código. Eles não devem ser usados para preencher espaço ou explicar coisas que já são óbvias no código.

# Exemplo de comentário não coeso
Aqui está um exemplo de comentário não coeso em PHP:

```
<?php

// Esse método calcula o valor total da compra. Ele também verifica se o usuário tem saldo suficiente na conta
// para pagar a compra e lança uma exceção se não houver saldo suficiente. Além disso, ele envia um email para o
// usuário com o resumo da compra.
public function calculateTotal(array $items, float $balance): float
{
    $total = 0;
    foreach ($items as $item) {
        $total += $item['price'];
    }
    if ($total > $balance) {
        throw new Exception('Saldo insuficiente para realizar a compra');
    }
    sendEmailToUser('Resumo da compra', 'Obrigado por sua compra! Aqui está o resumo: ...');
    return $total;
}

?>
```

Esse comentário é considerado não coeso porque ele descreve várias responsabilidades diferentes da função, como calcular o valor total da compra, verificar o saldo do usuário e enviar um email para o usuário. Isso pode deixar o comentário confuso e difícil de entender. Além disso, se a função precisar ser modificada por algum motivo, o comentário pode ficar desatualizado e não mais

# Exemplo coeso
Aqui está um exemplo de comentário coeso em PHP:

```
<?php

// Calcula o valor total da compra
public function calculateTotal(array $items): float
{
    $total = 0;
    foreach ($items as $item) {
        $total += $item['price'];
    }
    return $total;
}

// Verifica se o usuário tem saldo suficiente na conta para pagar a compra e lança uma exceção se não houver saldo suficiente
public function checkBalance(float $total, float $balance): void
{
    if ($total > $balance) {
        throw new Exception('Saldo insuficiente para realizar a compra');
    }
}

// Envia um email para o usuário com o resumo da compra
public function sendEmail(array $items): void
{
    $message = 'Obrigado por sua compra! Aqui está o resumo: \n';
    foreach ($items as $item) {
        $message .= $item['name'] . ': ' . $item['price'] . '\n';
    }
    sendEmailToUser('Resumo da compra', $message);
}

?>
```

Nesse exemplo, cada função tem um único comentário que descreve exatamente o que a função faz. Isso ajuda a manter o código coeso e organizado e facilita a leitura e a manutenção do código. Além disso, se a função precisar ser modificada por algum motivo, o comentário ainda estará atualizado e relevante.