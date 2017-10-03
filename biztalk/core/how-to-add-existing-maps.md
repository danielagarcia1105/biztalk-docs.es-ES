---
title: "Cómo agregar asignaciones existentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fbeaea05-016e-488c-90f3-af8c6b9a3d84
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a61fb0faf5f4eed614257361b00cea781db2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-existing-maps"></a>Cómo agregar asignaciones existentes
Habrá ocasiones en las que desee agregar una asignación existente a un proyecto de BizTalk. Antes de hacerlo, debe asegurarse de que los esquemas de origen y de destino de la asignación están incluidos en el proyecto de BizTalk al que va a agregar la asignación o al menos deben tener una referencia en el ensamblado .NET correspondiente.  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a>Para agregar un asignación ya existente a un proyecto de BizTalk  
  
1.  Haga clic en un proyecto de BizTalk en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
2.  En el **Agregar elemento existente** cuadro de diálogo, busque la carpeta que contiene el mapa para agregar, selecciónelo y, a continuación, haga clic en **agregar**.  
  
     Se abre la asignación en el Asignador de BizTalk. La asignación que acaba de agregar también aparece como un elemento secundario del proyecto actual de BizTalk en el Explorador de soluciones.  
  
    > [!NOTE]
    >  Si abrió otra carpeta distinta de la del proyecto de BizTalk, en la carpeta del proyecto se creó una copia de la asignación que agregó, y esta es la copia que se agregó al proyecto. Los cambios posteriores a esta asignación se realizan en esta copia, no en la asignación original en la otra carpeta.  
  
    > [!IMPORTANT]
    >  Las asignaciones de BizTalk solo se pueden abrir con el Asignador de BizTalk, el cual se hospeda dentro del shell de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Si hace doble clic en una asignación en el Explorador de Windows, se abre una nueva instancia de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y el Asignador de BizTalk abrirá la asignación, siempre y cuando los esquemas correspondientes se carguen correctamente.  
  
    > [!NOTE]
    >  Si el mapa existente contiene functoids personalizados, los DLL correspondientes deberán copiarse a la carpeta "%BTSINSTALLPATH%\Developer Tools\Mapper Extensions". En caso contrario, la asignación no se cargará y lanzará un error debido a no poder cargar functoids personalizados.  
  
## <a name="see-also"></a>Vea también  
 [Administrar asignaciones en proyectos](../core/managing-maps-within-projects.md)   
 [Desarrollar Functoids personalizados](../core/developing-custom-functoids.md)