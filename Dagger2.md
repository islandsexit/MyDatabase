Dagger — это open source Dependency Injection библиотека от разработчиков [[Okhttp]], [[Retrofit]], [[Picasso]] и многих других замечательных библиотек, известных многим Android разработчикам.  
  
Главные преимущества Dagger :  

-   Статический анализ всех зависимостей
-   Определение ошибок конфигурации на этапе компиляции (не только в runtime)
-   Отсутствие reflection, что значительно ускоряет процесс конфигурации
-   Довольно небольшая нагрузка на память

В Dagger процесс конфигурации зависимостей разбит на 3 больших блока:  

-   инициализация графа завизимостей (ObjectGraph)
-   запрос зависимостей (`@Inject`)
-   удовлетворение зависимостей (`@Module`/`@Provides`)

## До Дагера
```kotlin
class MainActivity : AppCompatActivity{

	private lateinit var nameServices : NameServices
	private lateinit var aliasServices : AliasServices
	private lateinit var userRepository : UserRepository

	override fun onCreate(savedInstance:Bundle){
		super.onCreate(savedInstance)
		setContentView(R.layout.activity_main)
		init()
	}

	private fun init(){
		nameServices = CustomNamedServices()
		aliasServices = CustomAliaseServices()
		userRepository = DBRepository(aliasServices)
		userRepository.getUserName()
	}
} 
```

## После 
```kotlin
class MainActivity : AppCompatActivity{

	@Inject
	private lateinit var nameServices : NameServices
	@Inject
	private lateinit var aliasServices : AliasServices
	@Inject
	private lateinit var userRepository : UserRepository

	override fun onCreate(savedInstance:Bundle){
		super.onCreate(savedInstance)
		setContentView(R.layout.activity_main)
		AndroidInjector.inject(this)
	}

}
```

---
## P.s Не берусь за правильное написание, это чисто пример для понимания
