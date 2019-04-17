### Endpoint Address

[https://thuat.ebaocloud.com/gi/webservice/seg/endorsement?wsdl](https://thuat.ebaocloud.com/gi/webservice/seg/endorsement?wsdl)

#### Cancel Method

- Input Parameter

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.segstd.ws.sp.gs.ebao.com/">
   <soapenv:Header/>
   <soapenv:Body>
      <ser:CancelPolicy>
         <Username>1110127664</Username>
         <Password>eBao1234</Password>    
         <Remark>cancel without reason</Remark>
         <PolicyNo>NVMI9000006185</PolicyNo>
         <Attachments>
            <!--Zero or more repetitions:-->
            <Attachment>
               <Name>id-card</Name>
               <Suffix>jpg</Suffix>
               <Type></Type>
               <Base64String>ignore</Base64String>
            </Attachment>
            <Attachment>
               <Name>old-policy-doc</Name>
               <Suffix>pdf</Suffix>
               <Type></Type>
               <Base64String>ignore</Base64String>
            </Attachment>
         </Attachments>
      </ser:CancelPolicy>
   </soapenv:Body>
</soapenv:Envelope>
```

| Data Name | Type | Optional | Sample | Description |
| --- | --- | :-: | :-: | :-: |
| username | String | M | 1110127664 |  |
| password | String | M | eBao1234 |  |
| policyNo| String | M |  NVMI9000006185 |  |
| remark | String | O | mistake | |
| attachments | Array| O | |list of 'Attachment'  |


|Attachment| Type| Optional| Sample| Description|
| --- | --- | :-: | :-: | :-: |
|name|String|M|id-card| The name of this document|
|suffix|String|O|jpg| |
|type|String|M|undefined| The business type of this document|
|base64String|String|M|ignore| Base64 encoded file |


- Return

```xml
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
      <ns2:CancelPolicyResponse xmlns:ns2="http://service.segstd.ws.sp.gs.ebao.com/">
         <CancelPolicyResult>
            <IsSuccess>true</IsSuccess>
            <EndorsementNo>E0000000199</EndorsementNo>
         </CancelPolicyResult>
      </ns2:CancelPolicyResponse>
   </soap:Body>
</soap:Envelope>
```

| Data Name | Type  | Optional |Sample | Description |
| --- | --- | :-: | :-: | :-: |
| IsSuccess |Boolean | M| true | A flag indicates whether this transaction is succeed or failed|
| EndorsementNo | String | C | E0000000199 | Endorsement serial number|
| Message | String | C | - | The reason of failure |

