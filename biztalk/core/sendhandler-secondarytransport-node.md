---
title: SendHandler (nodo SecondaryTransport) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendHandler node [binding file]
ms.assetid: 32eb3e87-25ac-461e-9c09-3d6d9bcba3b2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f5ecdbb1860c9132133835b8928f85b1e0e1cfb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sendhandler-secondarytransport-node"></a>SendHandler (nodo SecondaryTransport)
El nodo SendHandler del nodo SecondaryTransport de un archivo de enlace contiene información específica acerca del controlador de envío asociado a un transporte que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-sendhandler-node"></a>Nodos del nodo SendHandler  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del controlador de envío asociado al transporte.|No requerido|Valor predeterminado: vacío|  
|HostTrusted|Attribute|xs:boolean|Especifica si el host asociado al controlador de envío es de confianza.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** si el host es de confianza, en caso contrario, se establece en **false**.|  
|[TransportType (nodo SendHandler)](../core/transporttype-sendhandler-node.md)|Grabar|ProtocolType (ComplexType)|Especifica el tipo de transporte, que también es el nombre del adaptador usado con este controlador de envío.|Necesario|Valor predeterminado: ninguno|