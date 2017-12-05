---
title: "Cómo agregar valores constantes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46bf66e-caf2-4352-930f-c3c43a5717c3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7ea539b778cc382991e82841dec45db5316f18
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-add-constant-values"></a>Cómo agregar valores constantes
Cuando realiza las pruebas de las asignaciones, algunas veces es conveniente establecer valores constantes para utilizarlos durante la prueba.  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a>Establecer valores constantes para los nodos en el origen o destino de árboles de esquema  
  
1.  Seleccione un registro o campo en los árboles de esquema de origen o destino.  
  
2.  En la ventana Propiedades, en la **General** categoría, use la **valor** propiedad para especificar un valor para el campo o registro seleccionado.  
  
    > [!NOTE]
    >  Sólo se puede asociar un valor con un registro con su **contenido** propiedad establecida en **sólo texto** o **Mixed**.  
  
 Para un nodo de esquema de origen, si establece la **valor** propiedad  **\<vacía\>**, el mensaje de instancia generado para el esquema de origen contiene un valor vacío para los respectivos nodo.  
  
 En ocasiones, no se usan todos los campos del esquema de destino; es decir, algunos de los campos del esquema de destino no tienen ningún vínculo entrante. En tales casos, la operación Comprobar asignación produce error, siempre que el **validar entrada de comprobar asignación** o **validar salida de comprobar asignación** propiedades se establecen en **True**. Para evitar errores de comprobar asignación en tales casos, establezca el **valor** propiedad del nodo que puede ser un valor constante o  **\<vacía\>**. Use  **\<vacía\>**  si no desea establecer datos arbitrarios para campos de esquema de destino sin usar.  
  
## <a name="see-also"></a>Vea también  
[Validar y probar las asignaciones](../core/how-to-configure-map-validation-and-test-parameters.md)