# Linguagem onipresente

Linguagem onipresente é uma prática de codificação em que todas as partes do código são escritas em uma única linguagem. Isso é considerado uma boa prática em clean code porque ajuda a manter o código limpo e organizado e facilita a leitura e a manutenção do código.

Por exemplo, se você estiver escrevendo código PHP, é uma boa prática escrever todo o código em PHP e não misturar outras linguagens, como HTML ou JavaScript. Isso ajuda a manter o código coeso e focado em sua responsabilidade principal.

Usar linguagem onipresente também pode ajudar a evitar problemas de compatibilidade ou erros de sintaxe ao misturar diferentes linguagens de programação. Além disso, ao usar uma única linguagem, é mais fácil para os outros desenvolvedores entenderem o que o código está fazendo e como ele funciona.

# Exemplo

Aqui está um exemplo de linguagem onipresente em PHP:

```
<?php

// Código PHP
$user = getUserById(1);
echo "Olá, " . $user['name'];

// Mais código PHP
$posts = getRecentPosts();
foreach ($posts as $post) {
    echo "<h2>" . $post['title'] . "</h2>";
    echo "<p>" . $post['content'] . "</p>";
}

?>
```

Nesse exemplo, todo o código está escrito em PHP e não há mistura de outras linguagens, como HTML ou JavaScript. Isso ajuda a manter o código coeso e organizado e facilita a leitura e a manutenção do código.