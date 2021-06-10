<app-customer-layout></app-customer-layout>

<div style="background-color:cornsilk" class="container">
  <h1 style="text-align:center">Edit Profile</h1>
  <div style=" text-align:center;margin-left:20em">
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *All fileds are manadatory
  </div>
  &nbsp;&nbsp;&nbsp;
  <div class="row">
    <div class="col-md-4">
    </div>
   
    <div style="background-color:cornsilk" class="col-md-4">
      <form [formGroup]="registerForm" (ngSubmit)="editProfile(registerForm)">
        <div class="form-group">
          <label style="text-align:left">First Name</label>
          <br />
          <input type="text" class="form-control" formControlName="firstName">
          <p *ngIf="registerForm.controls.firstName.errors?.required &&  registerForm.controls.firstName.touched"
             style="color:red" class="alert alert-danger">&nbsp;This field is required!</p>
          <p *ngIf="registerForm.controls.firstName.errors?.pattern && registerForm.controls.firstName.touched "
             style="color:red" class="alert alert-danger">Only Alphabets are allowed!</p>
        </div>
        <br />
        <div class="form-group">
          <label style="text-align:left">Last name</label>
          <br />
          <input type="text" class="form-control" formControlName="lastName">
          <p *ngIf="registerForm.controls.lastName.errors?.required &&  registerForm.controls.lastName.touched"
             style="color:red" class="alert alert-danger">This field is required!</p>
          <p *ngIf="registerForm.controls.lastName.errors?.pattern &&  registerForm.controls.lastName.touched"
             style="color:red" class="alert alert-danger">Only Alphabets are allowed!</p>
        </div>
        <br />
        <div class="form-group">
          <label>Gender</label>&nbsp;&nbsp;&nbsp;
          <input type="radio" formControlName="gender" name="gender" value="M" id="M" />
          <label for="M">Male</label>&nbsp;&nbsp;&nbsp;
          <input type="radio" formControlName="gender" name="gender" value="F" id="F" />
          <label for="F">Female</label>
          <p *ngIf="registerForm.controls.gender.errors?.required &&  registerForm.controls.gender.touched"
             style="color:red" class="alert alert-danger">&nbsp;This field is required!</p>
        </div>
        <br />
        <div class="form-group">
          <label style="text-align:left">Contact number</label>
          <br />
          <input type="number" class="form-control" formControlName="contactNumber">
          <p *ngIf="registerForm.controls.contactNumber.errors?.required &&  registerForm.controls.contactNumber.touched"
             class="alert alert-danger" style="color:red">This field is required!</p>
          <p *ngIf="registerForm.controls.contactNumber.errors?.min  && registerForm.controls.contactNumber.touched"
             style="color:red" class="alert alert-danger">contact should be of minimum 10 digit!</p>
          <p *ngIf="registerForm.controls.contactNumber.errors?.max &&  registerForm.controls.contactNumber.touched"
             style="color:red" class="alert alert-danger">contact cannot have more than 10 digit!</p>
          <p *ngIf="registerForm.controls.contactNumber.errors?.pattern &&  registerForm.controls.contactNumber.touched"
             style="color:red" class="alert alert-danger">contact number can't start with zero!</p>
        </div>
        <br />

        <div class="form-group">
          <label style="text-align:left">Date of Birth</label>
          <br />
          <input type="date" class="form-control" formControlName="dateOfBirth">
          <p *ngIf="registerForm.controls.dateOfBirth.errors?.required &&  registerForm.controls.dateOfBirth.touched"
             class="alert alert-danger" style="color:red">This field is required!</p>
          <p *ngIf="registerForm.controls.dateOfBirth.errors?.dateError &&  registerForm.controls.dateOfBirth.touched"
             class="alert alert-danger" style="color:red">{{registerForm.controls.dateOfBirth.errors?.dateError.message}}</p>
        </div>
        <br />
        <div class="form-group">
          <label style="text-align:left">Address</label> &nbsp;
          <br />
          <textarea type="text" class="form-control" formControlName="address"></textarea>
          <p *ngIf="registerForm.controls.address.errors?.required &&  registerForm.controls.address.touched"
             class="alert alert-danger" style="color:red">This field is required!</p>
        </div>
        <br />
        <button type="submit" style="color:green">Update</button>
      </form>
    </div>
    <div class="col-md-4">
    </div>
  </div>
  <br />
</div>
