# JavaScript_Todos_Application

## Todos_Application-1
### Agenda : HTML input(CheckBox) -> HTML Elements(Label) -> Dom Manipulations(html for setAttributes)

#### Add Check Box Statically

	<input type="checkbox">

#### Add Label to CheckBox
	<input type="checkbox" id="checkid"> 
    	<label for="checkid">Graduated</label>

#### Create CheckBox Dynamically using JavaScript
	let checkboxElement = document.getElementById("input")
	checkboxElement.type="checkbox"
	checkboxElement.id="checkboxid"
	document.body.appendChild(checkboxElement)

 	let labelElement = document.getElementById("label")
	labelElement.htmlFor ="checkboxid"
	labelElement.textContent="Graduated"
	document.body.appendChild(labelElement)

 #### setAttribute() 
 	-> It allows to add attribute to the HTML element. if the attribute exists it will replace to that attribute
  	labelElement.setAttribute("for","checkboxid")
   
#####   1) Listing the all items in the List using for_of loop
 	A) let todosList = [
	    {text:"Learn HTMNL",uniqueNo:1},
     	    {text:"Learn CSS",uniqueNo:2},
	    {text:"Learn JavaScript",uniqueNo:3}]
     	   function createAndAppendTodo(todo){Dynamic JScode}
	   for (let each_item of todosList){
		createAndAppendTodo(each_item)
	   }
 	
### Agenda : InputElement (placeholder) -> Dom Manipulations(removeChild(), classList.toggle() ) -> Js Built-in function ( alert() )

#####   1) Fixing the Check box (When the user Clicks the particular Checkbox/list it must be click)
 	A) Add the UniqueId to the object in ther list & pass that uniqueId to InputElement and LabelElement
  			let checkboxId = "checkbox"+todo.uniqueNo
     			inputElement.id=checkboxId
			labelElement.setAttribute("for",checkboxId)

#####   2) How to Strick of the text when we are clicking the textBox
	Step-1)  Add required CSS to Strick the text
 		 (text-decoration: line-through;)
 	Srep-2)  Speciific uniqueId to each Label Element
  			let labelId = "label"+todo.uniqueNo
     			labelElement.id=labelId
  	Step-3)  Add Event-Listener to Check Boxes
   			inputElement.onclick = function(){
        			onToDoStatusChanged(checkboxId,labelId)
    			}
   	Step-4)  Check the Styles of the Label Element based on CheckBox Check
    			function onToDoStatusChanged(checkboxId,labelId){
			    let checkboxElement = document.getElementById(checkboxId)
			    let labelElement = document.getElementById(labelId)
			
			    //  if(checkboxElement.checked === true){
			    //     labelElement.classList.add("checked")
			    //  }
			    //  else{
			    //     labelElement.classList.remove("checked")
			    //  }
			
			    labelElement.classList.toggle('checked')
			}
    	

 	#### classList.toggle() 
	-> Adds a class if it's not present and removes it if it is present
 		element.classList.toggle("className");

##### 3) Delete the Todo item
	Step-1) Specify Id to each Todo Item
 			let todoId = "todo" + todo.uniqueNo
    			todoElement.id=todoId
 	Step-2) Add Event listener to Delete Icon
  			deleteIcon.onclick=function(){
            			onDeleteToDo(todoId)
    			}
  	Step-3) Delete Todo Item from the Todos Items Container
			function onDeleteToDo(todoId){
			    let todoElement = document.getElementById(todoId)
			    todoItemsContainer.removeChild(todoElement)
			}

	#####  removeChild() : It removes the Child Element from the Parent Element
 			todoItemsContainer.removeChild(todoElement)   

##### 4) Add new Todo item on UserInput
	Step-1) Add EventListenier to the Button
 			let addToDoButton = document.getElementById('addTodoButton');
			addToDoButton.onclick = function(){
			    onAddTodo()
			}
 	Step-2) Access User Input Value
  			function onAddTodo(){
			    let userInputElement = document.getElementById("todoUserInput");
			    let userInputValue = userInputElement.value
			    if(userInputValue === ""){
			        alert("Enter valid Index");
			        return;
			    }
			    todoCount = todoCount + 1;
			    let newTodo ={
			        text : userInputValue,
			        uniqueNo : todoCount
			    }
			
			    createAndAppendTodo(newTodo);
			}
  	Step-3) Create New Todo Item
   			let newTodo ={
			        text : userInputValue,
			        uniqueNo : todoCount
			    }

### Todos App Part-3 
### Agenda : Local Storage(getItem(),setItem()) -> Values(null) -> HTML Elements(textarea Element)

### Todos App Part-4
### Agenda : JSON(JSON.stringify(), JSON.parse()) 
##### Store the Todo List in Local Storage
	-> Add Save Button To the Todo App when we click on the Save Button, Todo List will Save in to Local Storage
 		<button class="button" id="saveTodoButton">Save</button>
   	-> Add Eventlistener to the save Button
    		let saveTodoButton = document.getElementById("saveTodoButton")
		saveTodoButton.onclick=function(){localStorage.setItem("todoList",JSON.stringify(todosList))}
  	-> Add the Function This FUnction Will convert the TodoList(String) to Object
   		function getTodoListFromLocalStorage(){
		    let StringifyTodoList = localStorage.getItem("todoList")
		    let parseTodoList = JSON.parse(StringifyTodoList)
		}
  	-> Delete the Todo List Because We have create the TodosList Locally(LocalStorage)
   	-> Add The New TodoItem to TodoList (Local Storage)
    		todosList.push(newTodo)

### Todos App Part-5
### Agenda : Delete the TodoItem(after Reload)
	-> We wnat to update the TodoList After thr Clicking the Delete Button
 			let deleteTodoItemIndex = todosList.findIndex(function(eachTodo){
			            let eachTodoId = "todo"+eachTodo.uniqueNo
			            
			            if(eachTodoId===todoId){
			                return true;
			            }
			            else{
			                return false;
			            }
			    })
    			todosList.splice(deleteTodoItemIndex,1)
       
 	
   			





