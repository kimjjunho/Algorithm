# 달팽이

```kotlin
import java.util.*

var count  = 1
var array =  Array(0){IntArray(0)}
var sizeH = 0
var sizeW = 0
fun main(){
    val scanner = Scanner(System.`in`)
    sizeH = scanner.nextInt()
    sizeW = scanner.nextInt()

    array = Array(sizeH){ IntArray(sizeW) }

    goLeft(0)

    for(i in 0 until sizeH){
        for(j in 0 until sizeW){
            print(array[i][j])
            print(" ")
        }
        println()
    }
}
fun goRight(y: Int){

    var xLast = -1
    for(i in 0 until sizeW){
        if(array[y][i] == 0){
            xLast = i
            array[y][i] = count++
        }
    }

    if(xLast!= -1){
        goUp(xLast)
    }
}

fun goDown(x: Int){
    var yLast = -1
    for(i in 0 until sizeH){
        if(array[i][x] == 0){
            yLast = i
            array[i][x] = count++
        }
    }

    if(yLast != -1){
        goLeft(yLast)
    }
}

fun goLeft(y:Int){
    var xLast = -1
    for(i in sizeW-1 downTo 0){
        if(array[y][i] == 0){
            xLast = i
            array[y][i] = count++
        }
    }

    if(xLast != -1){
        goDown(xLast)
    }
}

fun goUp(x:Int){
    var yLast = -1
    for(i in sizeH-1 downTo 0){
        if(array[i][x] == 0){
            yLast = i
            array[i][x] = count++
        }
    }

    if(yLast != -1){
        goRight(yLast)
    }
}
```