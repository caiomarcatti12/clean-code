# Como escrever boas classes

As classes no clean code devem ser criadas de maneira clara, coesa e fácil de entender. Aqui estão algumas dicas para criar classes de maneira limpa:

- Tenha um propósito claro: As classes devem ter um propósito claro e devem fazer apenas uma coisa bem. Evite criar classes que sejam muito complexas ou que tenham muitas responsabilidades diferentes.
- Mantenha as classes pequenas: As classes devem ser pequenas e conter apenas o código necessário para cumprir seu propósito. Quanto menor a classe, mais fácil será entender e manter o código.
- Escolha nomes significativos: Os nomes das classes devem ser significativos e refletir o propósito da classe. Evite usar nomes genéricos ou confusos.
- Evite a dependência mútua: Evite criar classes que dependam umas das outras de maneira muito estreita. Isso pode tornar o código mais difícil de entender e manter.
- Faça as classes modulares: As classes devem ser modulares, ou seja, devem ser auto-suficientes e não depender de outras classes para funcionar corretamente. Isso ajuda a tornar o código mais fácil de entender e manter.

Em resumo, criar classes no clean code envolve ter um propósito claro, manter as classes pequenas, escolher nomes significativos, evitar a dependência mútua e fazer as classes modulares. Isso ajuda a garantir que as classes sejam coesas, fáceis de entender e fáceis de manter.

# O que é uma classe não coesa

Uma classe não coesa é aquela que tem muitas responsabilidades e faz muitas coisas diferentes. Isso pode ser um problema porque a classe fica grande e difícil de entender e manter. Além disso, se uma classe tem muitas responsabilidades, é mais provável que ela acabe sendo modificada por várias razões diferentes, o que pode levar a um código instável e difícil de manter.

O princípio da coesão sugere que uma classe deve ter uma única responsabilidade e todos os seus métodos devem estar relacionados a essa responsabilidade. Isso torna a classe mais fácil de entender e mais fácil de manter.

Para tornar uma classe mais coesa, você pode dividir a classe em várias classes menores, cada uma com uma responsabilidade única. Você também pode mover métodos que não estão relacionados à responsabilidade principal da classe para outras classes mais adequadas. Isso ajuda a manter o código limpo e organizado, o que torna mais fácil de ler e entender.

# Exemplo de classe não coesa

```
class User {
  private $name;
  private $email;
  private $password;

  public function __construct($name, $email, $password) {
    $this->name = $name;
    $this->email = $email;
    $this->password = $password;
  }

  public function getName() {
    return $this->name;
  }

  public function setName($name) {
    $this->name = $name;
  }

  public function getEmail() {
    return $this->email;
  }

  public function setEmail($email) {
    $this->email = $email;
  }

  public function getPassword() {
    return $this->password;
  }

  public function setPassword($password) {
    $this->password = $password;
  }

  public function sendEmail($subject, $message) {
    // código para enviar email
  }

  public function hashPassword() {
    // código para criptografar a senha
  }

  public function validatePassword($password) {
    // código para validar a senha
  }
}
```
# Porque não é coesa?

Essa classe tem várias responsabilidades diferentes: ela armazena informações do usuário, envia emails, criptografa senhas e valida senhas. Isso pode ser um problema porque a classe fica grande e difícil de entender e manter. Além disso, se uma classe tem muitas responsabilidades, é mais provável que ela acabe sendo modificada por várias razões diferentes, o que pode levar a um código instável e difícil de manter.

Para tornar essa classe mais coesa, você pode dividi-la em várias classes menores, cada uma com uma responsabilidade única. Por exemplo, você pode criar uma classe separada para enviar emails e outra classe para criptografar e validar senhas. Isso ajuda a manter o código limpo e organizado, o que torna mais fácil de ler e entender.


# Trazendo coesão a classe

```
class User {
  private $name;
  private $email;
  private $password;

  public function __construct($name, $email, $password) {
    $this->name = $name;
    $this->email = $email;
    $this->password = $password;
  }

  public function getName() {
    return $this->name;
  }

  public function setName($name) {
    $this->name = $name;
  }

  public function getEmail() {
    return $this->email;
  }

  public function setEmail($email) {
    $this->email = $email;
  }

  public function getPassword() {
    return $this->password;
  }

  public function setPassword($password) {
    $this->password = $password;
  }
}

class EmailSender {
  public function sendEmail($to, $subject, $message) {
    // código para enviar email
  }
}

class PasswordHasher {
  public function hashPassword($password) {
    // código para criptografar a senha
  }

  public function validatePassword($password, $hashedPassword) {
    // código para validar a senha
  }
}
```


# O que mudou?

Agora, cada classe tem uma única responsabilidade e todos os seus métodos estão relacionados a essa responsabilidade. Isso torna a classe mais fácil de entender e mais fácil de manter. Além disso, se uma classe tem uma única responsabilidade, é menos provável que ela seja modificada por várias razões diferentes, o que ajuda a manter o código estável.


# Exemplos de nome de classes não coesas 
Aqui estão alguns exemplos de nomes de classes que podem ser considerados não coesos:

- "Utility": esse nome de classe é amplo e não dá muitas pistas sobre o que a classe faz ou qual é a sua responsabilidade. Ela pode ter métodos para fazer qualquer tipo de tarefa  útil.
- "Helper": esse nome de classe é ainda mais amplo e genérico do que o anterior. Ele não dá nenhuma pista sobre o que a classe faz ou qual é a sua responsabilidade.
- "Manager": esse nome de classe é amplo e genérico e não dá nenhuma pista sobre o que a classe faz ou qual é a sua responsabilidade. Ela pode ser usada para gerenciar qualquer coisa.

Para tornar os nomes de classes mais coesos, é importante escolher nomes que sejam específicos e descrevam exatamente o que a classe faz ou qual é a sua responsabilidade. Isso ajuda a manter o código limpo e organizado e facilita a depuração e manutenção do código.


# Exemplos de nome de classes coesas 

Aqui estão alguns exemplos de nomes de classes coesos:

- "DataValidator": esse nome de classe é específico e descreve exatamente o que a classe faz. Ela tem uma única responsabilidade e todos os seus métodos estão relacionados a essa responsabilidade.
- "EmailSender": esse nome de classe é específico e descreve exatamente o que a classe faz. Ela tem uma única responsabilidade e todos os seus métodos estão relacionados a essa responsabilidade.
- "PasswordHasher": esse nome de classe é específico e descreve exatamente o que a classe faz. Ela tem uma única responsabilidade e todos os seus métodos estão relacionados a essa responsabilidade.
- "DatabaseConnection": esse nome de classe é específico e descreve exatamente o que a classe faz. Ela tem uma única responsabilidade e todos os seus métodos estão relacionados a essa responsabilidade.

Nomes de classe coesos são específicos e descrevem exatamente o que a classe faz ou qual é a sua responsabilidade, o que ajuda a manter o código limpo e organizado. Além disso, se uma classe tem uma única responsabilidade, é menos provável que ela seja modificada por várias razões diferentes, o que ajuda a manter o código estável.
