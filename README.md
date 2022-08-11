## Анализ 
Анализ необходимых мощностей для бесперебойной работы приложения 

## Разработка CI/CD 
Развернуть сервер Bitbucket и Jenkins для настройки 

Создать новый проект и выложить ранее работающий код в приватный репозиторий в ветку "master"

Создать отдельную ветку "dev"

Запретить любые коммиты в ветку "master"

Дать доступ к репозиторию разработчикам и тестировщикам

Поставить задачу тестировщикам написать необходимые тесты

Настроить Post Webhooks в Bitbucket и настроить джобы с пайплайном для Jenkins

## Принцип работы 

1) Поступает задача от клиента

2) Разработчики создают fork репозитория и вносят изменения, после всех изменений создают pull request (pr) в ветку "dev".

Каждый pr должен быть одобрен как минимум одним другим разработчиком.

3) Далее команда тестировщиков при необходимости пишут дополнительные тесты. 

4) Далее после мерджа отрабатывает джоб дженкинса и заливает весь код на тестовый стенд после чего прогоняет все тесты.

Если тест провалился запускается скрипт, который откатывает последние изменения в ветке "dev" и отправляется оповещение

Если тесты прошли успешно отправляется орповещение на почту и менеджер оценивает резултат на тестовом стенде.

5) После согласования с менеджером создается pull request из ветки "dev" в ветку "master".

Снова отрабатывает джоб дженкинса заливает код на ПРОД сервер и снова прогоняет тесты с оповещением о результатах.









