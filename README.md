# Estudo-Kotlin-e-Swift


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

fun (num_a : Int, num_b : Int) : Int {
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
