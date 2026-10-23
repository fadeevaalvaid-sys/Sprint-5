# Автотесты Stellar Burgers

Проект содержит UI-автотесты веб-приложения Stellar Burgers с использованием Selenium и pytest.

## Технологии

- Python
- Selenium WebDriver
- pytest
- Google Chrome

## Покрытые сценарии

### Регистрация
- Проверка ошибки при вводе короткого пароля.
- Проверка успешной регистрации с уникальными данными.

### Вход в аккаунт
- Вход через кнопку на главной странице.
- Вход через личный кабинет.
- Вход со страницы регистрации.
- Вход со страницы восстановления пароля.

### Личный кабинет
- Переход в личный кабинет.
- Выход из аккаунта.

### Конструктор
- Переход в конструктор по ссылке «Конструктор».
- Переход в конструктор по логотипу Stellar Burgers.
- Проверка раздела «Булки» по умолчанию.
- Проверка переключения между разделами «Булки», «Соусы» и «Начинки».

## Структура проекта

```text
Sprint_5/
├── tests/
│   ├── test_registration.py
│   ├── test_login.py
│   ├── test_personal_account.py
│   ├── test_constructor.py
│   ├── test_constructor_sections.py
│   └── test_logout.py
├── conftest.py
├── helpers.py
├── locators.py
├── requirements.txt
├── .gitignore
└── README.md
```

## Установка и запуск

### 1. Клонирование репозитория

```bash
git clone https://github.com/fadeevaalvaid-sys/Sprint-5.git
cd Sprint-5
```

### 2. Установка зависимостей

Рекомендуется использовать виртуальное окружение.

```bash
python -m venv .venv
```

Активация в Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Установка зависимостей:

```bash
python -m pip install -r requirements.txt
```

### 3. Настройка ChromeDriver

Для запуска тестов необходим установленный Google Chrome и совместимый ChromeDriver.

Путь к ChromeDriver указывается в файле `conftest.py`. При необходимости измени его на путь к ChromeDriver на своём компьютере.

### 4. Запуск тестов

Запуск всех тестов:

```bash
python -m pytest -v
```

Запуск тестов регистрации:

```bash
python -m pytest -v tests/test_registration.py
```

## Вспомогательные функции

В файле `helpers.py` находятся генераторы тестовых данных:

- `generate_email()` — создаёт уникальный email.
- `generate_password()` — генерирует случайный пароль.

Каждый тест использует отдельный экземпляр браузера. После завершения теста браузер закрывается с помощью `driver.quit()`, настроенного в фикстуре `driver` в файле `conftest.py`.
