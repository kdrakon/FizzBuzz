# FizzBuzz
It's FizzBuzz, or at least another inane version of it.

```scala
object FizzBuzz extends App {

  implicit class FizzyOrBuzzy(i: Int) {
    def isFizz = i % 3 == 0
    def isBuzz = i % 5 == 0
    def toFizzBuzz = if (i.isFizz || i.isBuzz) Some(("Fizz".filter(_ => i.isFizz)).concat("Buzz".filter(_ => i.isBuzz))) else None
  }

  print(
    (1 to 100).flatMap(i => i.toFizzBuzz orElse Some(i)).mkString(",")
  )

}
```
