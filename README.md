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
 	
### Agenda : InputElement (placeholder) -> Dom Manipulations(removeChild(), classList.toggle() ) -> Js Built-in function ( alert() )
