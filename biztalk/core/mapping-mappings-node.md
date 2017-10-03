---
title: Mapping (nodo Mappings) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2c62d46e4d5c2b73eee5094ecda0e20c039798a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mapping-mappings-node"></a>Mapping (nodo Mappings)
El nodo Mapping de un archivo de enlace describe la asignación entre un puerto de entidad y una operación de tipo de puerto de rol para la entidad dada de alta.  
  
## <a name="nodes-in-the-mapping-node"></a>Nodos del nodo Mapping  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|PortTypeName|Attribute|xs:string|Especifica el nombre del tipo de puerto.|No requerido|Valor predeterminado: vacío|  
|OperationName|Attribute|xs:string|Especifica la operación que pertenece a este tipo de puerto.|No requerido|Valor predeterminado: vacío|  
|[SendPortRef](../core/sendportref-mapping-node.md)|Grabar|SendPortRef (ComplexType)|Nodo contenedor de la lista de puertos de envío asociados a la asignación.|No requerido|Valor predeterminado: ninguno|