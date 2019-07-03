# ApiParser C#
C# class for using our company's API as part of the subscription.
<hr><br/>

## Installation
Install the [NuGet package](https://www.nuget.org/packages/ApiParser) from the package manager console:
```c#
Install-Package ApiParser -Version 1.2.6
```
<hr><br />

## How to use
1. Create instance from **ApiParser.NET.dll**
```csharp
ApiParser parser = new ApiParser("API_USERNAME", "API_TOKEN", "json");
```
2. Call method from ApiParser
```csharp
object responce = parser.GetCustomFields();
```
<hr><br />

## Changelog:
### _Differences between **v1.2.5** and **v1.2.6**_ 
#### New methods:

* **GetLeadScore**
>  *Definition:*
> ```csharp
> public object GetLeadScore(int subscriberid = 0)
> 
>```
<br/>

* **SetLeadScore**
>  *Definition:*
> ```csharp
> public object SetLeadScore(int subscriberid = 0, int? leadScore = null, string type = "add")
> 
>```

## Changelog:
### _Differences between **v1.2.4** and **v1.2.5**_ 
#### New method:

* **LoadCustomField**
>  *Definition:*
> ```csharp
>  public object LoadCustomField(int fieldid = 0, bool return_options = false, bool makeInstance = false)
> 
>```

#### Method condition changed:
* **GetCustomFields**
>  *Previous:*
> ```php
> public object GetCustomFields(int[] lists = null) 
>```
>  *Now:*
> ```php
> public object GetCustomFields(int[] lists = null) 
>```
> * **lists:** is not required.
<hr><br/>
  
### _Differences between **v1.2.3** and **v1.2.4**_ 
#### New methods:

* **GetNewsletterSummary**
>  *Definition:*
> ```csharp
> public object GetNewsletterSummary(int newsletterid = 0, int statid = 0, string from = "", string to = "")
> 
>```
<br/>

* **GetStatids**
>  *Definition:*
> ```csharp
> public object GetStatids(int listid = 0, int segmentid = 0, int campaignid = 0, string from = "", string to = "", int limit = 100, int offset = 0)
> 
>```
<br/>

* **GetSnapshots**
>  *Definition:*
> ```csharp
> public object GetSnapshots(int subscriberid = 0, int triggerid = 0, int autoresponderid = 0)
> 
>```
<br/>
  
### _Differences between **v1.2.2** and **v1.2.3**_ 
#### Method definition changed:

* **ResubscribeContact**
>  *Previous:*
> ```php
> public string ResubscribeContact(int listid = 0, string emailaddress = "", string mobileNumber = "", string mobilePrefix = "", bool add_to_autoresponders = false)
>```
>  *Now:*
> ```php
> public string ResubscribeContact(int listid = 0, string emailaddress = "", string mobileNumber = "", string mobilePrefix = "", bool add_to_autoresponders = false, List<ContactFieldText> contactFields = null, List<Dictionary<string, object>> otmValues = null)
>```
> * **Added:** contactFields and otmValues.
<hr><br/>

### _Differences between **v1.2.1** and **v1.2.2**_ 
#### New methods:

* **GetSegments**
>  *Definition:*
> ```csharp
> public object GetSegments(int listid = 0, bool count_subscribers = false, int limit = 1000, int offset = 0)
> 
>```
<br/>

* **GetTriggers**
>  *Definition:*
> ```csharp
> public object GetTriggers(int listid = 0, int limit = 1000, int offset = 0)
> 
>```
<br/>

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
