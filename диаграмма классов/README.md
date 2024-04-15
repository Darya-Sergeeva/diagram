### Отчет по диаграмме классов:

**Процесс генерации диаграммы:**
1. **Идентификация сущностей и их атрибутов:** Определение основных сущностей в системе и их характеристик.
2. **Создание диаграммы в PlantUML:**
   - В текстовом редакторе создан файл .puml.
   - С использованием ключевых слов PlantUML описаны классы и их атрибуты и методы.
3. **Проверка и доработка:** После создания диаграммы была проведена проверка на корректность и внесение необходимых корректировок.

**Подход к выполнению задания:**
1. **Определение сущностей:** Идентификация основных сущностей в системе и их атрибутов.
2. **Описание классов:** Создание классов для каждой сущности с указанием их атрибутов и методов.
3. **Создание диаграммы:** Внесение информации о классах, их атрибутах и методах в файл .puml.
4. **Проверка и коррекция:** Проверка диаграммы на корректность и соответствие требованиям.

**Программный код:**

```
@startuml
class Пользователь {
    -id: int
    -username: string
    -password: string
    +войтиВСистему(): void
    +создатьПроект(): Проект
    +создатьЗадачу(): Задача
    +просмотретьЗадачи(): void
    +выйтиИзСистемы(): void
}

class Проект {
    -id: int
    -название: string
    -описание: string
    +добавитьЗадачу(задача: Задача): void
    +получитьЗадачи(): Задача[]
}

class Задача {
    -id: int
    -название: string
    -описание: string
    -дата_создания: Date
    -срок_выполнения: Date
    -статус: string
    +изменитьНазвание(новоеНазвание: string): void
    +изменитьОписание(новоеОписание: string): void
    +изменитьСрок(новыйСрок: Date): void
    +изменитьСтатус(новыйСтатус: string): void
}

Пользователь --> Проект: создатьПроект()
Проект "1" --> "*" Задача: добавитьЗадачу()
@enduml

```

**Код диаграммы на языке java^**
```
public class User {
    private int id;
    private String username;
    private String password;
    
    public void login() {
        // Логика входа в систему
    }
    
    public Project createProject() {
        // Логика создания проекта
        return new Project();
    }
    
    public Task createTask() {
        // Логика создания задачи
        return new Task();
    }
    
    public void viewTasks() {
        // Логика просмотра задач
    }
    
    public void logout() {
        // Логика выхода из системы
    }
}

public class Project {
    private int id;
    private String name;
    private String description;
    private List<Task> tasks;
    
    public Project() {
        tasks = new ArrayList<>();
    }
    
    public void addTask(Task task) {
        // Логика добавления задачи в проект
        tasks.add(task);
    }
    
    public List<Task> getTasks() {
        // Логика получения списка задач
        return tasks;
    }
}

public class Task {
    private int id;
    private String name;
    private String description;
    private Date creationDate;
    private Date deadline;
    private String status;
    
    public void changeName(String newName) {
        // Логика изменения названия задачи
        this.name = newName;
    }
    
    public void changeDescription(String newDescription) {
        // Логика изменения описания задачи
        this.description = newDescription;
    }
    
    public void changeDeadline(Date newDeadline) {
        // Логика изменения срока выполнения задачи
        this.deadline = newDeadline;
    }
    
    public void changeStatus(String newStatus) {
        // Логика изменения статуса задачи
        this.status = newStatus;
    }
}

```


**Диаграмма классов:**
![image](https://github.com/Darya-Sergeeva/diagram-/assets/79162305/654d548c-f6ae-4efb-9358-152b88cc515b)
