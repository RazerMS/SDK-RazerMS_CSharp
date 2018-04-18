## Integrating MOLPay with C# SDK
Version 1.0.0

### Pre-Requisite
1. Visual Studio 2012 or above.
2. MOLPay Development or Production ID.
3. MOLPay General API.

### Installation
#### Via File Explorer
1. Download `MOLPay.dll` library.
2. Open Visual Studio project, right click on your project name in `Solution Explorer` and choose `Add Reference`.
3. Click `Browse` to search for downloaded library. Click `OK` to add.

### Usage
Create MOLPayVB object in order to access the properties of Base: 

```CSharp
MolPayCS.MOLPay object = new MolPayCS.MOLPay();
```
Set the values received from MOLPay's payment response
```CSharp
object.Vkey = "xxxxxxx"   'Replace ​xxxxxxxxxx with your MOLPay Secret_Key
object.TranID = String.Format("{0}", Request.Form["tranID"]);
object.Orderid = String.Format("{0}", Request.Form["orderid"]);
object.Status = String.Format("{0}", Request.Form["status"]);
object.MerchantID = String.Format("{0}", Request.Form["domain"]);
object.Amount = String.Format("{0}", Request.Form["amount"]);
object.Currency= String.Format("{0}", Request.Form["currency"]);
object.Paydate = String.Format("{0}", Request.Form["paydate"]);
object.Appcode = String.Format("{0}", Request.Form["appcode"]);
object.Skey = String.Format("{0}", Request.Form["skey"]);
```
Set which type of enviroment with either **Sandbox** or **Production**
```CSharp
object.Type = "sandbox" ' "sandbox" or "production"
```
### IPN(Instant Payment Notification)
Additional object must be set when using IPN
```CSharp
object.Treq = "1" 'Value is always 1. Do not change
```
Call the IPN function
```CSharp
object.IPN()
```
### Notification URL wtih IPN(Instant Payment Notification)
Set additional object for Notification URL 
```CSharp
object.Nbcb = String.Format("{0}", Request.Form["nbcb"]); 
```

### Sample of all 3 endpoints
`E.G` return & notification & callback URL

```CSharp
//invalid transaction if the key is different. Merchant might issue a requery to MOLPay to double check payment status with MOLPay. 
if (object.Skey != object.Key1checked())
    object.Status = "-1";
 
If status = "00" then  
 /*** NOTE : this is a user-defined function which should be prepared by merchant ***/
// action to change cart status or to accept order
// you can also do further checking on the paydate as well
// write your script here .....
Else
  // failure action. Write your script here .....
// Merchant might send query to MOLPay using Merchant requery
// to double check payment status for that particular order.
}
```


Support
-------

Merchant Technical Support / Customer Care : support@molpay.com <br>
Marketing Campaign : marketing@molpay.com <br>
Channel/Partner Enquiry : channel@molpay.com <br>
Media Contact : media@molpay.com <br>
R&D and Tech-related Suggestion : technical@molpay.com <br>
Abuse Reporting : abuse@molpay.com

Disclaimer
----------
Any amendment by your end is at your own risk.

Changelog
----------
1. 2018-04-18 - v1.0.0 - Initial Release
