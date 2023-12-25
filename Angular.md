
* Angular setup Angular version of 17
  step 1: google search github.com angular university
  
  step 2: github directory search angular form and click 
  
  step 3: click on master select first branch 
  
  step 4: download and npm install command  
  
  step 5 : npm run start run the angular version
  
  note: node.js version 18 required 
  
* angular material.ui use for angular for input box outline use appearance="outline"
 <mat-form-field appearance="outline">
 
 
* Angular ngform use 


	step1: #loginForm="ngForm"

	step2: login button (click)="login(loginForm)"

	step3: ts file inside Ex:
	login(loginForm: NgForm){
	console.log(loginForm.value)
	}

	step4: import ngform 

	note: check ngform import on not 
  
* what is ngModel and what is defination

  - ngModel is directive it bind value of thir property
  
  
* how to show ouput in keystroke on angular Eg.
 
  {{loginForm.value | json}}  

 
 * Ng Model value how to use output show in json Eg.
 
  - <input 
  ngModel
  #email="NgModel"
  />
  
  {{ email.value| json}}
  
 * Ng model value how to multiple input show thir value

 {{email.value+ ' '+ password.value | json}} 

 * how to check valid method get input ex 
   step 1:<input matInput type="email" name="email" ngModel #email="ngModel" placeholder="dfdf"  required> 
   
   {{ email.valid }}
  
  
  
  
