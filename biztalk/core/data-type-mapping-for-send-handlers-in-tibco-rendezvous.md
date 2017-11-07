---
title: "Tipo de datos de asignación para controladores de envío de TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bda336d149d373477b26efeb2e4b05de4aac7554
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a>Asignación de tipos de datos para controladores de envío de TIBCO Rendezvous
La asignación de tipos de esquema XML a tipos TIBCO Rendezvous solo es posible si TIBCO Rendezvous proporciona información de tipos (xsi:type=). Los tipos no compatibles se asignan a las cadenas si es posible. Si la asignación no es posible, o si la opción está deshabilitada en la configuración del puerto, se genera un error.  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a>Esquema XML para la asignación de tipos de datos de TIBCO Rendezvous  
 La siguiente tabla muestra la asignación posible desde tipos de esquema XML a tipos de TIBCO Rendezvous.  
  
|Tipo XML|Tipo TIBCO RV|  
|--------------|-------------------|  
||TIBRVMSG_MSG|  
||TIBRVMSG_XML|  
|xsd:dateTime|TIBRVMSG_DATETIME|  
|xsd:boolean|TIBRVMSG_BOOL|  
|xsd:byte|TIBRVMSG_I8|  
|xsd:short|TIBRVMSG_I16|  
|xsd:int|TIBRVMSG_I32|  
|xsd:long|TIBRVMSG_I64|  
|xsd:unsignedByte|TIBRVMSG_U8|  
|xsd:unsignedShort|TIBRVMSG_U16|  
|xsd:unsignedInt|TIBRVMSG_U32|  
|xsd:unsignedLong|TIBRVMSG_U64|  
|xsd:float|TIBRVMSG_F32|  
|xsd:double|TIBRVMSG_F64|  
|tibrv:IPaddress|TIBRVMSG_IPADDR32|  
|tibrv:IPport|TIBRVMSG_IPPORT16|  
|tibrv:arrayOfByte|TIBRVMSG_I8ARRAY|  
|tibrv:arrayOfShort|TIBRVMSG_I16ARRAY|  
|tibrv:arrayOfInt|TIBRVMSG_I32ARRAY|  
|tibrv:arrayOfLong|TIBRVMSG_I64ARRAY|  
|tibrv:arrayOfUnsignedByte|TIBRVMSG_U8ARRAY|  
|tibrv:arrayOfUnsignedShort|TIBRVMSG_U16ARRAY|  
|tibrv:arrayOfUnsignedInt|TIBRVMSG_U32ARRAY|  
|tibrv:arrayOfUnsignedLong|TIBRVMSG_U64ARRAY|  
|tibrv:arrayOfFloat|TIBRVMSG_F32ARRAY|  
|tibrv:arrayOfDouble|TIBRVMSG_F64ARRAY|  
|Todo lo demás, con un mensaje de depuración|TIBRVMSG_STRING el registro.|  
  
 Puesto que el adaptador de BizTalk para TIBCO Rendezvous no tiene acceso a un esquema, cuando se transmita de BizTalk Server a TIBCO Rendezvous, se debe proporcionar el atributo XML `xsi:type` para cualquier campo que no sea una cadena. El adaptador usa esa información para generar el tipo de campo de mensaje apropiado en el mensaje de TIBCO Rendezvous.  
  
## <a name="message-mapping-example"></a>Ejemplo de asignación de mensaje  
 En el ejemplo siguiente se muestra la asignación de un mensaje desde BizTalk Server a TIBCO Rendezvous. Consulte la tabla de asignación de tipos de datos para obtener información acerca de cómo se asignan los tipos.  
  
```  
<ns:QuoteUpdate xmlns:xsi http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd http://www.w3.org/2001/XMLSchema"  
xmlns:tibrv="http://schemas.microsoft.com/TibcoRendezvous/Types"  
xmlns:ns="some namespace for this message [value not important, unless the schema is also used for receive ports]">  
  
<ns:SymbolName id=1 xsi:type="xsd:string">MSFT</ns:SymbolName>  
  
<ns:LastTrade id=2 xsi:type="xsd:double">28.40</ns:LastTrade>   
<ns:DayLow id=3 xsi:type="xsd:double">28.25</ns:DayLow>  
  
```  
  
|||  
|-|-|  
|`<ns:DayHigh`|`id=4 xsi:type="xsd:double">28.40</ns:DayHigh>`|  
|`<ns:MarketCap`|`id=10>262575234981</ns:MarketCap>`|  
|`<ns:Bids`|`id=100 xsi:type="tibrv:message">`|  
  
```  
<ns:TopBids id=1 xsi:type="tibrv:arrayOfDouble">  
<item>28.40</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.38</item>  
  
</ns:TopBids>  
  
<ns:BidsSize id=2 xsi:type="tibrv:arrayOfLong">  
<item>500</item>  
<item>1000</item>  
<item>100</item>  
<item>100</item>  
<item>2000</item>  
  
</ns:BidsSize>  
</ns:Bids>  
</ns:QuoteUpdate>  
  
```  
  
 Una vez generado el mensaje anterior como mensaje de TIBCO Rendezvous estructurado, sería una instancia TibcoMsg de nivel superior con seis campos. Los últimos campos son un mensaje secundario, compuesto por dos campos de tipos de matriz (los elementos "item" no se asignan a los campos de mensaje de TIBCO Rendezvous, sino a los elementos de un campo de mensaje de tipo `array`). El campo MarketCap, al no tener ninguna especificación de tipo, se enviaría como un campo de mensaje de cadena.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de envío de TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)