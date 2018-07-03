---
title: Problemas conocidos de validación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73cc1caa3207901780a57e7b1213215217b73326
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010581"
---
# <a name="validation-known-issues"></a>Problemas conocidos de validación
Esta sección contiene información útil que puede ayudar a evitar errores de validación.  
  
## <a name="disabling-xml-validation"></a>Deshabilitar la validación de XML  
 Los "segmentos cuerpo validar" marca en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración controla la validación de cuerpo XML y no incluye la validación de delimitadores inesperados y delimitadores finales. Si un mensaje no tiene los delimitadores adecuados, el mensaje no puede analizarse correctamente. Si no se puede analizar correctamente un mensaje, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no se puede generar el XML intermedio válido. Deshabilitar la marca "Validar cuerpo segmentos" da como resultado lo siguiente:  
  
1.  Campos obligatorios vacíos.  
  
2.  No validados los tipos de datos.  
  
3.  No se valida la estructura de segmento (no se valida el orden de los segmentos).  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2. Se producirá un error de confirmaciones de XML con varios errores de validación  
 Si una entrada V2. Mensaje XML que contiene más de un error, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) analizador puede generar un V2. Confirmación (ACK) de XML con más de un error en el campo de error. Este tipo una V2. XML ACK se producirá un error de validación, porque el estándar HL7 especifica que el analizador puede informar de un único error en un V2. Campo de error de XML ACK.  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a>Se registran dos errores de análisis cuando los mensajes del lote en / escenario de lote Out contienen errores de validación  
 Cuando el primer mensaje en el lote en / escenario de lote horizontal (varios mensajes por lotes sin encabezados de lote) contiene errores de validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registra dos errores en el registro de eventos. El primer error pertenece al primer mensaje en el lote, y el segundo error pertenece al resto de los mensajes.  
  
## <a name="restrictions-in-validating-field-length"></a>Restricciones en la validación de longitud de campo  
 Campos asociados con tipos de datos complejos están compuestos de componentes y subcomponentes de HL7. Las reglas de HL7 especifican la longitud y la opcionalidad en el nivel de campo y no en el nivel de componente o subcomponente. Por ejemplo, en V2.4, HL7 rige MSH3 para que sea del tipo de datos de alta definición y la longitud máxima de 180 caracteres. HD es un tipo de datos compuestos con HD1 conjunto tal cual, HD2 conjunto como ST y HD3 conjunto como identificador. La restricción de longitud de campo implica que los datos de los tres componentes (incluidos los separadores de componentes de dos) deben ser menor o igual que 180. Sin embargo, no se especifica la opcionalidad de los tres tipos de datos; lo que significa que pueden haber algunos o todos los componentes. Además, los tipos de datos ST y IS son definidos por el usuario y, por tanto, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no puede ser consciente de la distribución de longitud de entre los tres componentes, ya que estas son normalmente sitio definido.  
  
 Debido a estas y otras complicaciones, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no valida la longitud de campo. Sin embargo, puede aplicar restricciones de longitud en cada componente o subcomponente individual (de simple del tipo de datos) mediante el Editor de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se validará estas durante el procesamiento.  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a>Validación del lote y el archivo de encabezados/finalizadores se ven afectados por la habilitación de fragmentación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no valida el lote y el archivo de encabezados/finalizadores cuando el campo FHS3 contiene una entidad que tiene habilitada la fragmentación.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)