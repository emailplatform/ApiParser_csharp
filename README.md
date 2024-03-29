# ApiParser C#
C# class for using our company's API as part of the subscription.
<hr><br/>

## Installation
Install the [NuGet package](https://www.nuget.org/packages/ApiParser) from the package manager console:
```c#
Install-Package ApiParser -Version 1.2.21
```
<hr><br />

## How to use
1. Create instance from **ApiParser.NET.dll**
```csharp
ApiParser parser = new ApiParser("API_USERNAME", "API_TOKEN", "json");
```
2. Call method from ApiParser

```csharp
int campaignid = 278;
float hours = 1;

object response = parser.ScheduleSendSMS(campaignid, hours);
```
<hr><br />

## Changelog:

### _Differences between **v1.2.20** and **v1.2.21**_ 
<br>

#### Method definition changed:

* **ScheduleSendSMS**
>  *Previous:*
> ```csharp
> public string ScheduleSendSMS(int campaignid = 0, int[] lists = null, float hours = 0)
>```
>  *Now:*
> ```csharp
> public string ScheduleSendSMS(int campaignid = 0, float hours = 0)
>```
> * **Removed:** lists.
<br>

#### Removed method:

* **SendSMS**
> ```csharp
> public string SendSMS(int campaignid = 0, string subject = "", string text = "", int subscriberid = 0, int listid = 0, string mobile = "", string mobilePrefix = "")
>```
<br>

### _Differences between **v1.2.18** and **v1.2.20**_ 
#### New method:

* **RemoveOTMDocument**
> ```csharp
> public string RemoveOTMDocument(int subscriberid = 0, int fieldid = 0, string path = "", int index = 0)
>```
<br>

### _Differences between **v1.2.17** and **v1.2.18**_ 
#### New methods:

* **CreateSubAccount**
> ```csharp
> public string CreateSubAccount(string accountName = "", string accountPassword = "", string ownerEmail = "", string[] allowedDomains = null)
>```
<br>

* **InheritListsToSubAccount**
> ```csharp
> public string InheritListsToSubAccount(string accountName = "", int[] inheritLists = null)
>```
<br>

* **InheritSegmentsToSubAccount**
> ```csharp
> public string InheritSegmentsToSubAccount(string accountName = "", int[] inheritSegments = null)
>```
<br>

* **InheritNewsletterToSubAccount**
> ```csharp
> public string InheritNewsletterToSubAccount(string accountName = "", int newsletterid = 0, string recipientsType = "", int[] recipientsid = null)
>```
<br>

### _Differences between **v1.2.16** and **v1.2.17**_ 
<br>

#### Method definition changed:

* **UpdateOTMDocument**
>  *Previous:*
> ```csharp
> public string UpdateOTMDocument(int subscriberid = 0, int fieldid = 0, Dictionary<string, object> values = null, string path = "");
>```
>  *Now:*
> ```csharp
> public string UpdateOTMDocument(int subscriberid = 0, int listid = 0, string emailaddress = "", string mobileNumber = "", string mobilePrefix = "", int fieldid = 0, Dictionary<string, object> values = null, string path = "");
>```
> * **Added:** listid, emailaddress, mobileNumber and mobilePrefix.
<br>

### _Differences between **v1.2.15** and **v1.2.16**_ 
<br>

#### Method definition changed:

* **GetSubscriberDetails**
>  *Previous:*
`listid was required.`

>  *Now:*
`listid is not required if subscriberid is specified.`

### _Differences between **v1.2.14.2** and **v1.2.15**_ 
#### New methods:

* **UpdateOTMDocument**
> ```csharp
> public string UpdateOTMDocument(int subscriberid = 0, int fieldid = 0, Dictionary<string, object> values = null, string path = "")
>```
<br>

* **RemoveOTMDocument**
> ```csharp
>  public string RemoveOTMDocument(int subscriberid = 0, int fieldid = 0, string path = "", int index = 0)
>```
<br>

#### Method definition changed:

* **SendNewsletter**
>  *Previous:*
> ```csharp
> public string SendNewsletter(int newsletterid = 0, int subscriberid = 0, string email = "", string senderEmail = "", string senderName = "", string replyEmail = "", string callbackUrl = "", bool reloadFeed = false)
>```
>  *Now:*
> ```csharp
> public string SendNewsletter(int newsletterid = 0, int subscriberid = 0, string email = "", string senderEmail = "", string senderName = "", string replyEmail = "", string callbackUrl = "", bool reloadFeed = false, bool notifyOwner = false)
>```
> * **Added:** notifyOwner
<br>

* **ScheduleSendNewsletter**
>  *Previous:*
> ```csharp
> public string ScheduleSendNewsletter(int campaignid = 0, float hours = 0, bool saveSnapshots = true, bool reloadFeed = true)
>```
>  *Now:*
> ```csharp
> public string ScheduleSendNewsletter(int campaignid = 0, float hours = 0, bool saveSnapshots = true, bool reloadFeed = true, bool notifyOwner = false)
>```
> * **Added:** notifyOwner
<br>

* **ScheduleSendNewsletterToLists**
>  *Previous:*
> ```csharp
>  public string ScheduleSendNewsletterToLists(int campaignid = 0, float timeToSend = 0, int[] listids = null, bool saveSnapshots = true, bool reloadFeed = true)
>```
>  *Now:*
> ```csharp
>  public string ScheduleSendNewsletterToLists(int campaignid = 0, float timeToSend = 0, int[] listids = null, bool saveSnapshots = true, bool reloadFeed = true, bool notifyOwner = false)
>```
> * **Added:** notifyOwner
<br>

* **ScheduleSendNewsletterToSegments**
>  *Previous:*
> ```csharp
>  public string ScheduleSendNewsletterToSegments(int campaignid = 0, float timeToSend = 0, int[] segmentids = null, bool saveSnapshots = true, bool reloadFeed = true)
>```
>  *Now:*
> ```csharp
>  public string ScheduleSendNewsletterToSegments(int campaignid = 0, float timeToSend = 0, int[] segmentids = null, bool saveSnapshots = true, bool reloadFeed = true, bool notifyOwner = false)
>```
> * **Added:** notifyOwner
<br>

### _Differences between **v1.2.14.1** and **v1.2.14.2**_ 
#### Method result changed:

* **GetStatids**
> ```csharp
> public object GetStatids(int listid = 0, int segmentid = 0, int campaignid = 0, string from = "", string to = "", int limit = 100, int offset = 0)
>```
<br>

### _Differences between **v1.2.14** and **v1.2.14.1**_ 
#### New method:

* **GetSampleDataForOTM**
> ```csharp
> public object GetSampleDataForOTM(int fieldid = 0)
>```
<br>

### _Differences between **v1.2.13** and **v1.2.14**_ 
#### Method definition changed:

* **ScheduleSendNewsletter**
>  *Previous:*
> ```csharp
> public string ScheduleSendNewsletter(int campaignid = 0, float hours = 0, bool saveSnapshots = true)
>```
>  *Now:*
> ```csharp
> public string ScheduleSendNewsletter(int campaignid = 0, float hours = 0, bool saveSnapshots = true, bool reloadFeed = true)
>```
> * **Added:** reloadFeed
<br>

* **ScheduleSendNewsletterToLists**
>  *Previous:*
> ```csharp
> public function ScheduleSendNewsletterToLists(int campaignid = 0, float timeToSend = 0, int[] listids = null)
>```
>  *Now:*
> ```csharp
> public function ScheduleSendNewsletterToLists(int campaignid = 0, float timeToSend = 0, int[] listids = null, bool saveSnapshots = true, bool reloadFeed = true)
>```
> * **Added:** saveSnapshots and reloadFeed
<br>

* **ScheduleSendNewsletterToSegments**
>  *Previous:*
> ```csharp
> public function ScheduleSendNewsletterToSegments(int campaignid = 0, float timeToSend = 0, int[] segmentids = null)
>```
>  *Now:*
> ```csharp
> public function ScheduleSendNewsletterToSegments(int campaignid = 0, float timeToSend = 0, int[] segmentids = null, bool saveSnapshots = true, bool reloadFeed = true)
>```
> * **Added:** saveSnapshots and reloadFeed
<br>

### _Differences between **v1.2.12** and **v1.2.13**_ 
#### New method:

* **CreateSegment**
> ```csharp
> public string CreateSegment(string name = "", Dictionary<string, object> rules = null, string connector = "and")
>```
<br>

### _Differences between **v1.2.11** and **v1.2.12**_ 
#### New method:

* **AddCustomFieldsToList**
> ```csharp
> public string AddCustomFieldsToList(int listid = 0, int[] customFields = null)
>```
<br>


### _Differences between **v1.2.10** and **v1.2.11**_ 
#### Method definition changed:

* **SendNewsletter**
>  *Previous:*
> ```csharp
> public string SendNewsletter(int newsletterid = 0, int subscriberid = 0, string email = "", string senderEmail = "", string senderName = "", string replyEmail = "")
>```
>  *Now:*
> ```csharp
>public string SendNewsletter(int newsletterid = 0, int subscriberid = 0, string email = "", string senderEmail = "", string senderName = "", string replyEmail = "", string callbackUrl = "", bool reloadFeed = false)
>```
> * **Added:** callbackUrl and reloadFeed
<br>

### _Differences between **v1.2.9** and **v1.2.10**_ 
#### New methods:

* **ScheduleSendNewsletterToLists**
>  *Definition:*
> ```csharp
> public string ScheduleSendNewsletterToLists(int campaignid = 0, float hours = 0, int[] listids = null)
> 
>```

* **ScheduleSendNewsletterToSegments**
>  *Definition:*
> ```csharp
> public string ScheduleSendNewsletterToSegments(int campaignid = 0, float hours = 0, int[] segmentids = null)
> 
>```

### _Differences between **v1.2.8** and **v1.2.9**_ 
#### Method definition changed:

* **ScheduleSendNewsletter**
>  *Previous:*
> ```csharp
> public string ScheduleSendNewsletter(int campaignid = 0, float hours = 0)
>```
>  *Now:*
> ```csharp
> public string ScheduleSendNewsletter(int campaignid = 0, float hours = 0, bool saveSnapshots = true)
>```
> * **Added:** saveSnapshots
<br>

#### New methods:

* **GetSentEmailCampaignEvents**
>  *Definition:*
> ```csharp
> public string GetSentEmailCampaignEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetSentEmailCampaignWithTriggerEvents**
>  *Definition:*
> ```csharp
> public string GetSentEmailCampaignWithTriggerEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetOpenCampaignEvents**
>  *Definition:*
> ```csharp
> public string GetOpenCampaignEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetOpenTriggersEvents**
>  *Definition:*
> ```csharp
> public string GetOpenTriggersEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetLinkClickCampaignEvents**
>  *Definition:*
> ```csharp
> public string GetLinkClickCampaignEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetLinkClickTriggersEvents**
>  *Definition:*
> ```csharp
> public string GetLinkClickTriggersEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetSentAutoresponderEvents**
>  *Definition:*
> ```csharp
> public string GetSentAutoresponderEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetOpenAutoresponderEvents**
>  *Definition:*
> ```csharp
> public string GetOpenAutoresponderEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetLinkClickAutoresponderEvents**
>  *Definition:*
> ```csharp
> public string GetLinkClickAutoresponderEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```

* **GetSentSMSCampaignEvents**
>  *Definition:*
> ```csharp
> public string GetSentSMSCampaignEvents(string from = "", string to = "", int limit = 10, int offset = 0)
> 
>```
<hr><br>

### _Differences between **v1.2.7** and **v1.2.8**_ 
#### Update on memory objects:
<hr><br>

### _Differences between **v1.2.6** and **v1.2.7**_ 
#### New method:

* **GetTrackingEvents**
>  *Definition:*
> ```csharp
> public object GetTrackingEvents(int listid = 0, int subscriberid = 0, int limit = 100, int offset = 0)
> 
>```
<hr><br>

### _Differences between **v1.2.5** and **v1.2.6**_ 
#### New methods:

* **GetLeadScore**
>  *Definition:*
> ```csharp
> public object GetLeadScore(int subscriberid = 0)
> 
>```
<br>

* **SetLeadScore**
>  *Definition:*
> ```csharp
> public object SetLeadScore(int subscriberid = 0, int? leadScore = null, string type = "add")
> 
>```
<hr><br>

### _Differences between **v1.2.4** and **v1.2.5**_ 
#### New method:

* **LoadCustomField**
>  *Definition:*
> ```csharp
>  public object LoadCustomField(int fieldid = 0, bool return_options = false, bool makeInstance = false)
> 
>```
<br>

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
<hr><br>
  
### _Differences between **v1.2.3** and **v1.2.4**_ 
#### New methods:

* **GetNewsletterSummary**
>  *Definition:*
> ```csharp
> public object GetNewsletterSummary(int newsletterid = 0, int statid = 0, string from = "", string to = "")
> 
>```
<br>

* **GetStatids**
>  *Definition:*
> ```csharp
> public object GetStatids(int listid = 0, int segmentid = 0, int campaignid = 0, string from = "", string to = "", int limit = 100, int offset = 0)
> 
>```
<br>

* **GetSnapshots**
>  *Definition:*
> ```csharp
> public object GetSnapshots(int subscriberid = 0, int triggerid = 0, int autoresponderid = 0)
> 
>```
<hr><br>
  
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
<hr><br>

### _Differences between **v1.2.1** and **v1.2.2**_ 
#### New methods:

* **GetSegments**
>  *Definition:*
> ```csharp
> public object GetSegments(int listid = 0, bool count_subscribers = false, int limit = 1000, int offset = 0)
> 
>```
<br>

* **GetTriggers**
>  *Definition:*
> ```csharp
> public object GetTriggers(int listid = 0, int limit = 1000, int offset = 0)
> 
>```
<hr><br>

### _Differences between **v1.1.11** and **v1.2.1**_ 
#### New methods:

* **AddToOTMDocument**
>  *Definition:*
> ```csharp
> public string AddToOTMDocument(int listid = 0, int subscriberid = 0, string emailaddress = "", string mobile = "", string mobilePrefix = "", int fieldid = 0, Dictionary<string, object> values = null, string path = "")
> 
>```
<br>

* **GetSubscribersByCustomField**
>  *Definition:*
> ```csharp
> public object GetSubscribersByCustomField(int listid = 0, List<ContactFieldText> data = null, bool activeonly = true, bool countonly = false, int limit = 1000, int offset = 0)
> 
>```
<hr><br>

### _Differences between **v1.1.10** and **v1.1.11**_ 
#### New methods:

* **GetTriggerSummary**
>  *Definition:*
> ```csharp
> public object GetTriggerSummary(int triggerid = 0, string from = "", string to = "")
> 
>```
<br>

* **GetAutoresponderSummary**
>  *Definition:*
> ```csharp
> public object GetAutoresponderSummary(int autoresponderid = 0, string from = "", string to = "")
> 
>```
<hr><br>

### _Differences between **v1.1.9** and **v1.1.10**_ 
#### New methods:

* **GetSegmentSummary**
>  *Definition:*
> ```csharp
> public object GetSegmentSummary(int segmentid = 0, string from = "", string to = "")
> 
>```
<br>

* **GetRulesForSegment**
>  *Definition:*
> ```csharp
> public object GetRulesForSegment(int segmentid = 0)
> 
>```
<br>

* **EditNewsletter**
>  *Definition:*
> ```csharp
> public object EditNewsletter(int newsletterid = 0, string name = "", string subject = "")
> 
>```
<br>

* **SetTriggerStatus**
>  *Definition:*
> ```csharp
> public object SetTriggerStatus(int triggerid = 0, bool status = false)
> 
>```
<br>

* **SetAutoresponderStatus**
>  *Definition:*
> ```csharp
> public object SetAutoresponderStatus(int autoresponderid = 0, bool status = false)
> 
>```
<hr><br>

### _Differences between **v1.1.8** and **v1.1.9**_ 
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
<br>

#### New methods:

* **SendSMS**
>  *Definition:*
> ```csharp
> public string SendSMS(int campaignid = 0, string subject = "", string text = "",  int subscriberid = 0, int listid = 0, string mobile = "", string mobilePrefix = "")
>```
<br>

* **GetSubscribersFromSegment**
>  *Definition:*
> ```csharp
> public object GetSubscribersFromSegment(int segmentid = 0, bool countonly = false, bool activeonly = true, int limit = 100, int offset = 0)
>```
<br>

* **ViewNewsletter**
>  *Definition:*
> ```csharp
> public object ViewNewsletter(int newsletterid = 0)
>```
<br>

* **GetTriggersForSegment**
>  *Definition:*
> ```csharp
> public object GetTriggersForSegment(int segmentid = 0)
>```
<br>
