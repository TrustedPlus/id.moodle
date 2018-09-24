## Moodle IdTrustedPlus

Инструкция для подключения авторизации [https://trusted.plus/id](https://trusted.plus/id) в системе moodle.

### Инструкция

1. Зарегистрируйте свое приложение в [https://trusted.plus/id](https://trusted.plus/id)

2. Перейдите в Ваш портал moodle на вкладку "Site administration > Server > OAuth 2 services" и нажмите кнопку "Create new custom services".
3. Заполните форму
    1. В поле "Client ID" введите Client ID приложения, созданного на сервисе IDTrustedPlus.
    2. В поле "Client secret" введите пароль от приложения, созданного на сервисе IDTrustedPlus.
    3. В поле "Scopes included in a login request" и "Scopes included in a login request for offline access" введите значение "userprofile".
    4. Поставьте галочки напротив пунктов: "Authenticate token requests via HTTP headers", "Show on login page".
4. Во вкладке "OAuth 2 services", справа от названия созданного Вами сервиса, нажмите на кнопку "Configure endpoints" и заполните полня:
    1. Name: "authorization_endpoint", URL: "https://id.trusted.plus/idp/sso/oauth/authorize".
    2. Name: "token_endpoint", URL: "https://id.trusted.plus/idp/sso/oauth/token".
    3. Name: "userinfo_endpoint", URL: "https://id.trusted.plus/trustedapp/rest/user/profile/get".
5. Во вкладке "OAuth 2 services", справа от названия созданного Вами сервиса, нажмите на кнопку "User field mappings":
    1. External field name: "data-givenName", Internal field name: "firstname". 
    2. External field name: "data-familyName", Internal field name: "lastname".
    3. External field name: "data-email", Internal field name: "email".
    4. External field name: "data-phone", Internal field name: "phone1".
    5. External field name: "data-login", Internal field name: "username".
6. Перейдите на вкладку "Site administration -> Plugins -> Authentication" и включите "OAuth 2", нажав на кнопку "Enable".
7. Во вкладке "OAuth 2 services" нажмите на кнопку "Connect to a system account" и пройдите авторизацию.

После выполнения всех действий на вашем портале moodle появится кнопка входа через ID.Trusted.Plus