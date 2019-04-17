### Endpoint Address

[https://thuat.ebaocloud.com/gi/webservice/seg/vmi?wsdl](https://thuat.ebaocloud.com/gi/webservice/seg/vmi?wsdl)

### SendPolicy Method

Business Logic ignore. Please refer to [CMI SendPolicy Method](../cmi/send-policy.html#send-policy-business-logic)

- Input Parameter

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
  xmlns:ser="http://service.segstd.ws.sp.gs.ebao.com/">
  <soapenv:Header/>
  <soapenv:Body>
    <ser:SendPolicy>
      <username>TMBC</username>
      <password>eBao1234</password>
      <info>
        <PolNo/>
        <PolNoPmc>NVMI0000302514</PolNoPmc>
        <Barcode/>
        <taxInvoiceNoPmc>TIBK80164231</taxInvoiceNoPmc>
        <taxInvoiceNo/>
        <ReferenceNo></ReferenceNo>
        <PreviousPolNo></PreviousPolNo>
        <PreviousPolNoPmc></PreviousPolNoPmc>
        <CarSeat>4</CarSeat>
        <CarCC>5000</CarCC>
        <CarWeight>3</CarWeight>
        <CarCode>HO020017</CarCode>
        <CarRegistNo>1°®2601</CarRegistNo>
        <CarChassisNo>WPJPRHQUDH</CarChassisNo>
        <CarYear>2016</CarYear>
        <CarProvince>10</CarProvince>
        <CusPrefix>7</CusPrefix>
        <CusFname>haoran</CusFname>
        <CusLname>ye</CusLname>
        <CusId>3575622333172</CusId>
        <Email>naresak.h@segroup.co.th</Email>
        <CusType>P</CusType>
        <PersonType>?</PersonType>
        <CoperateType>2</CoperateType>
        <CoperateBranchCode>12345</CoperateBranchCode>
        <PersonNationalityCode>THA</PersonNationalityCode>
        <Addrs1>Add No 12</Addrs1>
        <CusTelNumber>0910191811</CusTelNumber>
        <CusPostCode>10200</CusPostCode>
        <BillPrice>6632.35</BillPrice>
        <BillStamp>36</BillStamp>
        <BillVat>621.50</BillVat>
        <BillPrm>7125.5</BillPrm>
        <EffectiveDate>20180629</EffectiveDate>
        <ExpireDate>20190629</ExpireDate>
        <ProvinceCode>10</ProvinceCode>
        <DistrictCode>01</DistrictCode>
        <SubDistrictCode>01</SubDistrictCode>
        <CampaignCode>PMP120FTM3</CampaignCode>
        <PathImage>          
          <ImageRQ>
            <Name>0</Name>
            <Type>0</Type>
            <Base64String>01</Base64String>
            <ByteArray>cid:1267861750934</ByteArray>
          </ImageRQ>
        </PathImage>
        <FlagCCTV>true</FlagCCTV>
        <PreferredLang>en_US</PreferredLang>
        <DirectDiscountRate></DirectDiscountRate>
        <DirectDiscountAmount></DirectDiscountAmount>
        <ISP14></ISP14>
      </info>
      <genaratePolNo>false</genaratePolNo>
      <genaratePDF>true</genaratePDF>
      <calculatePremium>true</calculatePremium>
    </ser:SendPolicy>
  </soapenv:Body>
</soapenv:Envelope>
```

The basic columns are similar with CMI SendPolicy Method.
Ignore.

| info | Type | Length | Optional | Sample | Description |
| --- | --- | --- | --- | --- | --- |
| PolNo | String | | C | - | CMI policy number |
| PolNoPmc | String | | C | - | VMI policy number |
| Barcode | String | | C | - | CMI barcode number |
| TaxInvoiceNoPmc | String | | C | - | VMI taxinvoice number |
| TaxInvoiceNo | String | | C | - | CMI taxinvoice number |
| ReferenceNo | String | | C | - | external reference number |
| PreviousPolNo | String | | C | - |CMI previousPolNo  |
| PreviousPolNoPmc | String | | C | - |   VMI previousPolNo|
| CarCode | String | 8 | M | HO020017 |model code|
| PersonType | Integer | 2 | M | 01 | Person type must be in (1, 2) |
| CampaignCode | String | | M | PMC210MC5 | Plan code provided by SEG |
| PathImage | Array | | C | - | if FlagCCTV is true, this field would be mandatory and must contain at least one **ImageRQ** element. |
| FlagCCTV | Boolean | | M | true | CCTV discount |
| PreferredLang | String |  | O | en_US | this value should be one of en_US and th_TH  |

For other missing columns, please refer to [CMI SendPolicy Method - Input Parameter](../cmi/send-policy.html#jump-to-cmi-input-desc).

| ImageRQ | Type | Length | Optional | Sample | Description |
| --- | --- | --- | --- | --- | --- |
| Name | String | | M | car-image | |
| Type | String | | M | jpeg | |
| Base64String | String | | M | ignore. | |



- Return

```xml
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
      <ns2:SendPolicyResponse xmlns:ns2="http://service.segstd.ws.sp.gs.ebao.com/">
         <SendPolicyResult>
            <IsSuccess>true</IsSuccess>
            <PolNoPmc>NVMI9000006185</PolNoPmc>
            <BillPrm>2901.69</BillPrm>
            <BillStamp>12</BillStamp>
            <BillVat>203.96</BillVat>
            <BillPrice>3117.65</BillPrice>
            <Errors/>
            <TablePDF>https://thtst.ebaocloud.com/gi/api/std/b2b/policies/print/allinone/1282566622</TablePDF>
         </SendPolicyResult>
      </ns2:SendPolicyResponse>
   </soap:Body>
</soap:Envelope>
```

Note: SendPolicy Response here is the same with that of CMI's, please refer to [CMI SendPolicy Method - Retrun](../cmi/send-policy.html#jump-to-cmi-resp-desc).