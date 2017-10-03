---
title: TransportType (nodo PrimaryTransport) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransportType node [binding file]
ms.assetid: 9eb377ec-35d8-4b72-85f9-f264f6553c5a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40e0f005e7279541a2cdcb5c2bf205b7731e5263
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype-primarytransport-node"></a>TransportType (nodo PrimaryTransport)
El nodo TransportType del nodo PrimaryTransport de un archivo de enlace contiene información específica acerca del adaptador asociado a un transporte que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-transporttype-node"></a>Nodos del nodo TransportType  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del adaptador asociado al transporte.|No requerido|Valor predeterminado: vacío|  
|Capabilities|Atributo|xs:int|Especifica las funciones del adaptador asociado al transporte.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .|  
|ConfigurationClsid|Atributo|xs:string|Especifica el GUID de configuración del adaptador asociado al transporte.|No requerido|Valor predeterminado: vacío|