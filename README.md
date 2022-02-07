
## [Mobile SDK] – RazerMS CSharp
<img src="https://user-images.githubusercontent.com/38641542/74423739-b4440a00-4e8b-11ea-8d95-016d25d26e87.jpg">



### Pre-Requisite
1. Visual Studio 2012 or above.
2. MOLPay Development or Production ID.
3. MOLPay General API.

### Installation Guidance
[Installation](https://github.com/RazerMS/CSharp-SDK/wiki/Installation-Guidance)



FAQ
----------
**1. Exception of type 'System.IO.FileLoadException' occurred**
1. Simply right-click the "References" folder and select "Manage NuGet Packages...".
2. Select the Browse tab.
3. In the search bar in the upper left type "Newtonsoft.Jason".
4. Click "Install" and you're done.

**OR**
1. Remove Newtonsoft.Jason on reference.



**2. If payment keep loading wont proceed**

If you are using c# webform **(aspx.cs file)** to set the value of Seamless Intergration, please make sure empty your **aspx** file except   the first line of the file. For example:
``
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Seamless.aspx.cs" Inherits="MolPayUI.Seamless_function" %>
``



Support
-------

Merchant Technical Support / Customer Care : support-sa@razer.com <br>
Marketing Campaign : marketing-sa@razer.com <br>
Channel/Partner Enquiry : channel-sa@razer.com <br>
Media Contact : media-sa@razer.com <br>
R&D and Tech-related Suggestion : technical-sa@razer.com <br>
Abuse Reporting : abuse-sa@razer.com

Disclaimer
----------
Any amendment by your end is at your own risk.

Changelog
----------
1. 2018-04-18 - v1.0.0 - Initial Release
2. 2018-04-24 - v1.1.0 - Add 5 requery method
3. 2018-04-26 - v1.2.0 - Add seamless integration, add a UI file inside seamlessintegration.zip
4. 2018-07-30 - v1.2.1 - Fix invalid production URL for certain function. `Payment Endpoin Integration`, Rename `Vkey` to `SecretKey`
