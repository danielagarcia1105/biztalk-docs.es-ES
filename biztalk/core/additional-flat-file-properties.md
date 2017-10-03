---
title: Propiedades adicionales del archivo sin formato | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c88ad2f-b5a8-46e6-b1b8-61ce6ba910d1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9989d29eadf2487b84e2520755e879cd201b1798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="additional-flat-file-properties"></a>Propiedades adicionales de archivos sin formato

## <a name="hidden-properties"></a>Propiedades ocultas
La siguiente tabla contiene propiedades adicionales de los nodos de archivo sin formato que no aparecen en el Editor de esquemas. Para usar estas propiedades, es necesario editar manualmente el archivo de esquema en un editor de texto.  
  
|Propiedad|Valores|Valor predeterminado|Description|  
|--------------|------------|-------------------|-----------------|  
|suppress_empty_nodes|**True** o **False**|**false**|Indica si se van a quitar o no los nodos XML vacíos después de que el analizador genere datos de instancia XML.|  
|generate_empty_nodes|**True** o **False**|**true**|Genera nodos vacíos para los registros existentes en los datos de instancia XML.|  
|parser_optimization|**velocidad** o **complejidad**|**velocidad**|La optimización de la velocidad (valor speed) reduce el tiempo de análisis, pero a costa de tener ciertas ambigüedades en los datos. La optimización de la complejidad (valor complexity) soluciona un mayor número de ambigüedades, pero a costa de tener una menor velocidad de procesamiento.|  
|lookahead_depth|Cualquier entero positivo; cero (0) indica lectura previa infinita|3|Profundidad de lectura utilizada para encontrar datos coincidentes.|  
|allow_early_termination|**True** o **False**|**false**|Indica si los registros posicionales pueden finalizar al principio (**true**) o debe contener datos para todos los campos de registro (**false**).|  
|early_terminate_optional_fields|**True** o **False**|**false**|Habilita la finalización anticipada de campos finales opcionales (**true**). Si el esquema existente sin esta anotación se abrirá en el Editor de BizTalk, esta anotación se agregará a él con el valor predeterminado establecido en (**false**). **Nota:** la anotación early_terminate_optional_fields solo aplica si allow_early_termination está establecido en "true".|  
  
 Todas estas propiedades son atributos de la **/annotation/appinfo/schemaInfo** elemento.  
  
 Cuando **parser_optimization** está establecido en **complejidad**, es posible que tenga errores de validación en un esquema cuando hay muchos nodos opcionales en el mismo grupo o registro. Puede que necesite establecer **lookahead_depth** en cero (0) para evitar errores de validación.  
  
## <a name="see-also"></a>Vea también  
-  [Propiedades de nodo](../core/node-properties.md)   
-  **Esquemas de archivo de propiedades de nodo adicionales plano**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]