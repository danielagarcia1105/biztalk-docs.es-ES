---
title: ReceiveLocationTransportType (nodo ReceiveLocation) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveLocationTransportType node [binding file]
ms.assetid: 375076c3-d5e6-4c25-b054-b452e29717e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eae3e2c4fd9f5f668cb12ffd630640b1b63c74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268724"
---
# <a name="receivelocationtransporttype-receivelocation-node"></a>ReceiveLocationTransportType (nodo ReceiveLocation)
El nodo ReceiveLocationTransportType del nodo ReceiveLocation de un archivo de enlace contiene información específica acerca del adaptador asociado a un transporte que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a>Nodos del nodo ReceiveLocationTransportType  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del adaptador asociado al transporte.|No requerido|Valor predeterminado: vacío|  
|Capabilities|Atributo|xs:int|Especifica las funciones del adaptador asociado al transporte.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .|  
|ConfigurationClsid|Atributo|xs:string|Especifica el GUID de configuración del adaptador asociado al transporte.|No requerido|Valor predeterminado: vacío|