---
title: ReceiveLocation (nodo ReceiveLocations) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveLocation node [binding file]
ms.assetid: 706ec5b2-c26f-428a-ad56-1c01b34aa8f8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f959dfc9aadfbf317d3843fb0ed174a2a0f22ea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270284"
---
# <a name="receivelocation-receivelocations-node"></a>ReceiveLocation (nodo ReceiveLocations)
El nodo ReceiveLocation del nodo ReceiveLocations de un archivo de enlace contiene información específica acerca de una ubicación de recepción que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-receivelocation-node"></a>Nodos del nodo ReceiveLocation  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre de la ubicación de recepción.|No requerido|Valor predeterminado: vacío|  
|Description|Elemento|xs:string|Especifica una descripción para la ubicación de recepción.|Necesario|Valor predeterminado: vacío|  
|Dirección|Elemento|xs:string|Especifica la dirección de la ubicación de recepción.|Necesario|Valor predeterminado: vacío|  
|PublicAddress|Elemento|xs:string|Especifica la dirección pública de la ubicación de recepción.|No requerido|Valor predeterminado: vacío|  
|Principal|Elemento|xs:boolean|Especifica si la ubicación de recepción es principal.|Necesario|Valor predeterminado: ninguno|  
|ReceiveLocationServiceWindowEnabled|Elemento|xs:boolean|Especifica si la ventana de servicio está habilitada.|Necesario|Valor predeterminado: ninguno<br /><br /> Especifique **true** si la ventana de servicio está habilitada; en caso contrario, especifique **false.**|  
|ReceiveLocationFromTime|Elemento|xs:dateTime|Especifica la hora de inicio de la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|ReceiveLocationToTime|Elemento|xs:dateTime|Especifica la hora de finalización de la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|ReceiveLocationStartDateEnabled|Elemento|xs:boolean|Especifica si está habilitada la fecha de inicio para la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|ReceiveLocationStartDate|Elemento|xs:dateTime|Especifica la fecha de inicio de la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|ReceiveLocationEndDateEnabled|Elemento|xs:boolean|Especifica si está habilitada la fecha de finalización para la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|ReceiveLocationEndDate|Elemento|xs:dateTime|Especifica la fecha de finalización de la ventana de servicio.|Necesario|Valor predeterminado: ninguno|  
|[ReceiveLocationTransportType](../core/receivelocationtransporttype-receivelocation-node.md)|Grabar|ProtocolType (ComplexType)|Especifica el tipo de transporte para esta ubicación de recepción.|Necesario|Valor predeterminado: ninguno|  
|ReceiveLocationTransportTypeData|Elemento|xs:string|Especifica las propiedades del tipo de transporte para la ubicación de recepción.|No requerido|Valor predeterminado: vacío<br /><br /> Vea [propiedades de configuración para los adaptadores de BizTalk integrados](../core/configuration-properties-for-integrated-biztalk-adapters.md) para obtener información específica de adaptador acerca de las propiedades que se pueden almacenar en esta cadena.|  
|[ReceivePipeline](../core/receivepipeline-receivelocation-node.md)|Grabar|PipelineRef (ComplexType)|Especifica la canalización de recepción para la ubicación de recepción.|Necesario|Valor predeterminado: ninguno|  
|ReceivePipelineData|Elemento|xs:string|Especifica la configuración personalizada correspondiente a la canalización de recepción que se usa para esta ubicación de recepción.|Necesario|Valor predeterminado: vacío|  
|[SendPipeline](../core/sendpipeline-receivelocation-node.md)|Grabar|PipelineRef (ComplexType)|Especifica la canalización de envío para una ubicación de recepción bidireccional. **Nota:** en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enviar canalizaciones para recepciones bidireccionales se especifican en la ubicación de recepción en lugar de en el puerto de recepción. A menos que se especifique lo contrario en el archivo de enlace, una ubicación de recepción heredará automáticamente la canalización de envío del puerto de recepción al que pertenece.|Necesario|Valor predeterminado: ninguno|  
|SendPipelineData|Elemento|xs:string|Especifica la configuración personalizada correspondiente a la canalización de envío que se usa para esta ubicación de recepción.|Necesario|Valor predeterminado: vacío|  
|[EncryptionCert](../core/encryptioncert-receivelocation-node.md)|Grabar|CertificateInfo (ComplexType)|Especifica el certificado de cifrado asociado a la ubicación de recepción.|No requerido|Valor predeterminado: ninguno|  
|Habilitar|Elemento|xs:boolean|Especifica si la ubicación de recepción está habilitada o no.|Necesario|Valor predeterminado: ninguno|  
|[ReceiveHandler](../core/receivehandler-receivelocation-node.md)|Grabar|ReceiveHandlerRef (ComplexType)|Especifica el controlador de recepción que se va a usar para esta ubicación de recepción.|No requerido|Valor predeterminado: ninguno|