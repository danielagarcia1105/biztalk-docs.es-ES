---
title: Operadores lógicos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3b3c187e353babafd86590fdeacdc19fc115b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262076"
---
# <a name="logical-operators"></a>Operadores lógicos
El Marco de trabajo de reglas de negocio admite el uso de los operadores lógicos Y, O y NO en la creación de reglas de negocio. En la tabla siguiente se describen los operadores lógicos.  
  
|Operador lógico|Description|  
|----------------------|-----------------|  
|**AND**|Devuelve **true** si ambos operandos se evalúan como **true**; de lo contrario devuelve **false**.|  
|**OR**|Devuelve **true** si uno de los operandos se evalúa como **true**, de lo contrario devuelve **false**.|  
|**NOT**|Devuelve **true** si el operando se evalúa como **false**, de lo contrario devuelve **false**.|  
  
 Cuando los operandos son de tipos diferentes, el motor de reglas convierte el tipo de uno de los parámetros para que coincida con el tipo del otro parámetro, o bien convierte los dos parámetros a un tipo común antes de evaluar la expresión.  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>Para usar un operador lógico en una regla de negocios  
 Use el siguiente procedimiento para usar un operador lógico en una regla de negocios.  
  
1.  En el **IF** panel del compositor de reglas de negocio, haga clic en el **condiciones** nodo y, a continuación, seleccione el operador lógico que desea agregar a la expresión lógica.  
  
2.  Haga clic con el botón secundario en el operador lógico y agregue los predicados o los operadores lógicos anidados que desee.  
  
## <a name="see-also"></a>Vea también  
 [Operadores aritméticos](../core/arithmetic-operators.md)