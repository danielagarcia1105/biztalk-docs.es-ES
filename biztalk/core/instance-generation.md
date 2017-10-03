---
title: "Generación de la instancia | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14060dca-5e14-474a-bf2c-4e8bc56e3c61
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bd3d2bc6852ec0c73fbbe4ffc55924a8012ce5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instance-generation"></a>Generación de instancias
El Editor de BizTalk, se invoca el **IInstanceGenerator.GenerateInstance** método de una extensión cuando se cumplen las condiciones siguientes:  
  
-   La extensión está establecida como estándar mediante el uso de la **estándar** propiedad de la **esquema** nodo.  
  
-   En el **páginas de propiedades** cuadro de diálogo asociado con el esquema, el **genere el tipo de salida de instancia** propiedad está establecida en **nativo.**  
  
-   En el **páginas de propiedades** asociado con el esquema, el cuadro de diálogo la **nombre de archivo de instancia de salida** propiedad se establece en el nombre del archivo que se guardará en la instancia de salida.  
  
> [!NOTE]
>  Si el **nombre de archivo de instancia de salida** propiedad no está establecida, se utiliza un nombre de archivo predeterminado en una carpeta temporal para el mensaje de instancia generado y se proporciona un vínculo a él en la ventana de salida.  
  
 Antes de la **IInstanceValidator.ValidateInstance** se llama al método, el Editor de BizTalk genera un mensaje de instancia XML de ejemplo y, a continuación, se pasa y el archivo especificado en el **nombre de archivo de instancia de salida** propiedad o un nombre de archivo predeterminado, a ese método.  
  
 Si se producen errores, mensajes de error se devuelven como una matriz de **IValidationInfo** objetos y se muestran en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Lista de tareas.  
  
## <a name="see-also"></a>Vea también  
 [Extender el Editor de BizTalk](../core/extending-biztalk-editor.md)