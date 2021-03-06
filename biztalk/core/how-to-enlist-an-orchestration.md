---
title: Cómo dar de alta una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], enlisting
- orchestrations, enlisting
- enlisting, orchestrations
ms.assetid: b21a398b-8c9a-42ae-aac0-de35dbfd8176
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203f8a61c439230b692577c8674b12e35944c24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966293"
---
# <a name="how-to-enlist-an-orchestration"></a>Cómo dar de alta una orquestación
Este tema describe cómo usar la consola de administración de BizTalk Server para dar de alta una orquestación en un host. Antes de iniciar la orquestación, es necesario darla de alta.  
  
 Al dar de alta una orquestación, tenga en cuenta los siguientes puntos:  
  
-   **Antes de darla, se debe enlazar la orquestación.** Para obtener instrucciones sobre cómo configurar enlaces para orquestaciones, consulte [cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md).  
  
-   **Las suscripciones se crean automáticamente.** El proceso de alta de la orquestación crea las suscripciones necesarias en la base de datos de cuadro de mensajes.  
  
-   **Debe instalar la aplicación.** Tendrá que instalar la aplicación que contiene la orquestación en todos los equipos en los que ésta se va a ejecutar. Para obtener más información, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
-   **En el mismo host que la orquestación de llamada se debe enlazar una orquestación que realiza la llamada.** Toda orquestación a la que llame otra orquestación debe estar enlazada al mismo host que la segunda.  
  
-   **También debería dar de alta orquestaciones dependientes.** Si da de alta una orquestación y no da de alta ninguna orquestación dependiente, las orquestaciones dependientes no tendrán ninguna suscripción. Una orquestación dependiente sin suscripciones podría omitir o suspender mensajes, al no existir ninguna suscripción que coincida con éstos.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede dar de alta una orquestación para probar su funcionalidad durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-enlist-an-orchestration"></a>Para dar de alta una orquestación  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea dar de alta.  
  
3. Haga clic en **orquestaciones**, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **Enlist**.  
  
   > [!NOTE]
   >  Para dar de alta varias orquestaciones a la vez, mantenga presionada la tecla MAYÚS y seleccione cada orquestación para dar de alta, haga clic en una orquestación y, a continuación, haga clic en **Enlist**.  
  
    La orquestación se da de alta y se crean las suscripciones pertinentes. La orquestación se encuentra en estado de detención. Para comenzar a procesar los mensajes entrantes, es preciso iniciar expresamente la orquestación haciendo clic en él y haga clic en **iniciar**. Para obtener más información, consulte [cómo iniciar una orquestación](../core/how-to-start-an-orchestration.md).  
  
## <a name="see-also"></a>Vea también  
 [Administración de orquestaciones](../core/managing-orchestrations.md)   
 [Cómo dar de baja una orquestación](../core/how-to-unenlist-an-orchestration.md)