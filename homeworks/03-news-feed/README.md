# Домашно 3

`Краен срок: 23.01.2022, 23:45`

Задачата ни този път е фокусирана върху HTTP и Design Patterns, които бяха и последните теми от курса.

За разлика от предните задачи, този път няма да има автоматични референтни тестове, готови интерфейси, които да имплементирате или фиксирана от нас структура на проекта - имате цялата свобода, що се отнася до дизайна, имплементацията и тестването.

## **News Feed** :newspaper:

Създайте програма, която предоставя възможност за търсене на новини по различни критерии.

[REST API](https://newsapi.org/)-то, което ще използваме за намиране на новини, е публично, безплатно и работи с API Key, който може да вземете след [регистрация](https://newsapi.org/register).

Необходимият ви endpoint e `/v2/top-headlines`, документиран [тук](https://newsapi.org/docs/endpoints/top-headlines).

API-то има свои лимити - можете да правите **до 100 заявки на ден**, заради което ще се наложи да обмислите и оптимизирате използването му, докато разработвате и тествате.

### Дизайн

Както казва чичото на Спайдърмен: "With Great Power Comes Great Responsibility".
Този път, вие определяте абстракциите, които ще използвате. Единственото условие е, да приложите знанията си за design patterns (използвайте поне един), като задачата предразполага в това отношение.

### Функционалност

Критериите, по които можем да търсим новини, са:

- ключови думи (задължителен параметър)
- категория
- държава

Както може да видите в [документацията](https://newsapi.org/docs) на News API-то, то поддържа задължителни и опционални параметри - имплементацията ви също трябва да работи така - например, трябва да позволява търсене по ключови думи и категория, но не и само по държава.

#### Странициране

Когато едно API може да върне голям брой резултати, обикновено (от performance съображения) то не го прави на един път, а използва т.нар. *странициране* - връща резултатите на части (страници), като първо извличаме първа страница, после втора и т.н.
Имплементирайте възможност за прочитане на **до 3 страници**, с **до 50 новини** във всяка от тях.

:warning: **Важно:** Имайте предвид лимита от 100 request-a на ден, при имплементиране и тестване на тази част от задачата.

#### Error handling

При изпращане на request към сървъра, обработката му не винаги е успешна. Когато нещо се обърка, сървърът връща подходящ статус код и съобщение, които следва да обработвате. Моделирайте тази функционалност с помощта на custom checked exceptions.
Различните грешки, които могат да се върнат, може да разгледате [тук](https://newsapi.org/docs/errors)

### Тестване

Сами отговаряте за цялостното тестване на решението си, ние пък ще оценяваме колко добре сте се справили с това.
Целете се към висок code coverage, както и покрийте всички възможни сценарии, които вашата програма поддържа, включително такива, които могат да ви се сторят тривиални.
За постигане на висок code coverage, може да се наложи да използвате Mockito.

## **Предаване**

За да предадете решението си, архивирайте в **zip** архив **src** и **test** директориите на проекта и го качете в съответния assignment в грейдъра.

### **Оценяване**

Решението може да ви донесе до 100 точки, като ще бъде оценявано за:

* функционална пълнота и коректност, и за автоматични тестове с добър code coverage (50% от оценката)
* добър обектно-ориентиран дизайн, спазване на правилата за чист код (50% от оценката: 5% от инструментите за статичен код анализ на грейдъра и 45% от code review от асистент)

**Успех!** :four_leaf_clover:
