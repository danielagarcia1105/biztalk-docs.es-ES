---
title: Esquema (nodo TrackedSchemas) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Schema node
ms.assetid: a503aad6-07f8-4650-a214-4d2f6650cb80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5376c505332ed05507169c1db2dc54ec4e7bdfe6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-trackedschemas-node"></a>Esquema (nodo TrackedSchemas)
El nodo Esquema del nodo TrackedSchemas de un archivo de enlace describe un esquema enlazado con un servicio que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-schema-node"></a>Nodos del nodo Esquema  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|Attribute|xs:string|Especifica el nombre completo del esquema.|No requerido|Valor predeterminado: vacío|  
|AssemblyQualifiedName|Attribute|xs:string|Especifica el nombre completo del ensamblado que contiene este esquema.|No requerido|Valor predeterminado: vacío|  
|AlwaysTrackAllProperties|Attribute|xs:boolean|Especifica si se va a hacer el seguimiento de todas las propiedades del ensamblado especificado.|Necesario|Valor predeterminado: ninguno<br /><br /> Establecido en **true** para realizar el seguimiento de todas las propiedades, en caso contrario, establézcalo **false**.|  
|Description|Atributo|xs:string|Especifica una descripción del esquema.|No requerido|Valor predeterminado: vacío|  
|[TrackedPropertyNames (nodo de esquema)](../core/trackedpropertynames-schema-node.md)|Grabar|ArrayOfString (ComplexType)|Contenedor de los elementos que especifican las propiedades a las que se debe hacer el seguimiento.|No requerido|Valor predeterminado: ninguno|