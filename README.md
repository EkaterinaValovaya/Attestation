# Использование коллекции
### Для того, чтобы коллекция работа следует особое внимание обратить на методы (GET, POST, PATCH, DELETE)
***Для создания коллекции и работы запросов использовался инструмент тестирования - Postman***

## В коллекции 4 основных запросы:
1. Создание issue с названием Issue 1, описанием Something went wrong. Также у этой issue должен быть label — bug — и assignee — вы (текущий логин на GitHub):
   - Чтобы создать данный запрос нужно обраться к документации GitHub [Текст ссылки] (https://docs.github.com/en/rest/issues/issues?apiVersion=2022-11-28#about-issues) (POST /repos/{owner}/{repo}/issues)
   - В поле URL ввести адрес API GitHub issues - https://api.github.com/repos/{owner}/{repo}/issues
   - Исправить {owner} на логин на GitHub, у меня это - EkaterinaValovaya
   - Исправить {repo} на имя вашего репозитория, у меня это - Attestation
   - В разделе "Authorization" выберать тип "Bearer Token" и вставить ранее сгенерированный API-ключ (выбирала именно этот пункт, т.к. с другим методом авторизации запросы не работали)
   - В разделе "Headers" добавить требуемые параметры (по документации рекомендовано: ключ accept, значение application/vnd.github+json)
   - В разделе "Body" выбрать тип "Raw", формат "JSON" и ввести требуемые заданием параметры:

```
{
 "title": "Issue 1",
 "body": "Something went wrong.",
 "labels": ["bug"],
 "assignees": ["{owner}"]
}
```

 - Замените "{owner}" на ваш логин на GitHub.

7. Нажмите на кнопку "Send" (Отправить) для выполнения запроса.
3. Получить список issues
4. Изменить название задачи на Issue 2
5. Удалите Issue 2
