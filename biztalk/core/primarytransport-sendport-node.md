---
title: PrimaryTransport (nodo puertoEnvío) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PrimaryTransport node [binding file]
ms.assetid: 22b68d27-f280-4272-84b8-8a50f230228a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b2d60f3b7fbb09e2e106a4d91f1eca0385aa155
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="primarytransport-sendport-node"></a>PrimaryTransport (nodo puertoEnvío)
El nodo PrimaryTransport del nodo puertoEnvío de un archivo de enlace proporciona información específica acerca del transporte principal enlazado a un puerto de envío que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-primarytransport-node"></a>Nodos del nodo PrimaryTransport  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Dirección|Elemento|xs:string|Especifica la dirección (o URI) del transporte.|No requerido|Valor predeterminado: vacío|  
|[TransportType (nodo PrimaryTransport)](../core/transporttype-primarytransport-node.md)|Grabar|ProtocolType (ComplexType)|Especifica el tipo de transporte, que también es el nombre del adaptador usado para este transporte.|No requerido|Valor predeterminado: ninguno|  
|TransportTypeData|Elemento|xs:string|Especifica la información de configuración específica del adaptador.|No requerido|Valor predeterminado: vacío<br /><br /> Vea [propiedades de configuración para los adaptadores de BizTalk integrados](../core/configuration-properties-for-integrated-biztalk-adapters.md) para obtener información específica de adaptador acerca de las propiedades que se pueden almacenar en esta cadena.|  
|RetryCount|Elemento|xs:int|Especifica el número de reintentos para el adaptador usado con el transporte.|Necesario|Valor predeterminado: ninguno|  
|RetryInterval|Elemento|xs:int|Especifica el intervalo de reintentos en minutos para el adaptador usado con el transporte.|Necesario|Valor predeterminado: ninguno|  
|ServiceWindowEnabled|Elemento|xs:boolean|Especifica si la ventana de servicio está habilitada para el adaptador usado con el transporte.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** si está habilitada la ventana de servicio, en caso contrario, se establece en **false**.|  
|FromTime|Elemento|xs:dateTime|Especifica la hora de inicio de la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|ToTime|Elemento|xs:dateTime|Especifica la hora de finalización de la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|Principal|Elemento|xs:boolean|Especifica si el adaptador usado con el transporte es principal.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** si el adaptador usado con el transporte es principal, en caso contrario, se establece en **false**.|  
|OrderedDelivery|Elemento|xs:boolean|Especifica si el adaptador usado con el transporte debería o no enviar mensajes de una manera ordenada.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** si el transporte es enviar mensajes en orden, en caso contrario, se establece en **false**.|  
|DeliveryNotification|Elemento|xs:int|Especifica si el adaptador usado con el transporte debería o no devolver una notificación de entrega que indique si la transmisión fue correcta.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** para las notificaciones de entrega, de lo contrario establece **false**.|  
|[SendHandler](../core/sendhandler-primarytransport-node.md)|Grabar|SendHandlerRef (ComplexType)|Especifica el controlador de envío para el adaptador usado con el transporte.|Necesario|Valor predeterminado: ninguno|