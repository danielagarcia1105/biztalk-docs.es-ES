---
title: "Cómo crear nuevas asignaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43b36cd8-f28e-4349-87d5-c94b7d8761bf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 910d79782f4332ae1d706e12a8c5dda8c399a41b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-new-maps"></a>Cómo crear asignaciones nuevas

## <a name="overview"></a>Información general
Para generar una nueva asignación de BizTalk hay que llevar a cabo tres pasos de nivel superior:  
  
1.  Crear la nueva asignación en un proyecto de BizTalk.  
  
2.  Agregue los esquemas de origen y destino para la asignación.  
  
3.  Generar el conjunto de vínculos y, posiblemente, functoids intermedios que especifiquen cómo se asigna el esquema de origen al esquema de destino.  
  
 En el contexto actual, los dos primeros pasos de los tres mencionados, se consideran "crear" la asignación. El tercer paso se considera "generar" la asignación. Para obtener instrucciones paso a paso acerca de muchas de las tareas relacionadas con el proceso de compilación del mapa, vea [utilizar Functoids para crear asignaciones más complejas](../core/using-functoids-to-create-more-complex-mappings.md).  
  
## <a name="create-a-new-map"></a>Crear una nueva asignación 
  
1.  Haga clic en un proyecto de BizTalk en el Explorador de soluciones, seleccione **agregar**y, a continuación, seleccione **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, en la **plantillas** área, seleccione **mapa**.  
  
3.  Seleccione el texto en el **nombre** cuadro, escriba un nombre para la asignación y, a continuación, seleccione **agregar**.  
  
     El Asignador de BizTalk se abre en la ventana de edición de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y muestra adyacentemente tres paneles diferenciados. De izquierda a derecha, estos paneles muestran el esquema de origen, la cuadrícula (que puede tener múltiples páginas) y el esquema de destino.  
  
    > [!IMPORTANT]
    >  No se puede usar los siguientes nombres para asignaciones: "XmlContent", "SourceSchemas", "TargetSchemas" o "XsltArgumentListContent". No pueden utilizarse estos nombres porque una compilación en un ensamblado .NET provoca restricciones de nombre como resultado del código C# generado.  
  
4.  En el asignador de BizTalk, en el panel izquierdo, seleccione **Abrir esquema de origen**.  
  
5.  En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquemas** nodo, seleccione el esquema de origen que corresponda y, a continuación, seleccione **Aceptar**.  

    > [!TIP] 
    > **A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede cambiar el tamaño de la ventana del selector de tipos para ver el nombre completo del esquema.
  
     Si solo existe una raíz del esquema de origen, o se ha establecido un nodo de raíz para el esquema mediante la **referencia raíz** propiedad de la **esquema** nodo, el esquema de origen se abre en el panel izquierdo y, puede continuar con el paso 7.  
  
6.  Si el esquema de origen tiene múltiples nodos raíz, y no se ha establecido ningún nodo de raíz para el esquema de origen mediante el **esquema** del nodo **referencia raíz** propiedad, en la **nodo raíz para el origen Esquema** cuadro de diálogo, seleccione el nodo raíz apropiado y seleccione **Aceptar**.  
  
    > [!IMPORTANT]
    >  Si elige un nodo raíz para un esquema en el asignador de BizTalk y después cambie la **referencia raíz** propiedad en el esquema, la próxima vez que abra el esquema en el asignador de BizTalk, el nodo raíz no se actualizará con la nueva referencia raíz configurada en el Editor de BizTalk.  
  
7.  En el asignador de BizTalk, en el panel derecho, seleccione **Abrir esquema de destino**.  
  
8.  En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquema** nodo en el árbol, si fuera necesario, seleccione el esquema de destino adecuado y, a continuación, seleccione **Aceptar**.  
  
     Si solo existe una raíz del esquema de destino, o se ha establecido un nodo de raíz para el esquema de destino mediante el **referencia raíz** propiedad de la **esquema** abre el nodo, el esquema de destino en el panel derecho, y no debe realizar el paso 9.  
  
9. Si el esquema de destino tiene múltiples nodos raíz, y no se ha establecido ningún nodo de raíz para el esquema de destino mediante el **referencia raíz** propiedad de la **esquema** nodo, en la **nodo raíz para el esquema de destino** cuadro de diálogo, seleccione el nodo raíz apropiado y seleccione **Aceptar**.  
  
     El esquema de destino se abre en el panel de la derecha.  
  
## <a name="see-also"></a>Vea también  
 [Administrar asignaciones en proyectos](../core/managing-maps-within-projects.md)