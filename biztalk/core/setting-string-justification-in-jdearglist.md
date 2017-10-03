---
title: "Establecer la justificación de cadena en Jdearglist | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, setting string justification
- strings, configuring
- strings, right-justified
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daecf4101ebf5dc8964562dc7f385d41279a3401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-string-justification-in-jdearglist"></a>Configuración de la justificación de cadena en Jdearglist
Para configurar determinados argumentos de cadena como justificados a la derecha (y rellenos a la izquierda) en el archivo JD Edwards OneWorld jdearglist.txt, debe saber a qué función empresarial desea acceder y, específicamente, debe saber qué campos de la función empresarial desea llamar.  
  
 Debe actualizar jdearglist.txt antes de generar los enlaces (esquemas) en la orquestación. Las instrucciones para actualizar el archivo jdearglist.txt se describen en [control de valores de cadena](../core/handling-string-values1.md).  
  
 Si recibe un mensaje de advertencia de jdearglist.txt en el registro de auditoría, le informará de que falta el archivo jdearglist.txt. Si ejecuta las funciones empresariales SalesOrder o PurchaseOrder, debe tener el archivo en su RUTA DE ACCESO para que funcione.  
  
## <a name="see-also"></a>Vea también  
 [Administración de BizTalk Adapter para JD Edwards OneWorld](../core/administering-biztalk-adapter-for-jd-edwards-oneworld.md)