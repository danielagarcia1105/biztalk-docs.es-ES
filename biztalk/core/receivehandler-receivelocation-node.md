---
title: ReceiveHandler (nodo ReceiveLocation) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveHandler node [binding file]
ms.assetid: dd105052-ec71-4762-aa74-e8cdb806a6bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e865886624731414f979c77f3f2e898e417c8b11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268540"
---
# <a name="receivehandler-receivelocation-node"></a>ReceiveHandler (nodo ReceiveLocation)
El nodo ReceiveHandler del nodo ReceiveLocation de un archivo de enlace contiene información específica acerca del controlador de recepción asociado a un transporte que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-receivehandler-node"></a>Nodos del nodo ReceiveHandler  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del controlador de recepción asociado al transporte.|No requerido|Valor predeterminado: vacío|  
|HostTrusted|Attribute|xs:boolean|Especifica si el host asociado al controlador de recepción asociado es de confianza.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** si el host es de confianza, en caso contrario, se establece en **false**.|  
|[TransportType (nodo ReceiveHandler)](../core/transporttype-receivehandler-node.md)|Grabar|ProtocolType (ComplexType)|Especifica el tipo de transporte, que también es el nombre del adaptador usado con este controlador de recepción.|Necesario|Valor predeterminado: ninguno|