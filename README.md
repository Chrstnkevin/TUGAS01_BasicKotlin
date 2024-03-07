# BANGKIT ACADEMY 2024 : MOBILE DEVELOPMENT
### Dicoding: Memulai Pemrograman dengan Kotlin

Halo semua pada kesempatan ini saya ingin membagikan penugasan 1 saya pada track MobileDdevelopment BANGKIT 2024'


![sertifikat_course_80_3855793_290224001029-1](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/323ed182-8151-49ff-a240-6535c94b8b7d)
![sertifikat_course_80_3855793_290224001029-2](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/8c8c55cc-47a5-4478-8096-2499aa747d02)
![sertifikat_course_80_3855793_290224001029-3](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/b0be919e-b5cf-40eb-8b8e-3bb85c6d9521)

#### Penugasan : 
Di dalam proyek, terdapat beberapa latihan dengan detail seperti di bawah ini:

## Latihan 1: Fundamental
> TODO 1
> Sesuaikan fungsi di bawah ini dengan kode untuk mengecek apakah parameter number merupakan angka genap

```
fun isEvenNumber(number: Int) = number % 2 == 0  //modulo 2 untuk genap
```
> TODO 2
> Sesuaikan fungsi di bawah ini dengan kode untuk mengecek apakah parameter number lebih dari 5

```
fun moreThanFive(number: Int) = number > 5 //mengecek lebih dari 5
```

> TODO 3
> Sesuaikan fungsi di bawah ini agar dapat menghasilkan nilai akhir dengan rumus: param * ( param + 10 )

```
fun result(number: Int) = number * (number + 10) //nilai akhir
```

Serta untuk fungsi mainnya adalah sebagai berikut:
```
fun main() {
    val listNumber = 1.rangeTo(100)
    for (number in listNumber) {
        if (isEvenNumber(number)) continue

        if (moreThanFive(number)) break

        val result = result(number)
        println("range result is $result")
    }
}
```

Output:

![image](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/a1f1e18c-5f69-43a1-bf15-110c20f99ec3)


## Latihan 2: Control Flow
> TODO 1
> Sesuaikan fungsi di bawah ini agar dapat mengembalikkan nilai dengan rumus perhitungan berikut: valueA + (valueB - valueC) Jika valueC bernilai null, silakan tetapkan nilai 50 sebagai nilai default-nya

```
fun calculate(valueA: Int, valueB: Int, valueC: Int?): Int {
    return valueA + valueB - (valueC?.toInt() ?: 50)  // elwis untuk nilai null
}
```

> TODO 2
> Sesuaikan fungsi di bawah ini agar dapat mengembalikkan text seperti berikut: Result is ${result}

```
fun result(result: Int): String {
    return "Result is $result"
}
```

Serta untuk fungsi mainnya adalah sebagai berikut:
```
fun main() {
    val valueA = 101
    val valueB = 52
    val valueC = 99

    val resultA = calculate(valueA, valueB, valueC)
    val resultB = calculate(valueA, valueB, null)

    println(
        """
        ${result(resultA)}
        ${result(resultB)}
        """.trimIndent()
    )
}
```

Output:

![image](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/8e1240c6-532a-4696-8c39-74f95db0e6e7)

## Latihan 3: Generics

> TODO 1
> Lengkapi fungsi di bawah ini agar dapat mengembalikkan tipe nilai sesuai dengan parameter yang dilampirkan

```
fun <T> checkType(args: T): String {
    return when (args) {
        is Int -> {
            "Yes! it's Integer"
        }
        is String -> {
            "Yes! it's String"
        }
        is Boolean -> {
            "Yes! it's Boolean"
        }
        is Double -> {
            "Yes! it's Double"
        }
        is List<*> -> {
            "Yes! it's List"
        }
        is Map<*, *> -> {
            "Yes! it's Map"
        }
        else -> {
            "Unknown type"
        }
    }
}
```

serta fungsi main adalah sebagai berikut
```
fun main() {
    println(
        """
        '[10, 9, 8 , 6]' is List? ${checkType(listOf(10, 9, 8, 6))}
        'Dicoding Indonesia' is String? ${checkType("Dicoding Indonesia")}
        'True' is Boolean? ${checkType(true)}
        '10.01' is Double? ${checkType(10.01)}
        """.trimIndent()
    )
}
```

Output:

![image](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/327c5bda-9398-42df-a18d-d50246713bf3)

## Latihan 4: Collections

> TODO 1
> Lengkapi inisialisasi fungsi dengan nilai kembalian Map di bawah ini dengan nilai key-value

```
fun vehicle() = mapOf<String, String>(
    "type" to "motorcycle",
    "maxSpeed" to "230Km/s",
    "maxTank" to "100Ltr"
)
```
Fungsi mainnya adalah sebagai berikut
```
fun main() {
    println(
        """
        My Map Result:
        ${vehicle()}
        """.trimIndent()
    )
}
```

Output:

![image](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/460811ae-4e94-4361-a3a9-fb5ed650f7f8)

## Latihan 5: Coroutines
> TODO 1
> Sesuaikan fungsi di bawah ini dengan kriteria

```
suspend fun sum(valueA: Int, valueB: Int): Int {
    delay(3000L) //waktu delay
    return valueA + valueB
}
```

> TODO 2
> Sesuaikan fungsi di bawah ini dengan kriteria
```
suspend fun multiple(valueA: Int, valueB: Int): Int {
    delay(2000L) // waktu delay
    return valueA * valueB
}
```
dan berikut fungsi main
```
fun main() = runBlocking {
    println("Counting...")

    val resultSum = async { sum(10, 10) }
    val resultMultiple = async { multiple(20, 20) }

    println(
        """
            Result sum: ${resultSum.await()}
            Result multiple: ${resultMultiple.await()}" 
        """.trimIndent()
    )
}
```
Output:

![image](https://github.com/Chrstnkevin/TUGAS01_BasicKotlin/assets/97864068/5d6bd9aa-ff38-4e50-80d0-fa93f515770b)
