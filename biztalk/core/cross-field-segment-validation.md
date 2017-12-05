---
title: "Campo de segmento validación cruzada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e757b4f-71fe-44d5-9580-c8b1c8eb2366
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd3a0b5f68ded39fbf5cc88a4ba8aac6725602e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="cross-field-segment-validation"></a>Campo de segmento validación cruzada
La canalización de recepción EDI y la canalización de envío EDI pueden llevar a cabo una validación de segmentos/campos cruzados en los elementos de datos del conjunto de transacciones en los mensajes codificados con X12. Esta validación se denomina condiciones de relación en X12. La validación de campos cruzados se expresa mediante anotaciones y, como resultado, se relaciona con la validación EDI.  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no admite las reglas de dependencia de EDIFACT.  
  
 Para mensajes codificados con X12, habilite esta validación mediante el establecimiento del indicador X12ConditionDesignator_Check del esquema de mensajes en "Sí". Este indicador es una anotación en la sección "appinfo" del esquema. De forma predeterminada, este indicador se establece en "No" y no se habilita la validación de segmentos\campos cruzados para los esquemas X12. Para los esquemas HIPAA, el valor predeterminado se establece en "Sí" y se habilita la validación de segmentos\campos cruzados.  
  
> [!NOTE]
>  La validación de segmentos/campos cruzados es distinta de la validación de elementos de datos EDI y la validación (BTS-XSD) extendida. La validación de elementos de datos EDI o la validación extendida se pueden realizar sin llevar a cabo la validación de segmentos/campos cruzados, y la validación de segmentos/campos cruzados se puede realizar sin llevar a cabo la validación de elementos de datos EDI o la validación extendida.  
  
 La opcionalidad en X12 se compone de obligatorio (M), opcional (O) y relacional (R) (validación de campos cruzados). Si la opcionalidad es obligatoria, se debe valorar como mínimo un elemento de datos de componente en tipos compuestos.  
  
## <a name="x12-optionality"></a>Opcionalidad X12  
 En X12, la validación de segmentos/campos cruzados para la opcionalidad relacional incluye una serie de comprobaciones enumeradas en las reglas del esquema. Cada regla se identifica mediante el siguiente elemento en un \<xs\> elemento:  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 La condición relacional del elemento "Rule" indica lo que va a validar dicha regla. Este elemento incluye una lista de asuntos en los que se ejecuta la validación de campos cruzados. Los asuntos se incluyen en el siguiente nodo:  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 La tabla siguiente muestra las condiciones relacionales X12:  
  
|Subclasificación|Condición relacional|Description|  
|-----------------------|--------------------------|-----------------|  
|Emparejado|X12ConditionDesignatorX_Paired|Si alguno de los elementos del asunto especificados en la condición relacional está presente, todos los elementos del sujeto especificados deben estar presentes.|  
|Necesario|X12ConditionDesignatorX_Required|Como mínimo, debe estar presente uno de los elementos del asunto especificado en la condición relacional.|  
|Exclusión|X12ConditionDesignatorX_Exclusion|Es posible que no esté presente más de un elemento del asunto en la condición relacional.|  
|Condicional|X12ConditionDesignatorX_Conditional|Si está presente el primer elemento del asunto especificado en la condición relacional, los demás elementos del asunto deben estar presentes. Puede aparecer alguno o todos los elementos no especificados como primer elemento en la condición sin que sea necesario que el primer elemento esté presente. El orden de los elementos en la condición no tiene que ser el mismo que el orden de los elementos de datos en los segmentos de datos.|  
|Condicional de lista|X12ConditionDesignatorX_List Conditional|Si está presente el primer elemento del asunto especificado en la condición relacional, debe estar presente, como mínimo, uno de los elementos restantes del asunto. Puede aparecer alguno o todos los elementos no especificados como primer elemento en la condición sin que sea necesario que el primer elemento esté presente. El orden de los elementos en la condición no tiene que ser el mismo que el orden de los elementos de datos en los segmentos de datos.|  
  
## <a name="see-also"></a>Vea también  
 [Validación de mensajes EDI](../core/edi-message-validation.md)