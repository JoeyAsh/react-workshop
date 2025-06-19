### User Stories for Task Management App

#### User Story 1: Add Task
**As a** user, **I want** to add new tasks with a title and description, **so that** I can keep track of my to-dos.

**Acceptance Criteria:**
1. The user can open a form to add a new task.
2. The form includes fields for the task title and description.
3. The user can submit the form to add the task.
4. The new task appears in the task list upon submission.
5. The new task should be manually added to the rtk query cache.

#### User Story 2: Edit Task
**As a** user, **I want** to edit existing tasks, **so that** I can update the task details if needed.

**Acceptance Criteria:**
1. The user can open a form to edit an existing task.
2. The form is pre-filled with the current task details.
3. The user can update the task title.
4. The user can submit the form to save changes.
5. The updated task appears in the task list upon submission.
6. The updated task should be manually updated in the rtk query cache.

#### User Story 3: Delete Task
**As a** user, **I want** to delete tasks, **so that** I can remove tasks that are no longer needed.

**Acceptance Criteria:**
1. The user can delete a task from the task list.
2. A confirmation prompt appears before deletion.
3. The task is removed from the task list upon confirmation.
4. The deleted task should be manually removed from the rtk query cache.

#### User Story 4: Mark Task as Completed
**As a** user, **I want** to mark tasks as completed, **so that** I can see which tasks are done.

**Acceptance Criteria:**
1. The user can mark a task as completed.
2. The completed task is visually distinct from pending tasks.
3. The task list updates to reflect the completed status.
4. The completed status should be manually updated in the rtk query cache.

#### User Story 5: Filter Tasks
**As a** user, **I want** to filter tasks by all, completed, and pending, **so that** I can easily find tasks based on their status.

**Acceptance Criteria:**
1. The user can filter tasks to show all, completed, or pending tasks.
2. The task list updates to show only the tasks that match the selected filter.
3. The filter state is saved in a slice.

### User Story 6: Sort Tasks
**As a** user, **I want** to sort tasks in ascending or descending order, **so that** I can organize my tasks based on their titles.

**Acceptance Criteria:**
1. The user can choose to sort tasks in ascending or descending order.
2. The task list updates to reflect the selected sort order.
3. The sort order is saved in use context.


### User Story 7: Navigation Sidebar
**As a** user, **I want** to have a navigation sidebar, **so that** I can easily access different sections of the application.

**Acceptance Criteria:**
1. The sidebar should display a list of navigation items.
2. Each navigation item should have an icon and a title.
3. The user can click on a navigation item to navigate to the corresponding section.
4. The sidebar should be visually distinct and accessible from all pages.
5. The sidebar should be collapsible to save screen space.
6. The sidebar should include the following navigation items:
    - Dashboard
    - Tasks
    - Posts
    - Page not found

### User Story 8: Task List
**As a** user, **I want** to view a list of tasks, **so that** I can see all my tasks in one place.

**Acceptance Criteria:**
1. The task list should display all tasks with their titles and descriptions.
2. Each task should have an option to mark it as completed.
3. Each task should have an option to edit or delete it.
4. The task list should be paginated if there are many tasks.
5. The task list should update in real-time as tasks are added, edited, or deleted.

### User Story 9: Display Todo Details
**As a** user, **I want** to view the details of a specific todo, **so that** I can see all the information related to that todo.

**Acceptance Criteria:**
1. The user can click on a todo item to view its details.
2. The details view should display the todo's title, description, creation date, and status.
3. The details view should be accessible from the task list.
4. The user can navigate back to the task list from the details view.

### User Story 10: Breadcrumb Navigation
**As a** user, **I want** to have breadcrumb navigation, **so that** I can easily understand my current location within the application and navigate back to previous sections.

**Acceptance Criteria:**
1. The breadcrumb should display the current path as a series of links.
2. Each segment of the breadcrumb should be clickable, allowing navigation to that section.
3. The breadcrumb should update dynamically based on the current route.
4. The breadcrumb should be visually distinct and accessible from all pages.
5. The breadcrumb should include a home icon as the first segment.

### User Story 11: Search Bar
**As a** user, **I want** to have a search bar, **so that** I can quickly find specific tasks by their titles.

**Acceptance Criteria:**
1. The search bar should be prominently displayed on the task list page.
2. The user can type keywords into the search bar to filter tasks.
3. The task list should update in real-time to show only tasks that match the search keywords.
4. The search should be case-insensitive.
5. The search bar should have a clear button to reset the search and display all tasks.