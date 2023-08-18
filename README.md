GoLang
Introduction

Here we've provided a complete 3rd-party library (SDK) for Golang developers that covers both SOAP and REST webservices. Before using, make sure you have provided a valid account in Pars corporation.
معرفی

فراپیامک مجموعۀ کامل از متدهای اتصال به وب سرویس REST و SOAP این شرکت را برای توسعه دهندگان GoLang فراهم نموده. قبل از استفاده از این کتابخانه، نیاز به خرید پنل فراپیامک دارید
Installation

You can run the following go command to have it:

go get github.com/payamak-panel/go

Usage

This is the simple usage for both REST and SOAP APIs:

package main

import (
	"fmt"
	"github.com/payamak-panel/go"
)

func main() {
    // REST
    restClient = := farapayamak.InitRestClient("username", "password")
    sendSMSData := farapayamak.SendSMSRestModel{
        From: "5000xxx",
        To: "09123456789",
        Text: "message",
    }
    result, err := restClient.SendSMS(&sendSMSData)
    if err != nil {
        fmt.Println(err)
    }
    fmt.Printf("%+v\n", *result)
    fmt.Println(fmt.Sprintf("RetStatus is %d", result.RetStatus))

    // SOAP
    soapClient := farapayamak.InitSoapClient("username", "password")
    SendSimpleSMS2Data := farapayamak.SendSimpleSMS2SoapModel {
        To: "09123456789",
        From: "5000xxx",
        Text: "message",
        IsFlash: false,
    }
    result2, err := soapClient.SendSimpleSMS2(&SendSimpleSMS2Data)
    if err != nil {
        fmt.Println(err)
    }
    fmt.Printf("%+v\n", *result2)
}

REST or SOAP?

We support a small number of methods in REST against the SOAP web service that supports the entire ones.
REST Methods

We're currently supporting the following methods in REST web service:

restClient.SendSMS(model)
restClient.GetDeliveries2(model)
restClient.GetMessages(model)
restClient.GetCredit()
restClient.GetBasePrice()
restClient.GetUserNumbers()
restClient.BaseServiceNumber(model)

SOAP Methods

We support a wide range of methods in SOAP web service. They're scope separated. Let's review all the SOAP web service methods.
Send Web Service

soapClient.GetCredit()
soapClient.GetDeliveries(model)
soapClient.GetDeliveries3(model)
soapClient.GetSmsPrice(model)
soapClient.SendByBaseNumber(model)
soapClient.SendByBaseNumber2(model)
soapClient.SendByBaseNumber3(model)
soapClient.SendSimpleSMS(model)
soapClient.SendSimpleSMS2(model)
soapClient.SendSms(model)
soapClient.SendSms2(model)
soapClient.SendMultipleSMS(model)
soapClient.SendMultipleSMS2(model)

Receive Web Service

soapClient.ChangeMessageIsRead(model)
soapClient.GetInboxCount()
soapClient.GetLatestReceiveMsg(model)
soapClient.GetMessages(model)
soapClient.GetMessagesAfterID(model)
soapClient.GetMessagesFilterByDate(model)
soapClient.GetMessagesReceptions(model)
soapClient.GetMessagesWithChangeIsRead(model)
soapClient.GetOutBoxCount()
soapClient.RemoveMessages(model)

User Web Service

soapClient.AddUser(model)
soapClient.AddUserWithLocation(model)
soapClient.AddUserWithMobileNumber(model)
soapClient.AddUserWithMobileNumber2(model)
soapClient.AddUserWithUserNameAndPass(model)
soapClient.AuthenticateUser()
soapClient.ChangeUserCredit(model)
soapClient.DeductUserCredit(model)
soapClient.ForgotPassword(model)
soapClient.GetCities(model)
soapClient.GetEnExpireDate()
soapClient.GetExpireDate()
soapClient.GetProvinces()
soapClient.GetUserBasePrice(model)
soapClient.GetUserCredit(model)
soapClient.GetUserCredit2()
soapClient.GetUserDetails(model)
soapClient.GetUserIsExist(model)
soapClient.GetUserNumbers()
soapClient.GetUserTransactions(model)
soapClient.GetUserWallet()
soapClient.GetUserWalletTransaction(model)
soapClient.GetUsers()
soapClient.RemoveUser(model)

Voice Web Service

soapClient.SendBulkSpeechText(model)
soapClient.SendBulkVoiceSMS(model)
soapClient.UploadVoiceFile(model)

Contacts Web Service

soapClient.AddContact(model)
soapClient.AddContactEvents(model)
soapClient.AddGroup(model)
soapClient.ChangeContact(model)
soapClient.ChangeGroup(model)
soapClient.CheckMobileExistInContact(model)
soapClient.GetContactEvents(model)
soapClient.GetContacts(model)
soapClient.GetContactsByID(model)
soapClient.GetGroups()
soapClient.MergeGroups(model)
soapClient.RemoveContact(model)
soapClient.RemoveContactByContactID(model)
soapClient.RemoveGroup(model)

Schedule Web Service

soapClient.AddNewMultipleSchedule(model)
soapClient.AddNewUsance(model)
soapClient.AddSchedule(model)
soapClient.GetScheduleDetails(model)
soapClient.GetScheduleStatus(model)
soapClient.RemoveSchedule(model)

Bulk Web Service

soapClient.AddNumberBulk(moel)
soapClient.BulkReception(model)
soapClient.BulkReceptionCount(model)
soapClient.GetBulkDeliveries(model)
soapClient.GetBulkDeliveries2(model)
soapClient.GetBulkDetails(model)
