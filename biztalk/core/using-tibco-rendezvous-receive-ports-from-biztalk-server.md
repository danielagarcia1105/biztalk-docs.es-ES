---
title: "Con TIBCO Rendezvous puertos de recepción de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive ports, using from BizTalk Server
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e0999362844570bb56cfbc488e5fd5775e286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a>Uso de puertos de recepción TIBCO Rendezvous desde BizTalk Server
Para usar un puerto de recepción, puede proporcionar un esquema a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para los mensajes entrantes. Un puerto de recepción se configura para escuchar un determinado conjunto de nombres de asunto. Usa un nombre de asunto con caracteres comodín opcionales para coincidir con varios nombres de asunto. Defina diferentes operaciones de puerto en la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para cada posible asunto que coincida con la cadena dada.  
  
> [!NOTE]
>  El Adaptador admite escenarios tanto de mensajería como de orquestación.  
  
## <a name="defining-schemas"></a>Definición de esquemas  
 Por ejemplo, si el puerto está configurado para escuchar el nombre del sujeto, **existencias. MERCADO. ÍNDICES. >** ('**>**' es un carácter comodín que significa cualquier cosa a la derecha), sería válido definir operaciones para nombres de asunto como **existencias. MERCADO. ÍNDICES. NYSE. SP500**, **existencias. MERCADO. ÍNDICES. TSX.TSX60**, y así sucesivamente. El adaptador genera mensajes usando la estrategia descrita en [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)y genera el nombre del elemento raíz y espacios de nombres basado en la escucha del firmante nombre y un mensaje recibido asunto nombres respectivamente.  
  
 En el ejemplo anterior, el adaptador genera un mensaje similar a este para el evento SP500:  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 Debe definir un esquema que usa las mismas convenciones. Por ejemplo:  
  
```  
<xsd:schema  
targetNamespace='   
  
http://schemas.microsoft.com/TibcoRendezvous/Types/STOCK.MARKET.INDICES.N  
YSE.GTWILDCARD'  
xmlns:xsd=' http://www.w3.org/2001/XMLSchema'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types'>  
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
<xsd:element name='STOCK.MARKET.INDICES.NYSE.SP500'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_NYSE_SP500" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<SP500 message definitions goes here>  
</xsd:complexType>  
<xsd:element name='STOCK.MARKET.INDICES.TSX.TSX60'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_TSX_TSX60" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<TSX60 message definitions goes here>  
</xsd:complexType>  
  
```  
  
 Tenga en cuenta el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName** anotación. Esto es para indicar a la integración de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk que use dicho nombre para los tipos de .NET Framework generados, en lugar del nombre que contiene puntos. Puede especificar cualquier cosa. En los ejemplos, los puntos se reemplazan por caracteres de subrayado.  
  
> [!NOTE]
>  Los puntos dan lugar a que las herramientas de desarrollo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generen nombres no válidos.  
  
## <a name="see-also"></a>Vea también  
 [Asignación de tipos de datos para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)   
 [Controladores de recepción de creación TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)