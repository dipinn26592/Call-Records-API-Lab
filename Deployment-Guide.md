# Docs

#Summary 

The following is a step-by-step guide for using Azure Logic Apps to leverage the Microsoft Graph Call Records API to solve customer challenges using CDR information.  

Call Records API: https://docs.microsoft.com/en-us/graph/api/resources/callrecords-api-overview?view=graph-rest-beta 

Disclaimer 

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. in no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software. 

Lab Environment 

To follow this guide, you will need the following: 

Access to a tenant with paid Azure subscription associated to your O365 tenant where you can create Azure Application, Azure Logic Apps and Azure log analytics workspace. 

You will also need a valid Office 365 subscription which will be used to make and receive calls. 
 

High Level Overview 

In this solution we will create 2 logic Apps. The first one will be used to create\renew a webhook subscription, and the second one will be used to retrieve the call ID. 
