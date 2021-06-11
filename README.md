  CustCare(CustQuery: string, bookingId: number): Observable<boolean> {
    var Ccare: ICustCare;
    Ccare = {
      requestId: 0,
      bookingId: bookingId,
      queryStatus: "Assigned", custQuery: CustQuery
    }
    console.log( (bookingId))
    return this.http.post<boolean>('https://localhost:44322/api/user/AddCustomerCare', Ccare).pipe(catchError(this.errorHandler));
  }
