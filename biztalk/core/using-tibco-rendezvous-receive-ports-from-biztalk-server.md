---
title: Esquemas de recepción y procesar los eventos con el adaptador de TIBCO Rendezvous | Documentos de Microsoft
description: Trabajar con esquemas de TIBCO Rendezvous en el lado de recepción y procesamiento de eventos con el adaptador de BizTalk para TIBCO Rendezvous en BizTalk
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbbae69dc1b7df1f5675442dde544a444cec02fb
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014099"
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a>Uso de puertos de recepción TIBCO Rendezvous desde BizTalk Server

## <a name="overview"></a>Información general
Para usar un puerto de recepción, puede proporcionar un esquema a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para los mensajes entrantes. Un puerto de recepción se configura para escuchar un determinado conjunto de nombres de asunto. Usa un nombre de asunto con caracteres comodín opcionales para coincidir con varios nombres de asunto. Defina diferentes operaciones de puerto en la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para cada posible asunto que coincida con la cadena dada.  
  
> [!NOTE]
>  El adaptador admite escenarios de mensajería y orquestación.  
  
## <a name="define-schemas"></a>Definir esquemas  
 Por ejemplo, si el puerto está configurado para escuchar el nombre del sujeto, **existencias. MERCADO. ÍNDICES. >** ('**>**' es un carácter comodín que significa cualquier cosa a la derecha), sería válido definir operaciones para nombres de asunto como **existencias. MERCADO. ÍNDICES. NYSE. SP500**, **existencias. MERCADO. ÍNDICES. TSX.TSX60**, y así sucesivamente. El adaptador genera mensajes usando la estrategia descrita en [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)y genera el nombre del elemento raíz y espacios de nombres basado en la escucha del firmante nombre y un mensaje recibido asunto nombres respectivamente.  
  
 En el ejemplo anterior, el adaptador genera un mensaje que es similar al siguiente para el evento SP500:  
  
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

## <a name="event-processing"></a>Procesamiento de eventos
El adaptador de Microsoft BizTalk para TIBCO Rendezvous distribuye eventos de una cola en varios subprocesos. Ubicación de recepción de un servidor BizTalk Server está asociado a una cola de eventos de TIBCO Rendezvous y su grupo de subprocesos de distribución.  
  
### <a name="memory-use-and-errors"></a>Uso de memoria y errores  
 Al procesar eventos, el adaptador vigila los recursos usados. Si el uso de memoria supera el umbral de marca de agua superior, el adaptador deja de distribuir eventos hasta que llega al consumo de memoria de la marca de agua inferior. Tenga en cuenta que, debido a esto, podrían perderse mensajes de TIBCO Rendezvous para mensajes no certificados (un consumidor de TIBCO RV tiene 60 segundos para quitar mensajes de una cola). Esta pérdida de datos se notifica como un error. Si el adaptador recibe un mensaje NO_MEMORY de aviso del sistema de TIBCO Rendezvous, significa que ya se han perdido mensajes.  
  
 El Adaptador de BizTalk para TIBCO Rendezvous mantiene un estado y ejecuta las tareas de diferente forma basándose en dicho estado. Si el Motor de mensajes de BizTalk notifica un error y el adaptador está configurado para ser una escucha certificada, notificará el error a TIBCO Rendezvous de modo que pueda reenviar el mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Asignación de tipos de datos para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)   
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)