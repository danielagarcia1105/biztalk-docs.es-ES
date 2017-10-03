---
title: "Cómo publicar una directiva | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- managing [policies], publishing
- publishing, policies
ms.assetid: 730c57a7-526f-40ca-8610-88216558e375
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a64c4764459eecd0d1a4fceedf7a7e8e61159503
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-publish-a-policy"></a>Cómo publicar una directiva
En este tema se describe cómo usar la consola de administración de BizTalk Server para publicar una directiva en un grupo de BizTalk. Publicar una directiva hace que esté disponible para agregar a una aplicación de BizTalk, tal y como se describe en [cómo agregar una directiva a una aplicación](../core/how-to-add-a-policy-to-an-application.md).  
  
 Para poder publicar una directiva, ésta debe existir en la base de datos del motor de reglas del grupo de BizTalk. Existen tres formas de importar una directiva a la base de datos del motor de reglas:  
  
-   Puede importar una aplicación que contenga una directiva. Al hacerlo, la directiva se importa de forma automática a la base de datos del motor de reglas.  
  
-   Puede importar explícitamente de una directiva en la base de datos de motor de reglas mediante la consola de administración o BTSTask, como se describe en [cómo importar una directiva](../core/how-to-import-a-policy.md).  
  
-   Puede agregar una directiva de la base de datos de motor de reglas mediante el Asistente para la implementación del motor de reglas, como se describe en [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).  
  
> [!NOTE]
>  Mientras que una directiva publicada puede sobrescribirse con otra directiva importada (si especifica esta opción), un vocabulario publicado nunca puede sobrescribirse. Para actualizar un vocabulario publicado, debe quitarlo de la base de datos del motor de reglas y, a continuación, importar la versión nueva.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-publish-a-policy"></a>Para publicar una directiva  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk que contiene la directiva para publicar, expanda **aplicaciones**y, a continuación, expanda  **\<todos los artefactos >**.  
  
3.  Haga clic en **directivas**, haga clic en la directiva y, a continuación, haga clic en **publicar**.  
  
    > [!NOTE]
    >  Para publicar una directiva, cualquier ensamblado que hace referencia la directiva debe instalarse en la caché Global de ensamblados (GAC) de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo antes de abrir **administración de BizTalk Server**. Cuando **administración de BizTalk Server** está abierto, mantiene una caché de los ensamblados que se instalan en la GAC. Esta memoria caché no se actualiza hasta que **administración de BizTalk Server** se cierra y se vuelve a abrir. Si intenta publicar una directiva y se produce un error en la publicación porque un ensamblado de referencia no está instalado en la GAC, debe cerrar **administración de BizTalk Server**, instale el ensamblado que se hace referencia en la GAC, abra  **Administración de BizTalk Server**y, a continuación, publicar la directiva.  
  
## <a name="see-also"></a>Vea también  
 [Administración de directivas](../core/managing-policies.md)