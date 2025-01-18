# Hello World IaC

Projeto de estudos provisionando uma ec2 utilizando o terraform e o localstack.

# Para executar o projeto:
- Inicialmente é necessário configure as credenciais do localstack, que simulam os tokens da AWS. Para isso adicione o seguinte texto no arquivo `.aws/credentials`:
  ```
  [localstack]
  aws_access_key_id = giropops
  aws_secret_access_key = strigus
  ```
  Essas são as mesmas credenciais configuradas no arquivo `main.tf` e servem para a comunicação com o localstack. Pode ser utilizado qualquer outro texto, desde que eles sejam igual no arquivo `credentials` e `main.tf`
  
- Inicie o localstack em um terminal:
  ```
  localstack start
  ```
- Em outro terminal, no diretório com os arquivos terraform, inicie o projeto:
  ```
  terraform init
  ```
- Em seguida, utilize o plan para verificar o que será provisionado com o código:
  ```
  terraform plan -out plan
  ```
  Obs: O argumento -out plan faz com que todo planejamento exibido no terminal seja salvo no arquivo `plan`. 
  A utilização desse argumento é uma boa prática, pois ao aplicar as configurações do terraform iremos utilizar o planejamento contido nesse arquivo, assim garantido que o planejamento que o provisionamento será identico ao planejamento.
- Por fim, provisione os recursos:
  ```
  terraform appply "plan"
  ```

# Pré requisitos:
  - Docker (https://docs.docker.com/engine/install/)
  - Terraform (https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
  - AWS CLI (https://docs.aws.amazon.com/pt_br/cli/latest/userguide/getting-started-install.html)
  - Localstack (https://docs.localstack.cloud/getting-started/installation/)

# Fontes usadas para o projeto:
  - LinuxTips (https://www.youtube.com/watch?v=0nU9yvqg2Rw)
  - Terraform (https://spacelift.io/blog/terraform-ec2-instance)
