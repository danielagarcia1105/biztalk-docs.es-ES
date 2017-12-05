---
title: "Cómo abrir, guardar, cerrar y cambiar el nombre de los mapas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9383dd3751f9ccdd7790b0215e596eba95dc4a45
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-open-save-close-and-rename-maps"></a>Cómo abrir, guardar, cerrar y cambiar el nombre de asignaciones
En Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las asignaciones existen como archivos en el sistema de archivos con la extensión .btm. No obstante, es mucho más habitual trabajar con asignaciones como elementos de un proyecto de BizTalk, desde el que lleva a cabo operaciones como abrir, guardar y cerrar asignaciones.  
  
### <a name="to-open-a-map"></a>Para abrir una asignación  
  
1.  En el Explorador de soluciones, seleccione la asignación que desea abrir.  
  
2.  En el **vista** menú, haga clic en **abiertos**.  
  
     Se abre la asignación en el Asignador de BizTalk.  
  
    > [!NOTE]
    >  Puede también haga clic en la asignación en el Explorador de soluciones y, a continuación, haga clic en **abiertos**, o simplemente haga doble clic en la asignación en el Explorador de soluciones.  
  
### <a name="to-save-a-map"></a>Para guardar una asignación  
  
1.  En el Explorador de soluciones, seleccione la asignación que desea guardar.  
  
2.  En el **archivo** menú, haga clic en **guardar  *\<de asignación de nombre de\>***.  
  
### <a name="to-save-a-map-to-a-new-location"></a>Para guardar una asignación en una nueva ubicación  
  
1.  En el Explorador de soluciones, seleccione la asignación que desea guardar en una nueva ubicación.  
  
2.  En el **archivo** menú, haga clic en **guardar  *\<de asignación de nombre de\>*  como**.  
  
3.  En el **Guardar archivo como** cuadro de diálogo, vaya a la ubicación de la carpeta donde desea guardar el mapa.  
  
4.  En el **nombre de archivo** , escriba un nombre para el archivo y, a continuación, haga clic en **guardar**.  
  
    > [!IMPORTANT]
    >  No utilice los siguientes nombres para asignaciones: "XmlContent", "SourceSchemas", "TargetSchemas" o "XsltArgumentListContent"; por lo tanto, al hacerlo se producirán problemas de compilación en el código C# generado en el ensamblado .NET correspondiente. Para obtener información acerca de problemas y su solución, vea [solución de problemas de mapas](../core/troubleshooting-maps.md).  
  
### <a name="to-rename-a-map"></a>Para cambiar el nombre de una asignación  
  
1.  En el Explorador de soluciones, haga clic en la asignación que desea cambiar y, a continuación, haga clic en **cambiar el nombre de**.  
  
2.  En el cuadro de edición que aparece en la ubicación de la asignación en el Explorador de soluciones, escriba el nuevo nombre de la asignación o modifique el existente y, a continuación, presione ENTRAR.  
  
> [!NOTE]
>  También puede cambiar la **nombre de tipo** del mapa cuando se cambia el nombre. Cambia el **nombre de tipo** seleccionando el **mapa** en el Explorador de soluciones y escribiendo el nuevo nombre en el **nombre de tipo** en la ventana Propiedades.  
  
#### <a name="to-close-a-map"></a>Para cerrar una asignación  
  
1.  En el Explorador de soluciones, seleccione la asignación que desea cerrar.  
  
2.  En el menú **Archivo** , haga clic en **Cerrar**.  
  
    > [!NOTE]
    >  También puede hacer clic en el icono Cerrar ([**x**]) en la esquina superior derecha de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de edición.  
  
## <a name="see-also"></a>Vea también  
 [Administración de asignaciones en proyectos](../core/managing-maps-within-projects.md)