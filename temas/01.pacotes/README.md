## Pacotes

Um pacote em Go é uma coleção de arquivos de código-fonte que são organizados juntos para fornecer funcionalidades específicas. Todo arquivo Go pertence a um pacote e cada aplicativo Go começa no pacote main.

### Estrutura Básica

#### Declaração do Pacote

- Cada arquivo Go começa com uma declaração de pacote.

```
package main
```
#### Importação de Pacotes

- Para usar funções, tipos e outras funcionalidades de outro pacote, você deve importar o pacote.

```
import "fmt"
```
#### Função Principal

- O ponto de entrada de um aplicativo Go é a função main dentro do pacote main.

```
func main() {
    fmt.Println("Hello, World!")
}
```

### Pacote personalizado

#### Criação do Diretório do Pacote

Crie um novo diretório para o seu pacote.

```
mkdir mypackage
cd mypackage
```
#### Criação do Arquivo do Pacote
Dentro deste diretório, crie um arquivo Go. Por exemplo, mypackage.go.

```
// mypackage/mypackage.go
package mypackage

import "fmt" //está no código interno

// Função Exportada
func SayHello() {
    fmt.Println("Hello from mypackage!")
}
```
#### Usando o Pacote
Para usar o pacote mypackage, importe-o no arquivo onde você deseja utilizá-lo.

```
// main.go
package main

import (
    "mypackage"
)

func main() {
    mypackage.SayHello()
}
  
```

### Pacotes Executáveis 

Pacotes executáveis são aqueles que contêm um ponto de entrada (main function) e são compilados para gerar um programa executável. Eles são utilizados para criar aplicativos que podem ser executados diretamente.

- Devem ser declarados como package main.
- Devem conter a função main, que é o ponto de entrada do programa.
- Ao compilar um pacote executável, o comando go build gera um arquivo executável.

### Pacotes Não Executáveis

- Devem ser declarados com um nome de pacote diferente de main, frequentemente refletindo a funcionalidade fornecida pelo pacote.
- Funções, tipos e variáveis que começam com letra maiúscula são exportadas e podem ser usadas por outros pacotes.
- Pacotes não executáveis são importados e utilizados em outros pacotes, incluindo pacotes executáveis.


### MODULO- 

- Conjunto de pacotes que compoem um conjunto de pacotes que compe seu projeto compilando em só lugar

```
cd PASTA
go mod init modulo 

```
### BUILD

- Cria um arquivo binario compilado na raiz com nome referente ao modulo que criei
- Não fica mexendo manualmente nele

```
go build
```
### BAIXAR dependencias externas 

```
go get github.com/badoux/checkmail
```

### Apaga todos os pacotesque não estão sendo usados

```
 go mod tidy
```