# ApiParser C#
C# class for using our company's API as part of the subscription.
<hr><br/>

## Installation
Install the [NuGet package](https://www.nuget.org/packages/ApiParser) from the package manager console:
```c#
Install-Package ApiParser -Version 1.1.3
```
<hr><br />

## How to use
1. Create instance from **ApiParser.NET.dll**
```csharp
ApiParser parser = new ApiParser("API_USERNAME", "API_TOKEN", "json");
```
2. Call method from ApiParser
```csharp
parser.GetLists();
```
<hr><br />

## Changelog:
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

### _Differences between **v1.1** and **v1.1.9**_ 
#### New methods:

* **SendSMS**
>  *Definition:*
> ```csharp
> public string SendSMS(int campaignid = 0, string subject = "", string text = "",  int subscriberid = 0, int listid = 0, string mobile = "", string mobilePrefix = "")
> 
>```
<br/>

* **GetSubscribersFromSegment**
>  *Definition:*
> ```csharp
> public object GetSubscribersFromSegment(int segmentid = 0, bool countonly = false, bool activeonly = true, int limit = 100, int offset = 0)
> 
>```
<br/>

* **GetTriggersForSegment**
>  *Definition:*
> ```csharp
> public object GetTriggersForSegment(int segmentid = 0)
> 
>```
<br/>

* **ViewNewsletter**
>  *Definition:*
> ```csharp
> public object ViewNewsletter(int newsletterid = 0)
> 
>```
<br/>

#### Method definition changed:

* **GetNewsletters**
>  *Previous:*
> ```csharp
> public object GetNewsletters(bool countOnly = false, bool getLastSentDetails = false, bool content = true, string afterCreateDate = "", string newsletterNameLike = "")
>```
>  *Now:*
> ```csharp
> public object GetNewsletters(bool countOnly = false, bool getLastSentDetails = false, bool content = true, string afterCreateDate = "", string newsletterNameLike = "", int limit = 100, int offset = 0)
>```
> * **Added:** $limit & $offset.
<hr><br/>

### _Differences between **v1.0** and **v1.1**_ 

#### Renamed methods:
| Old name [v1.0] | New name [v1.1]|
| ------ | ------ |
| Create_List | CreateList |
| Update_List | UpdateList |
| Delete_List | DeleteList |
| Update_Subscriber | UpdateSubscriber |
| Delete_Subscriber | DeleteSubscriber |

<br/>

#### Method definition changed:

* **CopyNewsletter**
>  *Previous:*
> ```csharp
> public string CopyNewsletter(int newsletterid = 0, string newsletterName = "")
>```
>
>  *Now:*
> ```csharp
> public string CopyNewsletter(int newsletterid = 0, string newsletterName = "", string subject = "")
>```
> * **Added:** subject.
<br />

* **ActivateSubscriber**
>  *Previous:*
> ```csharp
> public string ActivateSubscriber(int[] listids = null, string emailaddress = "", string mobile = "", string mobile_prefix = "")
>```
>
>  *Now:*
> ```csharp
> public string ActivateSubscriber(string service = "", int listid = 0, string emailaddress = "", string mobile = "", string mobile_prefix = "", int subsbcriberid = 0)
>```
> * **Added:** service, subscriberid.
<br />

* **SaveSubscriberCustomField**
>  *Previous:*
> ```csharp
> public string SaveSubscriberCustomField(int subscriberid = 0, int fieldid = 0, string value = "", bool skipEmptyData = false)
>```
>
>  *Now:*
> ```csharp
> public string SaveSubscriberCustomField(int subscriberid = 0, ContactFieldText contactFields = null, bool skipEmptyData = false)
>```
> * **Added:** Contact field is object form ContactFieldText class.
<br />

* **UnsubscribeSubscriberEmail**
>  *Previous:*
> ```csharp
> public string UnsubscribeSubscriberEmail(string emailaddress = "", int listid = 0, int subscriberid = 0, bool skipcheck = false, string statType = "", int statid = 0)
>```
>
>  *Now:*
> ```csharp
> public string UnsubscribeSubscriberEmail(string emailaddress = "", int listid = 0, int subscriberid = 0, bool skipcheck = false, int statid = 0)
>```
> * **Removed:** statType.
<br />

* **GetBouncesByList**
>  *Previous:*
> ```csharp
> public object GetBouncesByList(int listid = 0, int start = 0, int perpage = 0, string bounce_type = "", string calendar_restrictions = "", bool count_only = false)
>```
>
>  *Now:*
> ```csharp
> public object GetBouncesByList(int listid = 0, bool count_only = false, string bounce_type = "", string searchType ="", string searchStartDate = "", string searchEndDate = "")
>```
> * **Added:** searchType, searchStartDate and searchEndDate.
<br />

* **GetUnsubscribesByList**
>  *Previous:*
> ```csharp
> public object GetUnsubscribesByList(int listid = 0, int start = 0, int perpage = 0, string calendar_restrictions = "", bool count_only = false)
>```
>
>  *Now:*
> ```csharp
> public object GetUnsubscribesByList(int listid = 0, bool count_only = false, string searchType = "", string searchStartDate = "", string searchEndDate = "")
>```
> * **Added:** searchType, searchStartDate and searchEndDate.
<br />


* **GetRecipients**
>  *Previous:*
> ```csharp
> public object GetRecipients(int statid = 0, string stats_type, bool count_only = false)
>```
>
>  *Now:*
> ```csharp
> public object GetRecipients(int statid = 0, bool count_only = false)
>```
> * **Removed:** stats_type.
<br />


* **GetSubscriberDetails**
>  *Previous:*
> ```csharp
>  public object GetSubscriberDetails(string emailaddress = "", int listid = 0)
>```
>
>  *Now:*
> ```csharp
> public object GetSubscriberDetails(int listid = 0, int subscriberid = 0, string emailaddress = "", string mobile = "", string mobile_prefix = "")
>```
> * **Added:** mobile, mobile_prefix, subscriberid.
<br />

* **UpdateSubscriber**
>  *Previous:*
> ```csharp
>  public string Update_Subscriber(int subscriberid = 0, string emailaddress = "", int listid = 0, List<ContactFieldText> contactFields = null)
>```
>
>  *Now:*
> ```csharp
> public string UpdateSubscriber(int listid = 0, int subscriberid = 0, string emailaddress = "", string mobile = "", string mobilePrefix = "", List<ContactFieldText> contactFields = null)
>```
> * **Added:** mobile, mobile_prefix.
<br />

* **ScheduleSendSMS**
>  *Previous:*
> ```csharp
> public string ScheduleSendSMS(int campaignid = 0, float hours = 0, int[] lists = null)
>```
>
>  *Now:*
> ```csharp
> public string ScheduleSendSMS(int campaignid = 0, int[] lists = null, float hours = 0)
>```
<br />

* **GetSubscribers**
>  *Previous:*
> ```csharp
> public object GetSubscribers(Dictionary<string, string> searchinfo = null, bool countonly = false)
> 
>```
>
>  *Now:*
> ```csharp
> public object GetSubscribers(Dictionary<string, string> searchinfo = null, bool countonly = false, int limit = 1000, int offset = 0)
> 
>```
> * **Added:** limit, offset..

#### _New methods in **v1.1**_ 

* **UnsubscribeSubscriberMobile**
>  *Definition:*
> ```csharp
> public string UnsubscribeSubscriberMobile(int listid = 0, string mobile = "", string mobilePrefix = "", int subscriberid = 0, bool skipcheck = false, int statid = 0);
>```

<br />

* **GetListSummary**
>  *Definition:*
> ```csharp
> public object GetListSummary(int listid = 0)
>```

<br />

* **CopyNewsletter**
>  *Definition:*
> ```csharp
> public string CopyNewsletter(int newsletterid = 0, string newsletterName = "")
>```

<br />

* **GetSubscribersUpdatedSince**
>  *Definition:*
> ```csharp
> public object GetSubscribersUpdatedSince(string date = "", int[] lists = null, int limit = 1000, int offset = 0)
>```

<br />
