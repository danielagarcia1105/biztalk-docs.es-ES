---
title: Asignación de tipo de datos para recibir desde TIBCO Rendezvous | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb17ceac0c323bba7a6f25cff0d07473b6d7fa3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014667"
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a>Asignación de tipos de datos para controladores de recepción de TIBCO Rendezvous
El Adaptador de Microsoft BizTalk para TIBCO Rendezvous asigna los tipos TIBCO RV a los tipos de esquemas XML según se especifica en la tabla siguiente.  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a>TIBCO RV para asignación de tipos de datos XML  
  
|Tipo TIBCO RV|Tipo de esquema XML|Comentarios|  
|-------------------|---------------------|--------------|  
|TIBRVMSG_MSG|tibrv:message|Completo documento XML construido a partir de todo el mensaje.|  
|TIBRVMSG_XML|tibrv:rawxml|Documento XML construido a partir de la matriz de bytes (no interpreta por el adaptador).|  
|TIBRVMSG_DATETIME|xsd:dateTime|El adaptador usa la clase System.Xml.XmlConvert para convertir entre instancias de esquemas XML `dateTime` y `System.DateTime`.|  
|TIBRVMSG_OPAQUE|xsd:base64Binary||  
|TIBRVMSG_STRING|xsd:cadena||  
|TIBRVMSG_BOOL|xsd:boolean||  
|TIBRVMSG_I8|xsd:byte||  
|TIBRVMSG_I16|xsd:short||  
|TIBRVMSG_I32|xsd:int||  
|TIBRVMSG_I64|xsd:long||  
|TIBRVMSG_U8|xsd:unsignedByte||  
|TIBRVMSG_U16|xsd:unsignedShort||  
|TIBRVMSG_U32|xsd:unsignedInt||  
|TIBRVMSG_U64|xsd:unsignedLong||  
|TIBRVMSG_F32|xsd:float||  
|TIBRVMSG_F64|xsd:double||  
|TIBRVMSG_IPADDR32|tibrv:IPaddress|`System.Net.IPAddress.ToString( )` se usa para generar la salida. El contenido está en el orden de bytes de la red. ToString() se encarga de ello.|  
|TIBRVMSG_IPPORT16|tibrv:IPport|El contenido está en el orden de bytes de la red|  
|TIBRVMSG_I8ARRAY|tibrv:arrayOfByte|el espacio de nombres del esquema 'tibrv' se proporciona con el adaptador.|  
|TIBRVMSG_I16ARRAY|tibrv:arrayOfShort||  
|TIBRVMSG_I32ARRAY|tibrv:arrayOfInt||  
|TIBRVMSG_I64ARRAY|tibrv:arrayOfLong||  
|TIBRVMSG_U8ARRAY|tibrv:arrayOfUnsignedByte||  
|TIBRVMSG_U16ARRAY|tibrv:arrayOfUnsignedShort||  
|TIBRVMSG_U32ARRAY|tibrv:arrayOfUnsignedInt||  
|TIBRVMSG_U64ARRAY|tibrv:arrayOfUnsignedLong||  
|TIBRVMSG_F32ARRAY|tibrv:arrayOfFloat||  
|TIBRVMSG_F64ARRAY|tibrv:arrayOfDouble||  
  
 Las matrices de TIBCO Rendezvous difieren de una secuencia de campos con el mismo nombre. Por ejemplo, en un mensaje de TIBCO Rendezvous, es válido tener una matriz con 70.000 elementos, pero no tener 70.000 campos.  
  
 El esquema para los tipos de matriz de la tabla anterior es similar a éste:  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 Un elemento de matriz de un mensaje tiene este aspecto:  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 El esquema para la dirección IP tiene este aspecto:  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 El esquema para el puerto IP tiene este aspecto:  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a>Vea también  
 [Asignación de mensaje de TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md)   
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)