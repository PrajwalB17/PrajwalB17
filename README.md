editProfile(firstName: string, lastName: string, gender: string, contactNumber: number,
        dateOfBirth: Date, address: string): Observable<boolean> {
        var customer: ICustomer;
        var emailId: string = sessionStorage.getItem('userName');
        customer = {
          EmailId: emailId, Password: null, FirstName: firstName, LastName: lastName,
         Gender: gender, ContactNumber: contactNumber, DateOfBirth: dateOfBirth, Address: address
       }
    console.log(customer)
    return this.http.put<boolean>('https://localhost:44322/api/user/EditUserProfile', customer).
      pipe(catchError(this.errorHandler));
  }
