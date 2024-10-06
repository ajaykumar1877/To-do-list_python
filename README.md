# Simple To-Do List Application

# Define an empty list to store tasks
todo_list = []

# Function to display the menu options
def display_menu():
    print("\nTo-Do List Menu:")
    print("1. View To-Do List")
    print("2. Add a Task")
    print("3. Update a Task")
    print("4. Remove a Task")
    print("5. Exit")

# Function to view tasks
def view_tasks():
    if len(todo_list) == 0:
        print("\nYour To-Do List is empty.")
    else:
        print("\nYour To-Do List:")
        for i, task in enumerate(todo_list, 1):
            print(f"{i}. {task}")

# Function to add a task
def add_task():
    task = input("Enter the task you want to add: ")
    todo_list.append(task)
    print(f"Task '{task}' has been added to the list.")

# Function to update a task
def update_task():
    view_tasks()
    if len(todo_list) > 0:
        task_num = int(input("Enter the task number you want to update: "))
        if 1 <= task_num <= len(todo_list):
            new_task = input("Enter the new task: ")
            todo_list[task_num - 1] = new_task
            print(f"Task {task_num} has been updated to '{new_task}'.")
        else:
            print("Invalid task number.")

# Function to remove a task
def remove_task():
    view_tasks()
    if len(todo_list) > 0:
        task_num = int(input("Enter the task number you want to remove: "))
        if 1 <= task_num <= len(todo_list):
            removed_task = todo_list.pop(task_num - 1)
            print(f"Task '{removed_task}' has been removed from the list.")
        else:
            print("Invalid task number.")

# Main loop
while True:
    display_menu()
    choice = input("Choose an option (1-5): ")
    
    if choice == '1':
        view_tasks()
    elif choice == '2':
        add_task()
    elif choice == '3':
        update_task()
    elif choice == '4':
        remove_task()
    elif choice == '5':
        print("Exiting To-Do List application. Goodbye!")
        break
    else:
        print("Invalid choice. Please choose a valid option.")
