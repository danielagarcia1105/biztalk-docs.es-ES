---
title: "Problemas conocidos de la validación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69400c5196b31a53d49055e500356c7ce3430e58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validation-known-issues"></a>Problemas conocidos de la validación
Esta sección contiene información útil que puede ayudarle a evitar errores de validación.  
  
## <a name="disabling-xml-validation"></a>Cómo deshabilitar la validación de XML  
 Los "segmentos de cuerpo validar" se marcan en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración controla la validación de cuerpo XML y no se incluya la validación de delimitadores inesperados y delimitadores finales. Si un mensaje no tiene los delimitadores correcta, el mensaje no se puede analizar correctamente. Si un mensaje no se puede analizar correctamente, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no se puede generar el XML intermedio válido. Deshabilitar la marca "Validar cuerpo segmentos" genera lo siguiente:  
  
1.  Campos obligatorios vacíos.  
  
2.  Tipos de datos no ha validado.  
  
3.  No se valida la estructura de segmento (no se valida el orden de los segmentos).  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2. Confirmaciones de XML con varios errores se considerará no válido  
 Si una entrada V2. Mensaje XML que contiene más de un error, el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) analizador puede generar un V2. Confirmación (ACK) del XML con más de un error en el campo de error. Este tipo V2. XML ACK se producirá un error de validación, porque el estándar HL7 especifica que el analizador puede informar solo error en una V2. Campo de error de XML ACK.  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a>Se registran dos errores de análisis cuando mensajes del lote en / lote Out escenario contiene errores de validación  
 Cuando el primer mensaje en el lote en / escenario de lote Out (varios mensajes por lotes sin encabezados de lote) contiene errores de validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registra dos errores en el registro de eventos. El primer error pertenece al primer mensaje en el lote y el segundo error pertenece al resto de los mensajes.  
  
## <a name="restrictions-in-validating-field-length"></a>Restricciones en la validación de longitud de campo  
 Campos asociados con tipos de datos complejos están compuestos de componentes y subcomponentes de HL7. Las reglas de HL7 especifican la longitud y definir la opcionalidad como en el nivel de campo y no en el nivel de componente o subcomponente. Por ejemplo en V2.4, HL7 rige MSH3 para que sea del tipo de datos de alta definición y la longitud máxima de 180 caracteres. HD es un tipo de datos compuestos con el conjunto de HD1 tal cual, conjunto de HD2 como ST y HD3 conjunto como identificador. La restricción de longitud de campo implica que los datos de los tres componentes (incluidos los separadores de dos componentes) deben ser menor o igual a 180. Sin embargo, no se especifica la opcionalidad de los tres tipos de datos; lo que significa que pueden haber algunos o todos los componentes. Además, los tipos de datos ST y IS son definidos por el usuario y, por tanto, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no puede ser consciente de la distribución de longitud a través de los tres componentes, puesto que normalmente se sitio definido.  
  
 Debido a estas y otras complicaciones, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no valida la longitud de campo. Sin embargo, puede aplicar las restricciones de longitud en cada componente o subcomponente individual (de simple de tipo de datos) utilizando el Editor de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]validará estos durante el procesamiento.  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a>Validación del lote y el archivo encabezados/finalizadores se ven afectados por la habilitación de fragmentación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]no valida los encabezados/finalizadores por lotes y el archivo cuando el campo FHS3 contiene una entidad que tiene habilitada la fragmentación.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)