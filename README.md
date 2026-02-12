# Jac Todo App with AI & Priority Levels

**Name:** Anqi Dai
**UMID:** 47067350

## Project Description
This is a full-stack Todo application built using the **Jac** programming language. It features a persistent database, a reactive web frontend, and AI integration using `llama3.2:3b` via Ollama. 

The app allows users to:
- Add, list, toggle, and delete todos.
- Automatically categorize tasks using a local LLM (AI).
- Generate meal plans and shopping lists using AI.
- **[Custom Feature]** Assign and view Priority Levels for tasks.

## Custom Feature: Priority Levels
For the custom feature requirement, I implemented a **Priority System**. Users can now assign a "High", "Medium", or "Low" priority to each task. They are displayed in different colors.

### How it works:
1.  **UI:** A dropdown menu was added to the input area. The task list displays color-coded badges (Red for High, Yellow for Medium, Blue for Low).
2.  **Backend:** The data model was updated to store the priority field, and the Walkers were updated to handle the data transfer.

### Code Implementation:
* **Database (`main.jac`):** Modified `node Todo` to include `has priority: str = "Medium";`.
* **Backend Logic (`main.jac`):** Updated `walker:priv AddTodo` to accept a `priority` argument and store it. Updated `walker:priv ListTodos` to return this field.
* **Frontend Logic (`frontend.impl.jac`):** Updated `addTodo` implementation to pass the selected priority state to the backend.
* **Styling (`styles.css`):** Added CSS classes for `.priority-select` and dynamic classes `.priority-High/Medium/Low` for color coding.

## Prerequisites
* Python 3.10+
* Jac Cloud (`pip install jac-cloud`)
* Ollama running `llama3.2:3b`

## How to Install and Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AngieIsSleepy/jac-todo-app
    cd jac-todo-app
    ```

2.  **Install dependencies:**
    ```bash
    pip install jac-cloud jac-runtimes
    ```

3.  **Clean previous builds (Important):**
    ```bash
    jac clean
    ```

4.  **Run the application:**
    ```bash
    jac run main.jac
    ```

5.  **Access the App:**
    Open your browser and navigate to: `http://localhost:8000`
