---
title: TransportType (nodo SendHandler) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ee87a409-33dd-4111-ba6a-ead3bacc80aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3525b78fa9812c1e4fa8690a622f9b8cccce8d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278988"
---
# <a name="transporttype-sendhandler-node"></a>TransportType (nodo SendHandler)
El nodo TransportType del nodo SendHandler de un archivo de enlace contiene información específica acerca del adaptador asociado a un controlador de envío que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-transporttype-node"></a>Nodos del nodo TransportType  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del adaptador asociado al controlador de envío.|No requerido|Valor predeterminado: vacío|  
|Capabilities|Atributo|xs:int|Especifica las capacidades del adaptador asociado al controlador de envío.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .|  
|ConfigurationClsid|Atributo|xs:string|Especifica el GUID de configuración del adaptador asociado al controlador de envío.|No requerido|Valor predeterminado: vacío|