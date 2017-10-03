---
title: "PuertoRecepción (nodo ReceivePortCollection) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30ae9cef-4e0f-42ca-ac45-fe1fabdfc7c5
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da486df8bf406ca61f0b06d2cbc6f9b3f16539cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receiveport-receiveportcollection-node"></a>puertoRecepción (nodo ReceivePortCollection)
El nodo puertoRecepción del nodo ReceivePortCollection de un archivo de enlace contiene información específica acerca de un puerto de recepción que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-receiveport-node"></a>Nodos del nodo puertoRecepción  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del puerto de recepción.|No requerido|Valor predeterminado: vacío|  
|IsTwoWay|Attribute|xs:boolean|Especifica si el puerto de recepción es unidireccional o de solicitud-respuesta (bidireccional).|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.IsTwoWay propiedad (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]|  
|BindingOption|Attribute|xs:int|Especifica el tipo de enlace del puerto de orquestación.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.BindingType** enumeración.|  
|Description|Elemento|xs:string|Especifica una descripción para el puerto de recepción.|Necesario|Valor predeterminado: vacío|  
|[Ubicaciones de recepción](../core/receivelocations-receiveport-node.md)|Grabar|ArrayOfReceiveLocation (ComplexType)|Nodo contenedor de las ubicaciones de recepción asociadas a este puerto de recepción.|No requerido.|Valor predeterminado: ninguno|  
|[TransmitPipeline (nodo puertoRecepción)](../core/transmitpipeline-receiveport-node.md)|Grabar|PipelineRef (ComplexType)|Especifica la canalización de envío asociada con el puerto de recepción si éste es bidireccional.|No requerido|Valor predeterminado: ninguno|  
|SendPipelineData|Elemento|xs:string|Especifica la configuración personalizada correspondiente a esta instancia del uso de la canalización.|No requerido|Valor predeterminado: vacío.|  
|Autenticación|Elemento|xs:int|Especifica un valor de enumeración que indica si la autenticación es necesaria en este puerto de recepción.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.AuthenticationType** enumeración.|  
|Seguimiento|Elemento|xs:int|Especifica el nivel de seguimiento de documentos correspondiente al puerto de recepción.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.TrackingTypes** enumeración.|  
|[Transformaciones (nodo puertoRecepción)](../core/transforms-receiveport-node.md)|Grabar|ArrayOfTransform (ComplexType)|Especifica la colección de transformaciones de entrada de un puerto de recepción unidireccional.|No requerido|Valor predeterminado: ninguno|  
|[OutboundTransforms](../core/outboundtransforms-receiveport-node.md)|Grabar|ArrayOfTransform (ComplexType)|Especifica la colección de transformaciones de salida para aplicar a documentos en un puerto de recepción bidireccional.|No requerido|Valor predeterminado: ninguno|  
|RouteFailedMessage|Elemento|xs:boolean|Especifica si los mensajes con errores se enrutan o no a los suscriptores de mensajes con errores.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.RouteFailedMessage propiedad (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]|  
|ApplicationName|Elemento|xs:string|Especifica el nombre de la aplicación asociada al puerto de recepción.|Necesario|Valor predeterminado: vacío<br /><br /> Los valores posibles son en el **ISSOMapping (interfaz) (COM)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]|