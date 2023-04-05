# Настройка CI GitHub Actions для gradle java.

1.	Создайте новый репозиторий на GitHub и загрузите туда свой проект
2.	Перейдите на GitHub и создайте новый Actions

![image](https://user-images.githubusercontent.com/113560499/226146345-54f4595d-ebd7-44ba-b8b1-5df8abd37075.png)

3. В поиске впишите gradle, нажмите Enter и выберите Java with Gradle

![image](https://user-images.githubusercontent.com/113560499/226146514-b1517e94-1687-455c-8b08-e080b340d52f.png)

4.	Вставьте в файл gradle.yml следующий код

```.yml
name: Java CI with Gradle

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

permissions:
  contents: read
jobs:
  build:

    runs-on: ubuntu-latest   # образ для сборки

    steps:
    - uses: actions/checkout@v3
    - name: Set up JDK 11
      uses: actions/setup-java@v3
      with:
        java-version: '11'
        distribution: 'temurin'
    - name: Build with Gradle
      uses: gradle/gradle-build-action@67421db6bd0bf253fb4bd25b31ebb98943c375e1
      with:
        java-version: '11'
        distribution: 'adopt'
    - name: Run SUT
      run:  java -jar ./artifacts/app-order.jar & sleep 10
    - name: Grant execute permission for gradlew
      run: chmod +x gradlew
    - name: Build with Gradle
      run: ./gradlew test --info
```

Часть `-jar ./artifacts/app-mbank.jar` может меняться, но первая часть для вас во всех ДЗ при запуске на вашем ПК будет именно такой.
Для запуска тестов в режиме headless используйте: -Dselenide.headless=true

5.	Сохраните изменения

![image](https://user-images.githubusercontent.com/113560499/226146900-46e290d4-bf76-4fcc-8bbc-9d3fa5f30154.png)

Обратите внимание, что кнопка сохранения изменений может распологаться также внизу.

6.	После сборки вашего проекта отобразиться зеленая птичка

![image](https://user-images.githubusercontent.com/113560499/226147728-e895609a-5421-44e9-8281-5ded24cd018f.png)

7.	Нажмите на зеленую птичку и выберите "Details"

![image](https://user-images.githubusercontent.com/113560499/226147760-624c2af7-990e-41fe-a649-a1b169c0eaf5.png)

8.	Создайте ссылку на бейдж

![image](https://user-images.githubusercontent.com/113560499/226147787-414db8c7-009c-4091-9b1e-dc9693390d30.png)

9.	Скопируйте в буфер обмена ссылку на бейдж

![image](https://user-images.githubusercontent.com/113560499/226147866-5c701fb3-47cc-46d6-ad15-b382bdaf520d.png)

10.	Вернитесь в корень репозитория и создайте README.md

![image](https://user-images.githubusercontent.com/113560499/226147924-c7e9b247-1413-4486-9733-a13c9b7d8ec3.png)

11. Вставьте в README.md ссылку, скооперированную на этапе 8 и сохраните изменения. После сохранения изменений отображается бейдж со статусом сборки

![image](https://user-images.githubusercontent.com/113560499/226147981-67cb745b-ef0f-4493-b2d9-6d2e27dae3bd.png)

12.	После сохранения заберите изменения в локальный репозиторий командной git pull
