---
title: "Cómo generar mensajes de instancia | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff74c67a-7e73-4153-9ec4-e6e50464ee92
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a911e4b0f1167e8ec200dad65b8dacb94bb08be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-generate-instance-messages"></a>Cómo generar mensajes de instancia
Una vez creado un esquema, una forma de comprobar el trabajo es generar un mensaje de instancia de ejemplo a partir del esquema. Examinar un mensaje de instancia es mucho más sencillo en muchos sentidos que mirar el árbol de esquema o la representación del esquema en el lenguaje de definición de esquemas XML (XSD). El motivo es que el esquema debe describir todas las variaciones posibles de los mensajes de instancia correspondientes y que un mensaje de instancia concreto solo debe expresar algunos datos mediante el formato especificado por el esquema. El mensaje de instancia generado es una muestra y no puede mostrar todas las estructuras definidas por el esquema correspondiente.  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a>Para especificar de forma explícita que un archivo debe contener el mensaje de instancia generado  
  
1.  En el Explorador de soluciones, haga clic en el esquema para el que desea generar un mensaje de instancia y, a continuación, haga clic en **propiedades**.  
  
2.  Si es necesario, en la ventana Propiedades, expanda el **General** sección de la **General** ficha haciendo clic en su signo más (+) icono.  
  
3.  En el **nombre de archivo de instancia de salida** campo de valor de propiedad, escriba el nombre de un archivo o utilice el botón de puntos suspensivos (**...** ) situado en el extremo derecho del campo de valor para buscar un archivo en el que se colocarán los mensajes de instancia generado y, a continuación, haga clic en **guardar**.  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a>Para especificar el tipo del mensaje de instancia generado  
  
1.  En el Explorador de soluciones, haga clic en el esquema para el que desea generar un mensaje de instancia y, a continuación, haga clic en **propiedades**.  
  
2.  Si es necesario, en la ventana Propiedades, expanda el **General** sección de la **General** ficha haciendo clic en su signo más (+) icono.  
  
3.  En el **genere el tipo de salida de instancia** campo de valor de propiedad, use la lista desplegable lista para seleccionar **XML** o **nativo** como el tipo del que se genere el mensaje de instancia.  
  
     **XML** es el valor predeterminado.  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a>Para generar un mensaje de instancia de ejemplo para un esquema  
  
1.  En el Explorador de soluciones, haga clic en el esquema para el que desea generar un mensaje de instancia y, a continuación, haga clic en **generar instancia**.  
  
2.  En la ventana Resultados, vea los resultados. En esta ventana se muestran mensajes para indicar si la operación ha sido correcta o no.  
  
> [!NOTE]
>  Si la ventana Resultados o la ventana Lista de tareas no se abre ni muestra información acerca de si la generación de la instancia se ha realizado correctamente o no, puede abrirla manualmente. Para obtener más información acerca de cómo administrar estas ventanas, vea [administrar otras ventanas de Visual Studio](../core/how-to-manage-other-visual-studio-windows.md).  
  
> [!NOTE]
>  Si no especifica un valor para el **referencia raíz** propiedad, el Editor de BizTalk genera un mensaje de instancia de ejemplo para el primer nodo raíz del esquema. Si especifica un valor para el **referencia raíz** propiedad, el Editor de BizTalk genera un mensaje de instancia de ejemplo para ese nodo raíz.  
  
> [!NOTE]
>  En algunos casos, los mensajes de instancia generados desde un esquema concreto no pueden pasar la validación con ese mismo esquema. Para obtener más información acerca de estos casos, consulte [problemas conocidos relacionados con la validación y generación de esquema](../core/known-issues-with-schema-generation-and-validation.md). En general, es conveniente editar un mensaje de instancia generado y cambiar los datos que contiene para que represente el escenario más realista. A continuación, use ese mensaje de instancia modificado para validar el esquema.  
  
## <a name="see-also"></a>Vea también  
 [Comprobación de esquemas](../core/testing-schemas.md)   
 [Validación de esquemas](../core/schema-validation1.md)   
 [Validación y generación de mensajes de instancia](../core/instance-message-generation-and-validation.md)