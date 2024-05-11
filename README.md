# Estudo-Kotlin-e-Swift

## [Veja também o básico de numpy clicando aqui](/numpy/README.md)

## Objetivo

O objetivo desse humilde markdown é explorar de forma sucinta e básica a sintaxe de duas importantes linguagens: Kotlin e Swift. Essas linguagens possivelmente
serão cobradas em nossa prova. O mais interessante é que eu não estou usando qualquer ferramenta de IA tampouco sendo assistido pelo chatGPT
o que é um ato revolucionário em 2024.

## Kotlin

Brother, é importante sabermos um pouco da historinha dessa linguagem, pelo menos o básico. O java era a linguagem mais utilizada para o ambiente Android.
No entanto, a Oracle, que é a que mantém a linguagem atualmente, adotou uma postura inflexivel e isso irritou bastante a poderosa Google. A jetbrains, a empresa que 
faz umas IDEs da hora tal qual o InteliJ (acho que é assim que escreve) desenvolveu uma linguagem plenamente compativel com o java. Quando escrevo "plenamente" é porque 
código Kotlin pode ser chamado pelo java e código java pode ser chamado pelo kotlin. Se você quiser, pode usar as duas linguagens no projeto e no mesmo ambiente de execução.
Antes de estudar para a prova eu já tava por dentro disso pois o Spring sustenta projetos kotlin e java. Depois dessa palestrada, convém concluir a historinha:

A Google oficializa o kotlin como a linguagem oficial de desenvolvimento android.


### Tipos de dados no kotlin 
Inteiros: Byte, Short, Int, Long
Ponto flutuante: Float, Double
Booleano: Boolean
Caractere: Char
Cuidado com o Boolean,Int e Char. Int e Char são reduzidos mesmo e Boolean é escrito todo. Digo isso pois em provas anteriores eu cai no bait do Integer

Como no java é Integer, eu acabei confundindo. Porém, gravem, é Int,Char e Boolean


### Como declarar uma váriavel no kotlin

```kotlin
var time: String = "Vasco da Gama"

val cidade: String = "Valparaiso de Goiás"

val numero_da_sorte = 13

```

Seguinte, não manjo muito dessa linguagem e tudo que eu quero é passar na prova. No auge da vontade de aprender e fixar algo, estou escrevendo para uns camaradas nerdolas
Salve Lipe,Cauã e Malu . Já deixei o salve pros brous, agora continuando...Não sei muito, mas sei que val é para declarar constantes,ou seja, coisa que não pode mudar e var para
coisas que podem ser reatribuidas. Só lembrar que seu amigo val é um cara único e imutavel, ou voce pensa que var lembra variavel.

Veja que com kotlin há inferência de tipo.
### Como codificar uma função com Kotlin

Beleza, agora como eu escrevo uma função. Mano, são 22 hrs e eu tô cansado, porém tô achando maneiro e produtivo escrever essa paradinha. Quem sabe no proximo concurso eu documente o aprendizado com mkdocs, assim eu aprendo e ajudo os de fé. Voltando, a tá tarde e criatividade tá baixa , então vou usar o exemplo clássico da soma.

```kotlin

fun soma (num_a : Int, num_b : Int) : Int {
return a+b
}
```

repare que você não precisa se preocupar com ponto e vírgula.


### Como interpolar com Kotlin

Muito fácil . É assim:

```Kotlin
val time : String = "Vasco da Gama"

val time_do_mal = "Flamengo"

val minha_string = " Você pensa que o $time é time, $time não é time não, time é $time_do_mal. $time é seleção

```

Se precisar interpolar uma expressão, use ${}

ex:

```kotlin
val ano_ingresso :Int = 2018

var ano_saida: Int = 2030

val minha_frase : String = "Hoje já é $ano_saida e eu estou há ${ano_saida - ano_ingresso} anos nessa Universidade. Professor Vandor, seu canalha."
```


### for e if 

Nessa linguagem for e if são bem padrõezinhos. Usa parenteses o que deixa meio antigao na minha opinião ou seria pq estou me acostumando a codificar com python?


for ( i in 1..4) {

}

ele faz 1 a 4 num intervalo fechado para ambas extremidades, tu pode a extremidade do intervalo final usando until


for(i in 1 until 10)

tu pode colocar um passo pra variavel como step

for(i in 1 until 8 step 2)
{

}

## Classe kotlin


Galera, fiz esse exemplo para gente estudar


```Kotlin
class Time(
    private val nome: String,
    private val cidade: String,
    private val fundacao: Int
) {
    fun saudacao(): String {
        return when (nome.toLowerCase()) {
            "flamengo" -> "Melhore como pessoa"
            "vasco" -> "Eai, vascão"
            else -> "Ok"
        }
    }

    fun exibirDetalhes(): String {
        return "Time: $nome\nCidade: $cidade\nAno de Fundação: $fundacao"
    }
}

```
veja os modificadores de acesso, o famoso when que é tipo um switch case e o construtor

Herança é assim

```kotlin
open class Animal(val nome: String) {
    open fun fazerBarulho() {
        println("$nome está fazendo algum barulho")
    }
}

class Cachorro(nome: String) : Animal(nome) {
    override fun fazerBarulho() {
        println("$nome está latindo")
    }
}

class Gato(nome: String) : Animal(nome) {
    override fun fazerBarulho() {
        println("$nome está miando")
    }
}

fun main() {
    val cachorro = Cachorro("Rex")
    cachorro.fazerBarulho() // Saída: Rex está latindo

    val gato = Gato("Garfield")
    gato.fazerBarulho() // Saída: Garfield está miando
}


```
repara que pra uma classe gerar outras voce tem que colocar open


## Swift 

Vamos lá cabróns e Malu.


Pow, a ideia é não enrolar mto. Então simbora

Os tipos de variáveis:

Para lascar a nossa vida, muda um pouco do kotlin:
Inteiros (Int)
Números de Ponto Flutuante (Float e Double)
Booleanos (Bool)
Caracteres (Character)
Cadeias de Caracteres (String)

repare que é Bool e Character, no kotlin é Boolean e Char. 

para declarar uma constante com swift voce usa let e para declarar uma variavel voce usa var

então exemplos de declaracao com swift:

```Swift

let time: String = "Vasco da Gama"

var habilidade = 3


```


### Como codificar uma função com swift

Bem simples, curte só:
```Swift
func soma (_ a: Int, _ b: Int) -> Int {
  return a+b;
}
```

veja que tem esse sublinhadinho, com ele podemos passar os argumentos na ordem igual fazemos com as funções decentes
```
c = soma(3,2)
```
se a função fosse:

```Swift
func soma (a: Int, b: Int) -> Int {
  return a+b;
}
```
eu teria que usar 
```
c = soma(a:3, a:2)
```

### Como interpolar 

Para interpolar é coisa mais esquisita que já vi na minha vida

é assim:

```Swift
let time = "Vasco"

let frase = "Posso morrer pelo meu \(time),posso chorar se ele não ganhar ,mas se ele ganhar não há garganta que não pare de berrar"



```
### for e if

mesmo esquema do kotlin só que sem parenteses 



### Classe

```Swift
class Pessoa {
    // Propriedades da classe
    private var nome: String
    public var idade: Int
    
    // Método inicializador
    init(nome: String, idade: Int) {
        self.nome = nome
        self.idade = idade
    }
    
    // Método da classe
    func saudacao() {
        print("Olá, meu nome é \(nome) e eu tenho \(idade) anos.")
    }
}

// Exemplo de uso da classe Pessoa
let pessoa1 = Pessoa(nome: "Ana", idade: 30)
pessoa1.saudacao() // Saída: Olá, meu nome é Ana e eu tenho 30 anos.

```

o gpt fez esse codigo, eu falhei com a promessa
mas curte só o construtor é int()

e tem private,public e internal como possiveis modificadores de acesso
