# Atividades
## 1. Cálculo de IMC
```kotlin
fun main() {

    print("Insira seu peso. (Ex: 50) ")
    val peso = readln().toFloat()
    print("Insira sua altura. (Ex:1.50) ")
    val altura = readln().toFloat()
    val imc = peso / (altura * altura)
    
    if (imc <  18.50) {
        println("Você está abaixo do peso")
    } 
    else if(imc >= 18.5 && imc < 24.9) {
        println("Você está com o peso normal")
    } 

    else if(imc >= 25 && imc < 29.9) {
        println("Você está com sobrepeso (acima do peso desejado)")
    } 
    
    else {
        println("Você está obeso(a)")
    }
 } 
```

## 2. Cálculo de despesa de mão de obra.

```kotlin
import kotlin.math.pow

fun main() {

    print("Digite a largura do terreno: ")
    val largura = readln().toInt()

    print("Digite o comprimento do terreno: ")
    val comprimento = readln().toInt()
    val area = largura * comprimento //calculo da area 
    var mestres = 0
    var serventes = 0
    var engenheiros = 0

    print("Quantidade de quartos sem suíte: ")
    val semSuite = readln().toInt()
    print("Quantidade de áreas de serviço: ")
    val areaServico = readln().toInt()
    print("Quantidade de piscinas: ")
    val piscina = readln().toInt()
    print("Quantidade de quartos com suíte: ")
    val comSuite = readln().toInt()
    print("Quantidade de banheiros: ")
    val banheiro = readln().toInt()

    var subtotal: Float //declarando o tipo de dado das variaveis
    var total: Float
    var lucro: Float

    if (area > 10) {  //contrata profissionais com base no tamanho do terreno
        println("Subtotal por item")
        mestres = 1
        serventes = (area / 10) * 2
        if (area >= 100) {
            engenheiros = area / 100
        }

    // calculos da mão de obra. usamos val pois tem um valor fixo
        val mestreTotal = mestres * 3500
        println("Mestre: R$ $mestreTotal")

        val serventesTotal = serventes * 1900
        println("Serventes: R$ $serventesTotal")

        val engenheirosTotal = engenheiros * 11000
        println("Engenheiros: R$ $engenheirosTotal")

        // calculos dos itens
        val areaTotal = (area / 10) * 4500
        println("Área do Terreno: R$ $areaTotal")

        val semSuiteTotal = semSuite * 12000
        println("Quartos sem Suíte: R$ $semSuiteTotal")

        val areaServicoTotal = areaServico * 15000
        println("Área de Serviço: R$ $areaServicoTotal")

        val piscinaTotal = piscina * 27550
        println("Piscina: R$ $piscinaTotal")

        val comSuiteTotal = comSuite * 17000
        println("Quartos com Suíte: R$ $comSuiteTotal")

        val banheiroTotal = banheiro * 5000
        println("Banheiros: R$ $banheiroTotal")

        subtotal = (mestreTotal + serventesTotal + engenheirosTotal).toFloat()
        println("Total mão de obra: R$ $subtotal")

        total = areaTotal + semSuiteTotal + areaServicoTotal + piscinaTotal + comSuiteTotal + banheiroTotal + subtotal
               
        lucro = total
        val custoFinal = total * 1.25f
        val lucroReal = custoFinal - lucro

         println("Total mão de obra: R$ " + "%.2f".format(subtotal))
        println("Custo final da obra: R$ " + "%.2f".format(custoFinal))
        println("Lucro da empresa (25%): R$ " + "%.2f".format(lucroReal))
    } else {
        println("Erro ao contratar o serviço. Para o contrato, o terreno deve ter mais de 10m². ")
    }
}
```

