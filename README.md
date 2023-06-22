# Cadastro de carro

**RF**

- Deve ser possível cadastrar um novo carro.

**RN**

- Não deve ser possível cadastrar um carro com uma placa já existente.
- O carro deve ser cadastrado, por padrão, com disponibilidade.
- O usuário responsável pelo cadastro deve ser um usuário administrador.

# Listagem de carros

**RF**

- Deve ser possível listar todos os carros disponíveis
- Deve ser possível listar todos os carros disponíveis pelo - nome da categoria
- Deve ser possível listar todos os carros disponíveis pelo - nome da marca
- Deve ser possível listar todos os carros disponíveis pelo - nome do carro

**RN**

- O usuário não precisar estar logado no sistema.

# Cadastro de Especificação no carro

**RF**

- Deve ser possível cadastrar uma especificação para um carro

**RN**

- Não deve ser possível cadastrar uma especificação para um - carro não cadastrado.
- Não deve ser possível cadastrar uma especificação já - existente para o mesmo carro.
- O usuário responsável pelo cadastro deve ser um usuário - administrador.

# Cadastro de imagens do carro

**RF**

- Deve ser possível cadastrar a imagem do carro

**RNF**

- Utilizar o multer para upload dos arquivos

**RN**

- O usuário deve poder cadastrar mais de uma imagem para o - mesmo carro
- O usuário responsável pelo cadastro deve ser um usuário - administrador.

# Alugel de carro

**RF**

- Deve ser possível cadastrar um aluguel

**RN**

- O aluguel deve ter duração mínima de 24 horas.
- Não deve ser possível cadastrar um novo aluguel caso já - exista um aberto para o mesmo usuário
- Não deve ser possível cadastrar um novo aluguel caso já - exista um aberto para o mesmo carro
- O usuário deve estar logado na aplicação
- Ao realizar um aluguel, o status do carro deverá ser - alterado para indisponível

# Devolução de carro

**RF**

- Deve ser possível realizar a devolução de um carro

**RN**

- Se o carro for devolvido com menos de 24 horas, deverá - ser cobrado diária completa.
- Ao realizar a devolução, o carro deverá ser liberado para - outro aluguel.
- Ao realizar a devolução, o usuário deverá ser liberado - para outro aluguel.
- Ao realizar a devolução, deverá ser calculado o total do - aluguel.
- Caso o horário de devolução seja superior ao horário - previsto de entrega, deverá ser cobrado multa - proporcional aos dias de atraso.
- Caso haja multa, deverá ser somado ao total do aluguel.
- O usuário deve estar logado na aplicação

# Listagem de Alugueis para usuário

**RF**

- Deve ser possível realizar a busca de todos os alugueis para o usuário

**RN**

- O usuário deve estar logado na aplicação

# Recuperar Senha

**RF**

- Deve ser possível o usuário recuperar a senha informando o e-mail
- O usuário deve receber um e-mail com o passo a passo para a recuperação da senha
- O usuário deve conseguir inserir uma nova senha

**RN**

- O usuário precisa informar uma nova senha
- O link enviado para a recuperação deve expirar em 3 horas

{
 "email": "<admin@rentx.com.br>",
 "password": "admin"
}

// para configurar o putty

- o ambiente da AWS gera um arquivo ".pem" que possui o ssh de autenticação
- essa chave so funciona em linux, então para conectar com o putty vai ser preciso usar o puttygen para converter para um ".ppk".
- feito isso basta executar o putty.exe
  - na aba Connection > Auth > Credentials localizar o arquivo ".ppk" gerado via puttygen
  - na aba Connection > Data setar o user como "ubuntu" que é o padrão gerado pela intancia EC2 (pode ser modificado depois para adicionar um novo usuario)
  - na aba Session basta diginar o DNS Publico fornecido pela propia AWS ao gerar a instancia e então conectar.
- Para adicionar um novo user basta utilizar "sudo adduser <nome do usuário>" e então fornecer a senha (lembre-se dela)
- defina as permissões de admin para esse novo user com o comando "sudo usermod -aG sudo app", sendo "app" o nome do usuario exemplo que criamos.
- para acessar o usuario basta dar o comando "sudo su - app", que ele acessará o terminal como o novo usuario criado.
- para salvar a chave ssh criada com o git bash, sera necessario criar um diretorio com "mkdir .ssh", fornecer as permissões para somente o proprietario do dir. poder alterar com "chmod 700 .ssh/"
- acesse o diretorio com "cd .ssh/" e crie um arquivo com o ocmando "touch authorized_keys".
- para editar esse arquivo criado digite o comando "vi authorized_keys" que ele abrira como um editor
- adicione nesse arquivo a chave publica da sua maquina local (gerado via git bash ou puttygen)
  - ela começa com "ssh-rsa"
  - para editar o arquivo aperte a letra "i" do teclado, onde vai dar um aviso que esta em modo "INSERT"
  - cole a chave da maquina local
  - para salvar basta dar ctrl+c e digitar ":wq!"
  - para verificar se deuc erto de um "cat authorized_keys"
  
// para se conectar a instancia EC2 da azure, abra o terminal como adm:

- digite "ssh <user criado atraves da conexao via putty>@<ip da intancia do EC2 na AWS>"
  - EX: "ssh app@15.228.52.245"
- caso ele de algum erro de permissão, tentar rodar o comando para alterar a permissão no arquivo com "chmod 600 authorized_keys".
- a partir desse ponto basta dar o "sudo apt  update" para atualizar os pacotes necessarios e, caso queira baixar outros pacotes como NODE, YARN, DOCKER, DOCKER COMPOSE, basta pesquisar a documnetação dos mesmos nas respectivas paginas de download e utilizar os comandos para o linux.
-
