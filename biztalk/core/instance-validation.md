---
title: Validación de instancia | Documentos de Microsoft
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
ms.openlocfilehash: 3db1903030bbde96f2587ac14b5d168345b31823
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257380"
---
# <a name="instance-validation"></a>Validación de instancia
El Editor de BizTalk, se invoca el **IInstanceValidator.ValidateInstance** método de una extensión cuando se cumplen las condiciones siguientes:  
  
-   La extensión está establecida como estándar mediante el uso de la **estándar** propiedad de la **esquema** nodo.  
  
-   En el **páginas de propiedades** cuadro de diálogo asociado con el esquema, el **genere el tipo de salida de instancia** propiedad está establecida en **nativo.**  
  
-   En el **páginas de propiedades** cuadro de diálogo asociado con el esquema, el **nombre de archivo de instancia de entrada** propiedad se establece en el nombre de un archivo que contiene el mensaje de instancia que se debe validar.  
  
 El archivo especificado en el **nombre de archivo de instancia de entrada** propiedad se pasa como un parámetro a la **IInstanceValidator.ValidateInstance** método.  
  
 Si se producen errores, mensajes de error se devuelven como una matriz de **IValidationInfo** objetos y se muestran en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Lista de tareas.  
  
> [!NOTE]
>  Si el esquema contiene instrucciones pattern y el archivo pasado a la **ValidateInstance** método generado mediante la correspondiente **generar instancia** comando, no puede pasar el mensaje de instancia validación.  
  
## <a name="see-also"></a>Vea también  
 [Extender el Editor de BizTalk](../core/extending-biztalk-editor.md)