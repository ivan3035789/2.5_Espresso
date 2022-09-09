# 2.5_Espresso

# Домашнее задание к занятию "2.5 Espresso"

Любые вопросы по решению задач задавайте в чате учебной группы.

---

## Задание 1. Реализация теста на проверку "Главного экрана"

### Шаг 1. Запустите тестовый проект в Android Studio

- Создайте новый репозиторий (ссылку на этот репозиторий нужно будет прислать в качестве результата выполнения домашнего задания)
- Выгрузите тестовый проект https://github.com/netology-code/mqa-homeworks/tree/main/2.5%20Espresso/simpleAppForEspresso
- Запустите тестовый проект в Android Studio

### Шаг 2. Добавление зависимостей

- Откройте файл /app/build.gradle
- Проверьте наличие и при необходимости добавьте следующие зависимости в блок "dependencies":
```java
     testImplementation 'junit:junit:4.13.2' 
     androidTestImplementation 'androidx.test.ext:junit:1.1.3' 
     androidTestImplementation 'androidx.test:rules:1.4.0'  
     androidTestImplementation 'androidx.test:runner:1.4.0' 
     androidTestImplementation 'androidx.test.espresso:espresso-core:3.4.0' 
```

### Шаг 3. Создание и настройка класса тестов

- Создайте новый класс в директории /app/src/androidTest/java/ru/kkuzmichev/simpleappforespresso/
- Добавьте @RunWith(AndroidJUnit4.class) над именем класса
- Задайте правило для MainActivity внутри класса:
```java
@Rule
public ActivityTestRule<MainActivity> activityTestRule =
	new ActivityTestRule<>(MainActivity.class);
```

### Шаг 4. Написание теста

- Запустите приложение
- Посмотрите иерархию элементов с помощью Layout Inspector [Инструкция от Google](https://developer.android.com/studio/debug/layout-inspector)
- Найдите элемент с текстом "This is home fragment" и его id
- Напишите тест проверяющий что у найденного id текст "This is home fragment"

Шаблон теста:
```java
@Test
public void testName() {
    ViewInteraction mainText = onView(
        withId(R.id.найденный id)
    );
    mainText.check(
        matches(
            withText(Проверяемый текст)
        )
    );
}
```

### Шаг 5. Запуск теста и просмотр отчета

- Запустите тест нажав кнопку запуска возле метода теста
- Проверьте что тест прошел успешно
- Экспортируйте отчет в файл html 
