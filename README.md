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
    	
	
