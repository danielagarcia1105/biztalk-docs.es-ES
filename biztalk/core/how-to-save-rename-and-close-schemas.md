---
title: "Cómo guardar, cambiar el nombre y cerrar esquemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65e15d9e-40ae-4850-9c13-88033cb3b3bb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a295bacf263e3ecad9a9aa081fb0d5d3be2f635
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-save-rename-and-close-schemas"></a>Cómo guardar, cambiar el nombre y cerrar esquemas
En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], los esquemas son archivos de lenguaje de definición de esquemas XML (XSD) y residen en el sistema de archivos con extensiones .xsd. Cuando utilice el Editor de BizTalk para desarrollar esquemas, tendrá que guardar y cerrar archivos de esquema como parte de la rutina; además, ocasionalmente, tendrá que cambiarles el nombre. En este tema se describen los pasos necesarios para realizar estas operaciones básicas.  
  
### <a name="to-save-a-schema"></a>Para guardar un esquema  
  
1.  Si es necesario, active el Editor de BizTalk para guardar el esquema. Para ello, haga clic en la ficha correspondiente que se encuentra en la parte superior de la ventana de edición principal de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  En el **archivo** menú, haga clic en **guardar  *\<nombre de esquema\>***.  
  
     Si el esquema tiene cambios sin guardar, el nombre mostrado en la ficha en la parte superior de la ventana de edición principal no terminará con un asterisco (*), que es el carácter utilizado para indicar que hay cambios sin guardar.  
  
> [!NOTE]
>  Puede guardar el esquema con un nombre nuevo, haga clic en **guardar  *\<nombre de esquema\>*  como** en el **archivo** menú.  
  
> [!NOTE]
>  Puede guardar el esquema como parte del proceso de guardar todos los elementos modificados en el proyecto, haga clic en **guardar todo** en el **archivo** menú.  
  
#### <a name="to-rename-a-schema"></a>Para cambiar el nombre de un esquema  
  
1.  En el Explorador de soluciones, haga clic en el esquema que desea cambiar y, a continuación, haga clic en **cambiar el nombre de**.  
  
2.  En el cuadro de edición que aparece en la ubicación del esquema en el Explorador de soluciones, escriba el nuevo nombre del esquema o modifique el nombre existente y, a continuación, presione ENTRAR.  
  
> [!NOTE]
>  También puede cambiar la **nombre de tipo** del esquema cuando cambia el nombre. Cambia el **nombre de tipo** seleccionando el **esquema** en el Explorador de soluciones y escribiendo el nuevo nombre en el **nombre de tipo** en la ventana Propiedades.  
  
> [!IMPORTANT]
>  No debe cambiar el nombre de ningún esquema que utilice otro esquema. Esto incluye los esquemas que se han incluido, importado o redefinido con otros esquemas, así como los esquemas de propiedades para los que se han establecido promociones. Si lo hace, el esquema no encontrará el esquema cuyo nombre ha cambiado, porque el nombre que contiene ya no es exacto.  
  
> [!NOTE]
>  Algunos de los nombres que se eligen para los archivos del proyecto, como los archivos de esquema, pueden producir más adelante errores de compilación debido a conflictos con palabras reservadas del lenguaje C# y con nombres de tipos y espacios de nombres de .NET Framework (como "System"). Entre los ejemplos de esquemas se incluyen schema.xsd, XmlContent y RootNodes. Esto es porque el **nombre de tipo** valores predeterminados de la propiedad a la parte (no es una extensión) base de la **Filename** propiedad. Puede solucionar este tipo de error de compilación, cambie explícitamente el valor de la **nombre de tipo** propiedad a algo que no entra en conflicto.  
  
#### <a name="to-close-a-schema"></a>Para cerrar un esquema  
  
1.  Si es necesario, active el Editor de BizTalk para cerrar el esquema. Para ello, haga clic en la ficha correspondiente que se encuentra en la parte superior de la ventana de edición principal de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  En el menú **Archivo** , haga clic en **Cerrar**.  
  
     Se cierra el Editor de BizTalk para el esquema que se ha cerrado.  
  
## <a name="see-also"></a>Vea también  
 [Administración de esquemas en proyectos](../core/managing-schemas-within-projects.md)