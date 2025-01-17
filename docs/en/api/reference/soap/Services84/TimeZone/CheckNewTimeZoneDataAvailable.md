---
title: Services84.TimeZoneAgent.CheckNewTimeZoneDataAvailable SOAP
generated: 1
uid: Services84-TimeZone-CheckNewTimeZoneDataAvailable
---

# Services84 TimeZone CheckNewTimeZoneDataAvailable

SOAP request and response examples **Remote/Services84/TimeZone.svc**
Implemented by the <see cref="M:SuperOffice.Services84.ITimeZoneAgent.CheckNewTimeZoneDataAvailable">SuperOffice.Services84.ITimeZoneAgent.CheckNewTimeZoneDataAvailable</see> method.

## CheckNewTimeZoneDataAvailable





[WSDL file for Services84/TimeZone](../Services84-TimeZone.md)

Obtain a ticket from the [Services84/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## CheckNewTimeZoneDataAvailable Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:TimeZone="http://www.superoffice.net/ws/crm/NetServer/Services84">
  <TimeZone:ApplicationToken>1234567-1234-9876</TimeZone:ApplicationToken>
  <TimeZone:Credentials>
    <TimeZone:Ticket>7T:1234abcxyzExample==</TimeZone:Ticket>
  </TimeZone:Credentials>
 <SOAP-ENV:Body>
   <TimeZone:CheckNewTimeZoneDataAvailable>
   </TimeZone:CheckNewTimeZoneDataAvailable>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## CheckNewTimeZoneDataAvailable Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:TimeZone="http://www.superoffice.net/ws/crm/NetServer/Services84">
 <SOAP-ENV:Body>
  <TimeZone:CheckNewTimeZoneDataAvailableResponse>
   <TimeZone:Response xsi:type="xsd:boolean">false</TimeZone:Response>
  </TimeZone:CheckNewTimeZoneDataAvailableResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```

