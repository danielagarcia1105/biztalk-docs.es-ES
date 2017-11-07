---
title: "Establecer justificación de cadena en el adaptador de JD Edwards OneWorld | Documentos de Microsoft"
description: "Actualizar archivo jdearglist para utilizar el adaptador de JD Edwards OneWorld en una orquestación de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b32d0106d95a1970b480e32dfa47a81ebf98ca
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="set-string-justification-in-jdearglist"></a>Establezca la justificación de cadena en Jdearglist

## <a name="overview"></a>Información general
Para configurar determinados argumentos de cadena como justificados a la derecha (y rellenos a la izquierda) en el archivo JD Edwards OneWorld jdearglist.txt, debe saber a qué función empresarial desea acceder y, específicamente, debe saber qué campos de la función empresarial desea llamar.  
  
 Debe actualizar jdearglist.txt antes de generar los enlaces (esquemas) en la orquestación. Las instrucciones para actualizar el archivo jdearglist.txt se describen en [control de valores de cadena](../core/handling-string-values1.md).  
  
 Si recibe un mensaje de advertencia de jdearglist.txt en el registro de auditoría, le informará de que falta el archivo jdearglist.txt. Si ejecuta las funciones empresariales SalesOrder o PurchaseOrder, debe tener el archivo en su RUTA DE ACCESO para que funcione.  
  
## <a name="see-also"></a>Vea también  
[Uso del control de excepciones de BizTalk Server](using-biztalk-server-exception-handling1.md)