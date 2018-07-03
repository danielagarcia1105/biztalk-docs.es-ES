---
title: Validación de instancia | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906f2e9-2bf9-448b-927f-dd2d7d9b2272
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f4e4901d11bda5fb6633c00dd72899ee1b72db4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012877"
---
# <a name="instance-validation"></a>Validación de instancia
Editor de BizTalk invoca el **IInstanceValidator.ValidateInstance** método de una extensión cuando se cumplen las condiciones siguientes:  
  
- La extensión está establecida como estándar mediante el uso de la **estándar** propiedad de la **esquema** nodo.  
  
- En el **páginas de propiedades** cuadro de diálogo asociado con el esquema, el **genere el tipo de salida de instancia** propiedad está establecida en **nativo.**  
  
- En el **páginas de propiedades** cuadro de diálogo asociado con el esquema, el **nombre de archivo de instancia de entrada** propiedad está establecida en el nombre de un archivo que contiene el mensaje de instancia que se va a validar.  
  
  El archivo especificado en el **nombre de archivo de instancia de entrada** propiedad se pasa como parámetro a la **IInstanceValidator.ValidateInstance** método.  
  
  Si se producen errores, mensajes de error se devuelven como una matriz de **IValidationInfo** objetos y se muestran en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Lista de tareas.  
  
> [!NOTE]
>  Si el esquema contiene instrucciones pattern y el archivo pasa a la **ValidateInstance** generado con el correspondiente método **generar instancia** comando, no puede pasar el mensaje de instancia validación.  
  
## <a name="see-also"></a>Vea también  
 [Ampliar el Editor de BizTalk](../core/extending-biztalk-editor.md)