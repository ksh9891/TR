# 백준 알고리즘 2839번 문제
* 제목 : 설탕 배달
* URL : https://www.acmicpc.net/problem/2839  
* 사용언어 : Kotlin

## 문제  
상근이는 요즘 설탕공장에서 설탕을 배달하고 있다. 상근이는 지금 사탕가게에 설탕을 정확하게 N킬로그램을 배달해야 한다. 설탕공장에서 만드는 설탕은 봉지에 담겨져 있다. 봉지는 3킬로그램 봉지와 5킬로그램 봉지가 있다.

상근이는 귀찮기 때문에, 최대한 적은 봉지를 들고 가려고 한다. 예를 들어, 18킬로그램 설탕을 배달해야 할 때, 3킬로그램 봉지 6개를 가져가도 되지만, 5킬로그램 3개와 3킬로그램 1개를 배달하면, 더 적은 개수의 봉지를 배달할 수 있다.

상근이가 설탕을 정확하게 N킬로그램 배달해야 할 때, 봉지 몇 개를 가져가면 되는지 그 수를 구하는 프로그램을 작성하시오.

## 입력
첫째 줄에 N이 주어진다. (3 ≤ N ≤ 5000)

## 출력
상근이가 배달하는 봉지의 최소 개수를 출력한다. 만약, 정확하게 N킬로그램을 만들 수 없다면 -1을 출력한다.

## 풀이
반복문을 사용하고, 특정조건을 만족하면 빠져나올 수 있도록 설계한다.

최소한의 봉지로 담기를 원하기 때문에 5kg 봉지에 가장 먼저 담아본다.

그 후 정확히 나눠떨어지지 않는다면, 5kg 한 봉지를 해체하고 3kg 봉지에 담을 수 있는지 체크하는 식으로 계속 작업한다.

5kg를 해체하면서 3kg 담는 데 마지막까지 3kg 다 담을 수 없다면 분배가 불가능 한 것으로 -1을 리턴

## 코드 
```kotlin
import java.util.Scanner

fun main() {
    val stdIn = Scanner(System.`in`)
    var sugar = stdIn.nextInt()
    var count = 0

    while (true) {
        if (sugar % 5 == 0) {
            println(sugar / 5 + count)
            break
        } else if (sugar <= 2) {
            println(-1)
            break
        }
        sugar -= 3
        count++
    }
}
```