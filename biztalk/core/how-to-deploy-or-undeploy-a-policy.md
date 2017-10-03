---
title: "Cómo implementar o anular la implementación de una directiva | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [policies], undeploying
- deploying, policies
- policies, deploying
- managing [policies], deploying
- policies, undeploying
- undeploying, policies
ms.assetid: 9d26d4fe-9673-4baa-9927-02efda56b7a4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4913dbfa6f3d027d5540234b5af9370eb69f67a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a>Cómo implementar o anular la implementación de una directiva
En este tema se describe cómo usar la consola de administración de BizTalk Server para implementar o anular la implementación de una directiva de forma manual. Además, al iniciar una aplicación, las directivas que contenga se implementan automáticamente, y cuando se detiene, se anula de forma automáticamente la implementación de las directivas correspondientes. Al implementar una directiva, entra en vigor en la aplicación que la usa. Al anular la implementación de una directiva, se desactiva de modo que deja de funcionar en cualquier aplicación del grupo de BizTalk que la use.  
  
 Al implementar o anular la implementación de una directiva, tenga en cuenta los siguientes puntos importantes:  
  
-   Para poder implementar una directiva, debe existir en la base de datos del motor de reglas del grupo de BizTalk. Si importa una aplicación que contenga una directiva, la directiva se importa automáticamente en la base de datos de motor de reglas, o puede importar explícitamente de una directiva en la base de datos de motor de reglas mediante la consola de administración o BTSTask, como se describe en [Cómo importar una directiva](../core/how-to-import-a-policy.md). Como alternativa, puede agregar una directiva de la base de datos de motor de reglas utilizando el Asistente para la implementación del motor de reglas, como se describe en [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).  
  
-   Antes de poder implementar una directiva, debe estar publicada, como se describe en [cómo publicar una directiva](../core/how-to-publish-a-policy.md).  
  
-   Una directiva implementada no se puede modificar. Si desea modificar una directiva implementada, debe anular la implementación en primer lugar.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-deploy-or-undeploy-a-policy"></a>Para implementar o anular la implementación de una directiva  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la directiva que desea implementar o anular la implementación y, a continuación, expanda  **\<todos los artefactos >**.  
  
3.  Haga clic en **directivas**, haga clic en la directiva y, a continuación, haga clic en **implementar** o **anular la implementación**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de directivas](../core/managing-policies.md)   
 [Cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md)