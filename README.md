# Android-Reference-kotlin
> ### Kotlin List
- reversed() : 배열을 뒤집은 후 새로운 객체에 할당하여 반환(List)
- reverse() : 배열을 뒤집은 후 호출한 배열에 적용
- reversedArray() : 배열을 뒤집은 후 새로운 객체에 할당하여 반환(Array)
- mapIndexed() : mapIndexed는 특정 iterable을 대상으로 map 연산을 할 때, 원소 뿐 아니라 해당 원소가 갖고 있는 인덱스를 함께 묶어 매핑하게 해주는 함수
> ### by 키워드
- 위탁자(delegator) → 수탁자(delegate) 형태이며 어떤 일의 책임 및 처리를 다른 클래스 또는 메서드에게 넘긴다는 의미.
- 한 객체가 기능 일부를 다른 객체로 넘겨주어, 첫 번째 객체 대신 수행하도록 하는 일.
- 다른 클래스의 기능을 사용하되 그 기능을 변경하지 않으려면 상속 대신 위임.
- 위임을 활용하면 한 객체의 변경이 다른 객체에 미치는 영향이 작아짐.
```kotlin
interface Base {
    fun print()
}

class BaseImpl(val x: Int) : Base {
    override fun print() { print(x) }
}

/*Derived 클래스는 Base 인터페이스를 상속할 수 있으며, 
모든 public 메서드를 지정한 객체로 위임한다.*/
class Derived(b: Base) : Base by b

fun main() {
    val b = BaseImpl(10)
    Derived(b).print()
}

실행시 출력 값
10
```
