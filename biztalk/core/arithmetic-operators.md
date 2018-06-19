---
title: Operadores aritméticos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73e153c-aac1-4cea-92d8-af4a1bea6e6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3d66a990437929176835228efa1a74a5fa8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230524"
---
# <a name="arithmetic-operators"></a>Operadores aritméticos
El marco de trabajo de reglas de negocios admite el uso de los operadores de suma, resta, multiplicación, división y resto (módulo) para la creación de reglas de negocios. En la tabla siguiente se describen los operadores aritméticos.  
  
|Operador aritmético|Description|  
|-------------------------|-----------------|  
|**Agregar**|Representa el operador de suma (arg1 sumado a arg2).|  
|**Restar**|Representa el operador de resta (arg1 restado de arg2).|  
|**Multiplicar**|Representa el operador de multiplicación (arg1 multiplicado por arg2).|  
|**Divide**|Representa el operador de división (arg1 dividido entre arg2).|  
|**Resto**|Representa el operador de resto (arg1 módulo arg2).|  
  
 Cuando los operandos son de diferentes tipos se produce una promoción numérica automática, en la que el tipo de operando más pequeño se convierte en el tipo de operando mayor. Por ejemplo, si la **agregar** operador se usa con el primer operando de **int** tipo y el segundo operando del **largo** tipo, el tipo del primer operando se convierte en **largo** antes de realizar la **agregar** operación. El motor de reglas también admite la promoción doble si ambos operandos se pueden promocionar a un tipo común. Por ejemplo, si la **agregar** operador se usa con el primer operando de **int** tipo y el segundo operando del **uint** tipo, los tipos de ambos operandos se convierten en **long** antes de realizar la **agregar** operación.  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>Para usar un operador lógico en una regla de negocios  
 Use el siguiente procedimiento para usar un operador lógico en una regla de negocios.  
  
1.  En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.  
  
2.  Expanda **vocabularios**, expanda **funciones**, expanda **versión 1.0 - publicada**y, a continuación, arrastre el **agregar/restar/multiplicar/dividir/aviso** al panel condiciones o acciones de panel.  
  
3.  Especifique valores para los operadores izquierdo y derecho.  
  
## <a name="see-also"></a>Vea también  
 [Operadores lógicos](../core/logical-operators.md)