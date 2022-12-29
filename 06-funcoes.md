# Funções

As funções são um elemento importante do clean code, pois ajudam a dividir o código em pedaços menores e mais gerenciáveis. As funções permitem que você escreva código que pode ser reutilizado em vários lugares do seu programa, o que pode tornar o processo de desenvolvimento de software mais eficiente.

Aqui estão algumas dicas para escrever funções no conceito de clean code:

- Escreva funções pequenas e focadas: Evite escrever funções muito grandes que tentem fazer muitas coisas ao mesmo tempo. Em vez disso, tente dividir o código em funções menores e mais focadas que realizem uma tarefa específica. Isso torna o código mais fácil de ler e entender.
- Dê nomes significativos às funções: Dê nomes significativos às funções para que seja fácil entender o que elas estão fazendo. Por exemplo, em vez de chamar uma função de "f" ou "do_something", um nome mais significativo seria algo como "calcular_imposto" ou "obter_dados_do_cliente".
- Documente as funções: Documente as funções de maneira clara e concisa para explicar o que elas fazem e como elas devem ser usadas. Isso pode ajudar outras pessoas a entender o código e a reutilizar as funções de maneira apropriada.
- Teste as funções: É importante testar as funções para garantir que elas estejam funcionando corretamente e produzindo os resultados esperados.
- Mantenha as funções curtas e simples: Evite adicionar recursos desnecessários ou complicar as funções com soluções complexas. O código deve ser fácil de ler e entender.

Em resumo, escrever funções no conceito de clean code envolve criar funções pequenas e focadas, dar nomes significativos às funções, documentá-las, testá-las e mantê-las curtas e simples. Isso pode ajudar a tornar o código mais fácil de ler, entender e modificar, e pode aumentar a eficiência do processo de desenvolvimento de software.

# O que é uma função não coesa

Uma função sem coesão é aquela que faz muitas coisas diferentes ou tem várias responsabilidades. Isso pode ser um problema porque a função fica grande e difícil de entender e manter. Além disso, se uma função tem muitas responsabilidades, é mais provável que ela acabe sendo modificada por várias razões diferentes, o que pode levar a um código instável e difícil de manter.

O princípio da coesão sugere que uma função deve ter uma única responsabilidade e todos os seus códigos devem estar relacionados a essa responsabilidade. Isso torna a função mais fácil de entender e mais fácil de manter.

# Exemplo de função não coesa

```
function processData($data) {
  // código para validar os dados
  $errors = validateData($data);
  if ($errors) {
    return $errors;
  }

  // código para processar os dados
  $result = processData($data);

  // código para enviar os dados para o banco de dados
  saveDataToDatabase($result);

  // código para enviar um email com o resultado
  sendEmail($result);

  return $result;
}
```

# Porque não é coesa?

Essa função tem várias responsabilidades diferentes: ela valida os dados, processa os dados, salva os dados no banco de dados e envia um email. Isso pode ser um problema porque a função fica grande e difícil de entender e manter. Além disso, se uma função tem muitas responsabilidades, é mais provável que ela acabe sendo modificada por várias razões diferentes, o que pode levar a um código instável e difícil de manter.

Para tornar essa função mais coesa, você pode dividi-la em várias funções menores, cada uma com uma responsabilidade única. Isso ajuda a manter o código limpo e organizado, o que torna mais fácil de ler e entender.

# Trazendo coesão a função
Aqui está uma sugestão de como refatorar a função para torná-la mais coesa:

```
function validateData($data) {
  // código para validar os dados
  return $errors;
}

function processData($data) {
  // código para processar os dados
  return $result;
}

function saveDataToDatabase($result) {
  // código para enviar os dados para o banco de dados
}

function sendEmail($result) {
  // código para enviar um email com o resultado
}

function processAndSaveData($data) {
  $errors = validateData($data);
  if ($errors) {
    return $errors;
  }

  $result = processData($data);
  saveDataToDatabase($result);
  sendEmail($result);

  return $result;
}
```

# O que mudou?

Agora, cada função tem uma única responsabilidade e todos os seus códigos estão relacionados a essa responsabilidade. Isso torna a função mais fácil de entender e mais fácil de manter. Além disso, se uma função tem uma única responsabilidade, é menos provável que ela seja modificada por várias razões diferentes, o que ajuda a manter o código estável.