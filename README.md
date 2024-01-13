# Использование коллекции
### Для того, чтобы коллекция работа следует особое внимание обратить на методы (GET, POST, PATCH, DELETE)
***Для создания коллекции и работы запросов использовался инструмент тестирования - Postman***

## В коллекции 4 основных запросы (URL - api.github.com)
## 1. Создание issue с названием Issue 1, описанием Something went wrong. Также у этой issue должен быть label — bug — и assignee — вы (текущий логин на GitHub):
   - Чтобы создать данный запрос нужно обраться к документации GitHub (POST/repos/{owner}/{repo}/issues)
   - В поле URL ввести адрес API GitHub issues - метод **POST** https://api.github.com/repos/{owner}/{repo}/issues
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
>>> ВАЖНО!!! Обязательно исправьте {owner} на логин на GitHub и нажать "Send" для выполнения запроса
  
## 2. Получить список issues 
- Чтобы создать данный запрос нужно обраться к документации GitHub (GET/repos/{owner}/{repo}/issues/{issue_number})
- В поле URL введите адрес API GitHub issues - метод **GET** https://api.github.com/repos/{owner}/{repo}/issues
- Исправить {owner} на логин на GitHub, у меня это - EkaterinaValovaya
- Исправить {repo} на имя вашего репозитория, у меня это - Attestation
- В разделе "Authorization" выберать тип "Bearer Token" и вставить ранее сгенерированный API-ключ (выбирала именно этот пункт, т.к. с другим методом авторизации запросы не работали)
- В разделе "Headers" добавьте следующий заголовок: accept-application/vnd.github+json
- Нажать кнопку Send
  
## 3. Изменить название задачи на Issue 2
- Чтобы создать данный запрос нужно обраться к документации GitHub (PATCH/repos/{owner}/{repo}/issues/{issue_number})
- В поле URL введите адрес API GitHub issues - метод **PATCH**  https://api.github.com/repos/{owner}/{repo}/issues
- Исправить {owner} на логин на GitHub, у меня это - EkaterinaValovaya
- Исправить {repo} на имя вашего репозитория, у меня это - Attestation
- Исправить "{issue_number}" на номер issue, который вы получили из предыдущего запроса
- В разделе "Authorization" выберать тип "Bearer Token" и вставить ранее сгенерированный API-ключ (выбирала именно этот пункт, т.к. с другим методом авторизации запросы не работали)
- В разделе "Headers" добавьте следующий заголовок: accept-application/vnd.github+json
- В разделе "Body" выберать тип Rawи формат JSON и ввести следующий код на изменение:
```
{
 "title": "Issue 2"
}
```
## 5. Удаление Issue 2
- Чтобы создать данный запрос нужно обраться к документации GitHub: (DELETE/repos/{owner}/{repo}/issues/{issue_number}/lock)
  >>> Проанализировав документацю для API-запросов GitHub мне показалось странным размещение запросы с методом DELETE в разделе Unlock an issue (как минимум, это не логично), обратите внимание, что в конце запроса стоит команда **lock** возможно из-за этого запрос исполняется неверно (он не удаляет созданный issue), тем не менее опищу как я это делала:
- В поле URL введите адрес API GitHub issues с номером issue - метод **DELETE** https://api.github.com/repos/{owner}/{repo}/issues/{issue_number}
- Исправить {owner} на логин на GitHub, у меня это - EkaterinaValovaya
- Исправить {repo} на имя вашего репозитория, у меня это - Attestation
- Исправить "{issue_number}" на номер issue, который вы получили из предыдущего запроса
- В разделе "Authorization" выберать тип "Bearer Token" и вставить ранее сгенерированный API-ключ (выбирала именно этот пункт, т.к. с другим методом авторизации запросы не работали)
- В разделе "Headers" добавьте следующий заголовок: accept-application/vnd.github+json
  
