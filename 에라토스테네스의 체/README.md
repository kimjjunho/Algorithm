# 에라토스테네스의 체

- 에라토스테네스의 체는 가장 먼저 소수를 판별할 범위만큼 배열을 할당하여, 해당하는 값을 넣어주고, 이후에 하나씩 지워나가는 방법을 이용한다.

```kotlin
fun main(){
    val untilNum = readLine()!!.toInt()
    var primeNumberList = ArrayList<Int>()

    for(i in 2..untilNum){
        primeNumberList.add(i)
    }

    primeNumberList = sieveOfEratosthenes(primeNumberList)

    for(i in 0 until primeNumberList.size){
        if(primeNumberList[i] != 0){
            print(primeNumberList[i])
            print(" ")
        }
    }
}

fun sieveOfEratosthenes(primeNumberList: ArrayList<Int>): ArrayList<Int>{

    val answerList : ArrayList<Int> = primeNumberList

    for (i in 0 until answerList.size){
        if (answerList[i] == 0){
            continue
        }

        for(j in i+answerList[i] until answerList.size step answerList[i]){
            answerList[j] = 0
        }
    }


    return answerList
}
```



- https://velog.io/@max9106/Algorithm-에라토스테네스의-체
