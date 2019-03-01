# ApiParser C#
C# class for using our company's API as part of the subscription.
<hr><br/>

## Installation
Install the [NuGet package](https://www.nuget.org/packages/ApiParser) from the package manager console:
```c#
Install-Package ApiParser -Version 1.1.11
```
<hr><br />

## How to use
1. Create instance from **ApiParser.NET.dll**
```csharp
ApiParser parser = new ApiParser("API_USERNAME", "API_TOKEN", "json");
```
2. Call method from ApiParser
```csharp
List<ContactFieldText> data = new List<ContactFieldText>();

int listid = 55;

ContactFieldText cont1 = new ContactFieldText();
cont1.fieldid = 150;
string[] value1 = new string[] { "Name" };
cont1.fieldvalue = value1;
cont1.rule = "OR";
data.Add(cont1);

ContactFieldText cont2 = new ContactFieldText();
cont2.fieldid = 151;
string[] value1 = new string[] { "Last Name" };
cont2.fieldvalue = value1;
data.Add(cont2);
        
object result = parser.GetSubscribersByCustomField(listid, data);
```
<hr><br />

## Changelog:
### _Differences between **v1.1.11** and **v1.2.1**_ 
#### New methods:

* **AddToOTMDocument**
>  *Definition:*
> ```csharp
> public string AddToOTMDocument(int listid = 0, int subscriberid = 0, string emailaddress = "", string mobile = "", string mobilePrefix = "", int fieldid = 0, Dictionary<string, object> values = null, string path = "")
> 
>```
<br/>

* **GetSubscribersByCustomField**
>  *Definition:*
> ```csharp
> public object GetSubscribersByCustomField(int listid = 0, List<ContactFieldText> data = null, bool activeonly = true, bool countonly = false, int limit = 1000, int offset = 0)
> 
>```
<br/>

### _Differences between **v1.1.10** and **v1.1.11**_ 
#### New methods:

* **GetTriggerSummary**
>  *Definition:*
> ```csharp
> public object GetTriggerSummary(int triggerid = 0, string from = "", string to = "")
> 
>```
<br/>

* **GetAutoresponderSummary**
>  *Definition:*
> ```csharp
> public object GetAutoresponderSummary(int autoresponderid = 0, string from = "", string to = "")
> 
>```
<br/>

### _Differences between **v1.1.9** and **v1.1.10**_ 
#### New methods:

* **GetSegmentSummary**
>  *Definition:*
> ```csharp
> public object GetSegmentSummary(int segmentid = 0, string from = "", string to = "")
> 
>```
<br/>

* **GetRulesForSegment**
>  *Definition:*
> ```csharp
> public object GetRulesForSegment(int segmentid = 0)
> 
>```
<br/>

* **EditNewsletter**
>  *Definition:*
> ```csharp
> public object EditNewsletter(int newsletterid = 0, string name = "", string subject = "")
> 
>```
<br/>

* **SetTriggerStatus**
>  *Definition:*
> ```csharp
> public object SetTriggerStatus(int triggerid = 0, bool status = false)
> 
>```
<br/>

* **SetAutoresponderStatus**
>  *Definition:*
> ```csharp
> public object SetAutoresponderStatus(int autoresponderid = 0, bool status = false)
> 
>```
<br/>

### _Differences between **v1.1.8** and **v1.1.9**_ 
<br/>
#### Method definition changed:

* **GetNewsletters**
>  *Previous:*
> ```csharp
> public object GetNewsletters(bool countOnly = false, bool getLastSentDetails = false, bool content = true, string afterCreateDate = "", string newsletterNameLike = "")
>```
>
>  *Now:*
> ```csharp
> public object GetNewsletters(bool countOnly = false, bool getLastSentDetails = false, bool content = true, string afterCreateDate = "", string newsletterNameLike = "", int limit = 100, int offset = 0)
>```
> * **Added:** limit & offset.
<br />


#### _New methods in **v1.1.9**_ 

* **SendSMS**
>  *Definition:*
> ```csharp
> public string SendSMS(int campaignid = 0, string subject = "", string text = "",  int subscriberid = 0, int listid = 0, string mobile = "", string mobilePrefix = "")
>```

<br />

* **GetSubscribersFromSegment**
>  *Definition:*
> ```csharp
> public object GetSubscribersFromSegment(int segmentid = 0, bool countonly = false, bool activeonly = true, int limit = 100, int offset = 0)
>```

<br />

* **ViewNewsletter**
>  *Definition:*
> ```csharp
> public object ViewNewsletter(int newsletterid = 0)
>```

<br />

* **GetTriggersForSegment**
>  *Definition:*
> ```csharp
> public object GetTriggersForSegment(int segmentid = 0)
>```

<br />
