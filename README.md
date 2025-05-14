# Web-development-
Web development description 
# To Do List application 
#create , add new task and edit
#python code 


```
class Task:
    def __init__(self, title, description, priority):
        self.title = title
        self.description = description
        self.priority = priority
        self.completed = False

    def mark_as_completed(self):
        self.completed = True

    def __str__(self):
        status = "Completed" if self.completed else "Not Completed"
        return f"Title: {self.title}\nDescription: {self.description}\nPriority: {self.priority}\nStatus: {status}"

class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self):
        title = input("Enter task title: ")
        description = input("Enter task description: ")
        priority = input("Enter task priority (High/Medium/Low): ")
        task = Task(title, description, priority)
        self.tasks.append(task)
        print("Task added successfully!")

    def view_tasks(self):
        for i, task in enumerate(self.tasks, start=1):
            print(f"Task {i}:")
            print(task)
            print("------------------------")

    def mark_task_as_completed(self):
        task_number = int(input("Enter task number to mark as completed: ")) - 1
        if task_number >= 0 and task_number < len(self.tasks):
            self.tasks[task_number].mark_as_completed()
            print("Task marked as completed!")
        else:
            print("Invalid task number.")

    def edit_task(self):
        task_number = int(input("Enter task number to edit: ")) - 1
        if task_number >= 0 and task_number < len(self.tasks):
            task = self.tasks[task_number]
            task.title = input("Enter new title: ") or task.title
            task.description = input("Enter new description: ") or task.description
            task.priority = input("Enter new priority: ") or task.priority
            print("Task updated successfully!")
        else:
            print("Invalid task number.")

    def delete_task(self):
        task_number = int(input("Enter task number to delete: ")) - 1
        if task_number >= 0 and task_number < len(self.tasks):
            del self.tasks[task_number]
            print("Task deleted successfully!")
        else:
            print("Invalid task number.")

def main():
    todo_list = ToDoList()
    while True:
        print("1. Add Task")
        print("2. View Tasks")
        print("3. Mark Task as Completed")
        print("4. Edit Task")
        print("5. Delete Task")
        print("6. Exit")
        choice = input("Enter your choice: ")
        if choice == "1":
            todo_list.add_task()
        elif choice == "2":
            todo_list.view_tasks()
        elif choice == "3":
            todo_list.mark_task_as_completed()
        elif choice == "4":
            todo_list.edit_task()
        elif choice == "5":
            todo_list.delete_task()
        elif choice == "6":
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
``
