# Dataform-Jenkins-CLI

### Objetivo

Este projeto tem por objetivo a integração do [Jenkins] a ferramenta de ETL [Dataform]. Para fazer essa integração utilizamos uma imagem Docker do Jenkins e o [Dataform CLI].

Para ilustrar a integração com o Jenkins utilizamos um dataset de dados públicos do BigQuery o *Data to Insights*.

### Estrutura do Projeto

O projeto utiliza a estrutura gerada pelo template de projetos Dataform, o [cookiecutter-template].

``` shell
    ├──Dataform-Jenkins-CLI                 
        ├── definitions           
            ├── source              <- Fonte dos dados e parâmetros de configuração do BigQuery.
            ├── tests               <- Testes unitários
            ├── reports             <- Views e tabelas modeladas
        ├── includes 
            ├── constants.js        <- Arquivo de definição de constantes com JavaScript 
        ├── jenkins 
            ├──Jenkinsfile          <- Código de pipeline do Jenkins
        ├── dataform.json           <- Arquivo de configuração do Dataform
        ├── docker-compose.yml      <- Docker do Jenkins
        ├── environments.json       <- Configurações de branchs de desenvolvimento
    ├── README.md         
```

### Como utilizar esse repositório

* Faça o git clone do projeto

* Suba o Docker do Jenkins

```bash
    docker-compose up
```
    
### Configurando o Jenkins

* Abra seu browser no endereço *localhost:8083* .
* Siga o [tutorial] de setup da execução do Jenkins.

> **_NOTA:_** Estamos utilizando um Docker do Jenkins então possivelmente alguns plugins devem ser instalados.

* Para execução do pipeline certifique-se que o Docker possua o plugin do Node.js e do Github.

### Pipeline do Jenkins
![Captura de tela de 2021-04-27 10-09-38](https://user-images.githubusercontent.com/52939036/116247458-43f87000-a741-11eb-867a-3f1177ae6248.png)

[Jenkins]: https://www.jenkins.io/doc/
[Dataform]: https://docs.dataform.co/
[Dataform CLI]: https://docs.dataform.co/dataform-cli
[tutorial]: https://churrops.io/2017/04/22/jenkins-rodando-jenkins-como-container-utilizando-o-docker/
[cookiecutter-template]: https://github.com/oliveiraJessica/cookiecutter-dataform

