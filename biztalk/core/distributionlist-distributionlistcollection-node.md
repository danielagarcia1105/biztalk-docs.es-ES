---
title: DistributionList (nodo DistributionListCollection) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionList node [binding file]
ms.assetid: 51864a5c-1697-4804-ac18-8211494f3ff0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931443cdca27e5c06767f075298d50ff999545a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="distributionlist-distributionlistcollection-node"></a>DistributionList (nodo DistributionListCollection)
El nodo DistributionList de un archivo de enlace contiene información específica acerca de una lista de distribución que se exporta con el archivo de enlace. A una lista de distribución se hace referencia como un grupo de puertos de envío en el administrador de BizTalk Server.  
  
## <a name="nodes-in-the-distributionlist-node"></a>Nodos del nodo DistributionList  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre de la lista de distribución.|No requerido|Valor predeterminado: vacío|  
|[Puertos de envío](../core/sendports-distributionlist-node.md)|Grabar|ArrayOfSendPortRef (ComplexType)|Especifica el puerto o puertos de envío incluidos en lista de distribución.|No requerido|Valor predeterminado: ninguno|  
|Filtro|Elemento|xs:string|Especifica el nombre de la expresión de filtro opcional utilizada en esta lista de distribución.|Necesario|Valor predeterminado: vacío|  
|ApplicationName|Elemento|xs:string|Especifica el nombre de la aplicación a la que está asociada la lista de distribución.|Necesario|Valor predeterminado: vacío|  
|Description|Elemento|xs:string|Especifica una descripción para la lista de distribución.|Necesario|Valor predeterminado: vacío|