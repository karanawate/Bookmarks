
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



   ---------------------------
   
* how to form state class  use ngvalid and nginvalid property
{{ email.invalid }} bydefault true
{{email.valid }} bedefault false
{[email.untouched }} by default true
{{email.touched }} bye default false 

* how to form state class  of show errors in json
{{email.errors | json }}

* how to show only required in of any input of email Angular
<input type="text" required/>
<mat-error *ngIf="email.errors?.required">email is required</mat-error>

* angular in email property use email is not valid
<mat-error *ngIf="email.errors?.email">email is not valid</mat-error>


* max-lenth and actull lenth want in angular 
<mat-form-field>
        <input matInput type="email" name="email" ngModel email #email="ngModel" placeholder="dfdf" minlength="3"  required>
        <mat-error *ngIf="email.errors?.required">email is required</mat-error>
        <mat-error *ngIf="email.errors?.minlength">
          your email must have minimum {{ email.errors?.minlength.requiredLength }} chars,
          but it only has {{email.errors?.minlength.actualLength}}.
        </mat-error>
        <mat-error *ngIf="email.errors?.email">email is not valid</mat-error>
      </mat-form-field>
	  
	  ---------------------------------------------
  
  
  
  
