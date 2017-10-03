---
title: "PuertoEnvío (nodo SendPortCollection) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf7a6f9-9240-48b9-b196-8838afd4f41e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43db1aa63fb828ebbc0ee6d857ce79968b846aea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sendport-sendportcollection-node"></a>puertoEnvío (nodo SendPortCollection)
El nodo puertoEnvío de un archivo de enlace contiene información específica acerca de un puerto de envío que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-sendport-node"></a>Nodos del nodo puertoEnvío  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del puerto de envío.|No requerido|Valor predeterminado: vacío|  
|IsStatic|Attribute|xs:boolean|Determina si el puerto de envío es estático o dinámico.|Necesario|Valor predeterminado: ninguno|  
|IsTwoWay|Attribute|xs:boolean|Especifica si el puerto de envío es unidireccional o de petición-respuesta (bidireccional).|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.IsTwoWay propiedad (WMI)**.|  
|BindingOption|Attribute|xs:int|Especifica el tipo de enlace del puerto de orquestación.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.BindingType** enumeración.|  
|Description|Elemento|xs:string|Especifica una descripción para el puerto de envío.|Necesario|Valor predeterminado: vacío|  
|[TransmitPipeline (nodo puertoEnvío)](../core/transmitpipeline-sendport-node.md)|Grabar|PipelineRef (ComplexType)|Especifica la canalización de envío asociada al puerto de envío.|No requerido|Valor predeterminado: ninguno|  
|SendPipelineData|Elemento|xs:string|Especifica la configuración personalizada correspondiente a esta instancia del uso de la canalización.|No requerido|Valor predeterminado: vacío.|  
|[PrimaryTransport](../core/primarytransport-sendport-node.md)|Grabar|TransportInfo (ComplexType)|Especifica información sobre el transporte principal que el puerto de envío está configurado para utilizar.|No requerido|Valor predeterminado: ninguno|  
|[SecondaryTransport](../core/secondarytransport-sendport-node.md)|Grabar|TransportInfo (ComplexType)|Especifica información sobre el transporte secundario que el puerto de envío está configurado para utilizar.|No requerido|Valor predeterminado: ninguno|  
|[EncryptionCert](../core/encryptioncert-sendport-node.md)|Grabar|CertificateInfo (ComplexType)|Especifica información sobre el certificado de cifrado utilizado con el puerto de envío.|No requerido|Valor predeterminado: ninguno|  
|[ReceivePipeline](../core/receivepipeline-sendport-node.md)|Grabar|PipelineRef (ComplexType)|Especifica información sobre cualquier canalización de recepción utilizada con el puerto de envío.|No requerido|Valor predeterminado: ninguno|  
|ReceivePipelineData|Elemento|xs:string|Especifica la configuración personalizada correspondiente a esta instancia del uso de la canalización.|Necesario|Valor predeterminado: vacío|  
|Seguimiento|Elemento|xs:int|Especifica el nivel de seguimiento de documentos correspondiente al puerto de envío.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.TrackingTypes** enumeración.|  
|Filtro|Elemento|xs:string|Especifica el nombre de la expresión de filtro opcional utilizada en este puerto de envío.|Necesario|Valor predeterminado: vacío<br /><br /> Los valores posibles son en el **propiedad MSBTS_SendPort.Filter (WMI)**|  
|[Transformaciones (nodo puertoEnvío)](../core/transforms-sendport-node.md)|Grabar|ArrayOfTransform (ComplexType)|Especifica la colección de transformaciones de salida de un puerto de envío unidireccional.|No requerido|Valor predeterminado: ninguno|  
|[InboundTransforms](../core/inboundtransforms-sendport-node.md)|Grabar|ArrayOfTransform (ComplexType)|Especifica la colección de transformaciones de entrada de un puerto de envío bidireccional.|No requerido|Valor predeterminado: ninguno|  
|OrderedDelivery|Elemento|xs:boolean|Especifica si el puerto de envío ordena o no la entrega de mensajes.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.OrderedDelivery propiedad (WMI)**|  
|Prioridad|Elemento|xs:int|Especifica la prioridad del puerto de envío.|Necesario|Valor predeterminado: 5<br /><br /> Los valores posibles son en el **MSBTS_SendPort.Priority propiedad (WMI)**|  
|StopSendingOnFailure|Elemento|xs:boolean|Especifica si el puerto de envío deja o no de enviar mensajes cuando se produce un error.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.StopSendingOnFailure propiedad (WMI)**|  
|RouteFailedMessage|Elemento|xs:boolean|Especifica si los mensajes con errores se enrutan o no a los suscriptores de mensajes con errores.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.RouteFailedMessage propiedad (WMI)**|  
|ApplicationName|Elemento|xs:string|Especifica el nombre de la aplicación asociada al puerto de envío.|Necesario|Valor predeterminado: vacío<br /><br /> Los valores posibles son en el **ISSOMapping.ApplicationName (propiedad)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|

## <a name="see-also"></a>Vea también
Para obtener más información sobre estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].