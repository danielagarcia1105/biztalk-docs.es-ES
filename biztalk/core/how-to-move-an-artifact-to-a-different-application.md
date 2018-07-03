---
title: Cómo mover un artefacto a una aplicación diferente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, moving
- applications, artifacts
ms.assetid: 861e7782-0566-4478-a0bd-f8ced1ea6d56
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a76da726672d122935d6c7b393b403f11bb9068
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993509"
---
# <a name="how-to-move-an-artifact-to-a-different-application"></a>Cómo mover un artefacto a una aplicación diferente
En este tema se describe cómo mover un artefacto de una aplicación a otra dentro de un grupo de BizTalk mediante el comando Mover a aplicación de la consola de administración de BizTalk Server. Puede que desee hacerlo si necesita usar en una aplicación un artefacto que ya existe en otra aplicación del mismo grupo de BizTalk.  
  
 Al mover un artefacto, tenga en cuenta los siguientes puntos importantes:  
  
-   **Las aplicaciones deben estar en el mismo grupo.** El comando Mover a aplicación sólo funciona si la aplicación desde la que desea mover el artefacto se encuentra en el mismo grupo de BizTalk que la aplicación a la que desea mover el artefacto. Si desea mover el artefacto a una aplicación de un grupo diferente, puede exportar el artefacto desde la aplicación en la que existe ya y, a continuación, importarlo en la aplicación nueva, o bien agregar el artefacto a la aplicación. Para obtener instrucciones, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md), [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md), y [cómo crear o agregar un artefacto](../core/how-to-create-or-add-an-artifact.md). Debe, a continuación, quitar manualmente el artefacto de la aplicación original, como se describe en [cómo quitar un artefacto de una aplicación](../core/how-to-remove-an-artifact-from-an-application.md).  
  
-   **Mover un artefacto, también puede mover los artefactos en la que depende o que dependen de él.** Cuando mueve un artefacto a una aplicación nueva, se mueven también los artefactos con los que tiene relaciones de dependencia a no ser que la aplicación nueva tenga una referencia a las aplicaciones que contienen los artefactos de los que depende el artefacto movido. Asimismo, se mueven los artefactos que tengan relaciones de dependencia con el artefacto movido a no ser que las aplicaciones que los contienen tengan una referencia a la aplicación nueva. Al mover un artefacto, se muestra la lista de otros artefactos que también se moverán.  
  
> [!NOTE]
>  Si necesita usar el mismo artefacto en dos o más aplicaciones, es posible que necesite crear una referencia de la aplicación en la que desea usar el artefacto a la que lo contiene en ese momento. Esto se debe a que determinados tipos de artefactos deben ser únicos dentro de un grupo de BizTalk. Para obtener más información, consulte [artefactos que deben ser únicos en una aplicación o grupo](../core/artifacts-that-must-be-unique-in-an-application-or-group.md). Para obtener instrucciones sobre cómo agregar referencias, vea [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md). Tenga en cuenta que al agregar una referencia a otra aplicación, se crean relaciones de dependencia entre las aplicaciones y esto afecta al modo de implementarlas. Para obtener información general, consulte [dependencias e implementación de aplicación](../core/dependencies-and-application-deployment.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-move-an-artifact-to-a-different-application"></a>Para mover un artefacto a una aplicación diferente  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk y, a continuación, la aplicación desde la que desea mover el artefacto.  
  
3. Haga clic en la carpeta que contiene el artefacto que desea mover, haga clic en el artefacto y, a continuación, haga clic en **mover a aplicación**.  
  
4. En el **aplicación de destino** cuadro, haga clic en la flecha y, a continuación, haga clic en la aplicación a la que desea mover el artefacto.  
  
    El **Mover artefactos** cuadro muestra el artefacto que se mueven junto con todos los artefactos dependientes, que se va a mover también.  
  
5. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)