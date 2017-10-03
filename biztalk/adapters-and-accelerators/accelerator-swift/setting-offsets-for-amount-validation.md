---
title: "Establecer los desplazamientos para la validación de cantidad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- amounts, validating
- validating, amounts
- amounts, offsets
- offsets
ms.assetid: 39d5510c-52e6-4fd9-9632-582b508f04d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaa41714cbe5c3baba85e82f2992ff72544c425c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-offsets-for-amount-validation"></a>Configuración de desplazamientos para la validación de cantidad
Las reglas de uso para los campos de cantidad de tipos de mensaje MT102, MT103 y MT103PLUS se validan las reglas en las directivas de validación correspondiente. Los campos de cantidad pueden coincidir exactamente o pueden comprobar que está dentro del intervalo de cantidades.  
  
 Para habilitar la validación dentro de un intervalo, se especifica un porcentaje de desplazamiento en la llamada al método en la directiva de validación pertinentes. Por ejemplo, si la cantidad que se establece para el campo es 100 y el porcentaje de desplazamiento es 10 por ciento, una cantidad válida sería cualquier valor entre 90 y 110, ambos inclusive. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]proporciona esta compatibilidad para los tipos de mensaje MT102, MT102PLUS y MT103.  
  
 Se especifica el porcentaje de desplazamiento en la vista la **IsValidSettlementAmount** o **IsValidInterbankSettledAmount** método en la directiva de validación. El **IsValidSettlementAmount** método implementa la regla de uso de los campos de cantidad de mensajes MT102 y MT102PLUS. El **IsValidInterbankSettledAmount** método implementa la regla de uso de los campos de cantidad de mensajes de MT103. Especifique el porcentaje de desplazamiento en el argumento OffsetPercent, que es el décimo argumento de uno de estos métodos.  
  
 Cuando se establece, el desplazamiento de porcentaje se aplica a los campos siguientes:  
  
|Tipo de mensaje|Validada con desplazamientos de campos|  
|------------------|-----------------------------------|  
|MT102 o MT102PLUS|32<br /><br /> 33B|  
|MT103|19, secuencia de C<br /><br /> 31a, secuencia de C<br /><br /> 72G|  
  
### <a name="to-set-an-offset-percentage"></a>Para establecer un porcentaje de desplazamiento  
  
1.  Abra un editor de texto, como el Bloc de notas.  
  
2.  En el editor, vaya a la ubicación de la directiva de validación de mensaje en el que desea establecer un porcentaje de desplazamiento. Por ejemplo, puede encontrar la directiva de validación de mensajes para el tipo de mensaje MT103, MT103_Validation_Policy.xml, en  *\<unidad >*: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión > Mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión > \Category 1\MT103. Abra la directiva de validación.  
  
3.  En la directiva, buscar en IsValidSettlementAmount para mensajes MT102 y MT102PLUS o IsValidInterbankSettledAmount MT103 mensajes.  
  
4.  Cuenta atrás para el décimo argumento. Especifique el porcentaje de la posición de desplazamiento en el argumento.  
  
5.  Guarde el archivo y, a continuación, cierre el editor.