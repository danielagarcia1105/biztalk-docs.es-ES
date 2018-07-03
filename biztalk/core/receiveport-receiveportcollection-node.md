---
title: PuertoRecepción (nodo ReceivePortCollection) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ae9cef-4e0f-42ca-ac45-fe1fabdfc7c5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b8e30a789327f872e384152d64a2edbebb4b9dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023162"
---
# <a name="receiveport-receiveportcollection-node"></a>puertoRecepción (nodo ReceivePortCollection)
El nodo puertoRecepción del nodo ReceivePortCollection de un archivo de enlace contiene información específica acerca de un puerto de recepción que se exporta con el archivo de enlace.  

## <a name="nodes-in-the-receiveport-node"></a>Nodos del nodo puertoRecepción  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  


|                                      **Nombre**                                       | **Tipo de nodo** |            **Tipo de datos**             |                                               **Descripción**                                               | **Restricciones** |                                                                                                 **Comentarios**                                                                                                  |
|-------------------------------------------------------------------------------------|---------------|--------------------------------------|-------------------------------------------------------------------------------------------------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        Nombre                                         |   Attribute   |              xs:string               |                                   Especifica el nombre del puerto de recepción.                                   |   No requerido   |                                                                                             Valor predeterminado: vacío                                                                                              |
|                                      IsTwoWay                                       |   Attribute   |              xs:boolean              |               Especifica si el puerto de recepción es unidireccional o de solicitud-respuesta (bidireccional).               |     Obligatorio     |      Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.IsTwoWay propiedad (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]      |
|                                    BindingOption                                    |   Attribute   |                xs:int                |                          Especifica el tipo de enlace del puerto de orquestación.                          |     Obligatorio     |                                             Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.BindingType** enumeración.                                              |
|                                     Descripción                                     |    Elemento    |              xs:string               |                                Especifica una descripción para el puerto de recepción.                                |     Obligatorio     |                                                                                             Valor predeterminado: vacío                                                                                              |
|          [ReceiveLocations](../core/receivelocations-receiveport-node.md)           |    Grabar     | ArrayOfReceiveLocation (ComplexType) |                 Nodo contenedor de las ubicaciones de recepción asociadas a este puerto de recepción.                 |  No requerido.   |                                                                                              Valor predeterminado: ninguno                                                                                              |
| [TransmitPipeline (nodo ReceivePort)](../core/transmitpipeline-receiveport-node.md) |    Grabar     |      PipelineRef (ComplexType)       | Especifica la canalización de envío asociada con el puerto de recepción si éste es bidireccional. |   No requerido   |                                                                                              Valor predeterminado: ninguno                                                                                              |
|                                  SendPipelineData                                   |    Elemento    |              xs:string               |         Especifica la configuración personalizada correspondiente a esta instancia del uso de la canalización.          |   No requerido   |                                                                                             Valor predeterminado: vacío.                                                                                             |
|                                   Autenticación                                    |    Elemento    |                xs:int                |      Especifica un valor de enumeración que indica si la autenticación es necesaria en este puerto de recepción.       |     Obligatorio     |                                          Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.AuthenticationType** enumeración.                                          |
|                                      Seguimiento                                       |    Elemento    |                xs:int                |                        Especifica el nivel de seguimiento de documentos correspondiente al puerto de recepción.                        |     Obligatorio     |                                            Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **Microsoft.BizTalk.ExplorerOM.TrackingTypes** enumeración.                                             |
|       [Transformaciones (nodo ReceivePort)](../core/transforms-receiveport-node.md)       |    Grabar     |    ArrayOfTransform (ComplexType)    |                  Especifica la colección de transformaciones de entrada de un puerto de recepción unidireccional.                  |   No requerido   |                                                                                              Valor predeterminado: ninguno                                                                                              |
|        [OutboundTransforms](../core/outboundtransforms-receiveport-node.md)         |    Grabar     |    ArrayOfTransform (ComplexType)    |       Especifica la colección de transformaciones de salida para aplicar a documentos en un puerto de recepción bidireccional.       |   No requerido   |                                                                                              Valor predeterminado: ninguno                                                                                              |
|                                 RouteFailedMessage                                  |    Elemento    |              xs:boolean              |             Especifica si los mensajes con errores se enrutan o no a los suscriptores de mensajes con errores.              |     Obligatorio     | Valor predeterminado: ninguno<br /><br /> Los valores posibles son en el **MSBTS_SendPort.RouteFailedMessage propiedad (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] |
|                                   ApplicationName                                   |    Elemento    |              xs:string               |                   Especifica el nombre de la aplicación asociada al puerto de recepción.                   |     Obligatorio     |           Valor predeterminado: vacío<br /><br /> Los valores posibles son en el **interfaz ISSOMapping (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]           |

