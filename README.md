### Многомодульный проект на Gradle

Чтобы подключить новые модули к проекту, добавляем в корне проекта в settings.
gradle новые созданные модули:

include 'db'
include 'service'
include 'api'

После создания многомодульного проекта подключим связанные модули между собой.

Для подключения модуля db в модуль service добавим зависимость:

dependencies {
    implementation project(":db")
}
Для подключения модуля service в модуль api добавим зависимость:

dependencies {
    implementation project(":db")
    implementation project(":service")
}
Теперь можно собрать проект, выполнив команду:

gradle build
