---
title: Compatibilidad con los ceros iniciales de validaciones de campo de cantidad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- amounts, amount fields
- amounts, leading zeros
- validating, amount fields
ms.assetid: 7c202422-019f-43da-9c2a-4b9fdf0b2859
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1de45b5acbc780fad0847ab207d0d5c72ca2a652
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a>Compatibilidad con los ceros iniciales de validaciones de campo de cantidad
Las directivas de validación de algunos tipos de mensaje realizan validaciones en los campos de cantidad. Para habilitar los ceros a la izquierda en los campos de cantidad, debe modificar la directiva de validación para el tipo de mensaje. Puede crear una nueva versión de la directiva de validación de forma predeterminada y editar el argumento en el Compositor de reglas de negocios, o puede modificar la directiva predeterminada manualmente en un editor de texto antes de implementa la directiva.  
  
 En la tabla siguiente se enumera los métodos que habilitan o deshabilitan ceros a la izquierda. La tabla también indica el número ordinal del argumento que se debe establecer en el método. Establézcala en True para permitir ceros a la izquierda o en False para deshabilitarlo.  
  
|Método|Número de argumento|  
|------------|---------------------|  
|**CheckValidAmount**|6|  
|**CheckCurrencyAmount**|4|  
|**CheckValidSignCurrencyAmount**|3|  
|**CheckValidSignDateCurrencyAmount**|4|  
|**IsValidTransactionDetailsCurrencyAmount**|4|  
  
 Cada método en la tabla anterior se encuentra en una o varias directivas de validación de mensajes. Para establecer el argumento en una directiva, debe buscar en el nombre del método para comprobar si la directiva lo contiene. Un método puede aparecer varias veces en la directiva de un mensaje.  
  
### <a name="to-enable-or-disable-leading-zeros"></a>Para habilitar o deshabilitar los ceros a la izquierda  
  
1.  Abra un editor de texto, como el Bloc de notas.  
  
2.  En el editor, vaya a la ubicación de la directiva de validación de mensaje en el que desea habilitar o deshabilitar los ceros a la izquierda. Por ejemplo, puede encontrar la directiva de validación de mensajes para el tipo de mensaje MT103, MT103_Validation_Policy.xml, en  *\<unidad >*: / programa archivos/Microsoft BizTalk Accelerator for SWIFT/SWIFT mensajes/categoría 1 / MT103. Abra la directiva de validación.  
  
3.  En la directiva, busque en el **CheckValidAmount** método.  
  
4.  Si se encuentra el método, se cuentan hacia abajo para el argumento correspondiente. Por ejemplo, para la **CheckValidAmount** recuento hasta el sexto argumento del método. Establezca el argumento en **True** para habilitar ceros iniciales ni False para deshabilitarlo.  
  
5.  Repita los pasos 3 y 4 para cada método en la tabla anterior.  
  
6.  Guarde el archivo y, a continuación, cierre el editor.