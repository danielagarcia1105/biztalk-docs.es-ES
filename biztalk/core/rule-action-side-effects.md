---
title: Efectos secundarios de acciones de regla | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, side effects
ms.assetid: 1ef65014-9c0a-40d3-b941-2a67c20b54d3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ed890ca8efca6fdd1403c4ec89f4c0c5d32eaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="rule-action-side-effects"></a>Efectos secundarios de acciones de reglas
Si la ejecución de una acción afecta al estado de un objeto o a un término empleado en las condiciones, se considera que dicha acción tiene un efecto secundario sobre el objeto.  
  
 Suponga que tenemos las siguientes reglas:  
  
## <a name="rule-1"></a>Regla 1  
  
```  
IF OrderForm.ItemCount > 100   
THEN OrderForm.Status = "important"  
```  
  
## <a name="rule-2"></a>Regla 2  
  
```  
IF OrderList.IsFromMember = true   
THEN OrderForm.UpdateStatus("important")  
```  
  
 En este caso, **OrderForm.UpdateStatus** se dice que tiene un efecto secundario **OrderForm.Status**. Esto no significa que **OrderForm.UpdateStatus** tiene efectos secundarios; en su lugar, **OrderForm.Status** potencialmente se ve afectado por una o varias acciones.  
  
 De forma predeterminada, el **SideEffects** propiedad para los miembros de clase de .NET es **true**, que impide que el motor de reglas de almacenamiento en caché el miembro con efectos secundarios. En nuestro ejemplo, el motor de reglas no almacena en caché **OrderForm.Status** en la memoria de trabajo, sino que obtiene el valor más actualizado de **OrderForm.Status** cada vez que se evalúa la regla 1. Si el **SideEffects** propiedad está establecida en **false**, el motor de reglas almacena en caché el valor de la primera vez que se evalúa como **OrderForm.Status**, pero para evaluaciones posteriores (en escenarios de encadenamiento directo), utiliza el valor almacenado en caché.  
  
 Actualmente el Compositor de reglas de negocio no proporciona una manera para que los usuarios modifiquen **SideEffects**, sin embargo, sólo se puede establecer la **SideEffects** propiedad mediante programación con el marco de trabajo de reglas de negocios . Se realiza esto en el enlace, mediante el [ClassMemberBinding](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.aspx) clase para especificar métodos de objetos, propiedades y campos que se usan en condiciones de regla y las acciones. **ClassMemberBinding** tiene una propiedad, [SideEffects](https://msdn.microsoft.com/library/microsoft.ruleengine.classmemberbinding.sideeffects.aspx#P:Microsoft.RuleEngine.ClassMemberBinding.SideEffects), que contiene un valor booleano que indica si obtiene acceso al miembro cambia su valor.  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas](../core/rule-engine.md)