[[Основы классов в Kotlin]]

Эти классы позволяют создать ограниченную иерархию классов, во время компиляции заранее известны все прямые наследники этих классов.

Удобно использовать как State в presentation-слое 

```kotlin
sealed class WeatherType(  
    val weatherDesc: String,  
    @DrawableRes val iconRes: Int  
) {  
    object ClearSky : WeatherType(  
        weatherDesc = "Чистое небо",  
        iconRes = R.drawable.ic_sunny  
    )  
    object MainlyClear : WeatherType(  
        weatherDesc = "В основном ясно",  
        iconRes = R.drawable.ic_cloudy  
    )  
    object PartlyCloudy : WeatherType(  
        weatherDesc = "Переменная облачность",  
        iconRes = R.drawable.ic_cloudy  
    )
}
```

Тут, к примеру типы погоды представленны sealed-классом