###User Stories
                                                           
 * A user can add a new task to the list
 
 ```text
$ ruby todo.rb add finish yesterday's challenges
```
 * A user can print out a numbered list of tasks

  ```text
 $ ruby todo.rb list
 ```

 * A user can delete a task by number
 ```text
 $ ruby todo.rb delete <task_id>
 ```

 * A user can indicate a task is completed
  ```text
  $ ruby todo.rb complete <task_id>
  ```

 


###Responsibilities

Responsibility                                               | How
-------------------------------------------------------------|----------------------
 * Design the schema 
    * in SQL Designer
 * Convert schema to Migration Objects  
```Ruby
class CreateTodoList < ActiveRecord::Migration
    * completed
    * line_number (prioirity field) 
    * task_description
    * Tags- hmmm, tags was an array, a separate "owned" table
```
 * Create Model objects 
 class Task < ActiveRecord::Base
 has_many :tags
 end

 * Add a task to a TODO list                        
    * controller gets user input
    * creates Task Model object and calls add on it
    
* List all the tasks on a TODO list                
    * 
    ```ruby
    Task.find_each do |task|
  #put into a string
end
```
Delete a particular task from a TODO list                                 
 * Complete a particular task on a TODO list                    
    * find the task using model objects
    * set the completed field to true
    * to to_s 
    
 * Parse the command-line arguments and take the appropriate action          
  * similar to previous code, perhaps can be refactored.
  

