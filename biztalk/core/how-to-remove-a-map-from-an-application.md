---
title: "Cómo quitar una asignación de una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, maps
- deleting, maps
- managing [maps], deleting
- managing [maps], applications
ms.assetid: 27d9bb08-36f0-46ff-ae9a-2247be6e3f96
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b264809306e2cda40cc44be1287b6c2426fb43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-map-from-an-application"></a>Cómo quitar una asignación de una aplicación
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para quitar una asignación de una aplicación de BizTalk. Puede ser conveniente quitar una asignación después de implementar una versión nueva de ella. Para obtener más información y consideraciones importantes para actualizar artefactos de la aplicación, consulte [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md).  
  
 Al quitar una asignación, ocurre lo siguiente:  
  
-   La asignación se elimina de la base de datos de administración de BizTalk.  
  
-   El ensamblado de BizTalk que contiene la asignación se elimina de la base de datos de administración de BizTalk, aunque no se quita del sistema de archivos local ni de la caché de ensamblados global (GAC), si existe en estas ubicaciones.  
  
-   Como consecuencia de la eliminación del ensamblado de BizTalk, también se quitan de la base de datos de administración de BizTalk todos los artefactos que contiene el ensamblado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-remove-a-map"></a>Para quitar una asignación  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la asignación para quitar y, a continuación, expanda la aplicación que contiene la asignación.  
  
3.  Haga clic en el **mapas** carpeta, haga clic en el mapa y, a continuación, haga clic en **quitar**.  
  
> [!NOTE]
>  Para quitar varias asignaciones, mantenga presionada la tecla MAYÚS, haga clic en cada asignación para quitar, haga clic en una de las asignaciones y, a continuación, haga clic en **quitar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de mapas](../core/managing-maps.md)   
 [Cómo quitar un ensamblado de BizTalk desde una aplicación](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)   
 [Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md)