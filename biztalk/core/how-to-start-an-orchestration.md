---
title: Cómo iniciar una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], starting
- starting, orchestrations
- orchestrations, starting
ms.assetid: 83411279-ee6f-4d68-aa3b-b5cd5e106088
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e277c078a36129a125937114ee9287a1e97999b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255428"
---
# <a name="how-to-start-an-orchestration"></a>Cómo iniciar una orquestación
En este tema se explica cómo utilizar la consola de administración de BizTalk Server para iniciar una orquestación. Al iniciar una orquestación, ésta comienza a procesar mensajes entrantes.  
  
 Al iniciar una orquestación, tenga en cuenta que los siguientes puntos son importantes:  
  
-   Antes de poder iniciar la orquestación, debe darse de alta junto con todos los puertos de envío y grupos de puertos de envío asociados con ella. Para obtener instrucciones, consulte [cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md) y [cómo dar de alta un puerto de envío o grupo de puertos de envío](../core/how-to-enlist-a-send-port-or-send-port-group.md).  
  
-   Al iniciar una orquestación, no se inicia automáticamente todos los puertos de envío asociados. Debe iniciar por separado, tal como se describe en [cómo iniciar un puerto de envío o grupo de puertos de envío](../core/how-to-start-a-send-port-or-send-port-group.md).  
  
-   Si da de alta los puertos de envío o los grupos de puertos de envío asociados con la orquestación, pero no los inicia, BizTalk Server coloca todos los mensajes enviados a este puerto de envío o grupo de puertos de envío en la cola de suspensión del host en el que se dio de alta al puerto de envío o al grupo de puertos de envío.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede iniciar una orquestación para probar su funcionalidad durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento detallado en este tema, debe haber iniciado sesión como miembro del grupo de operadores o de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-start-an-orchestration"></a>Para iniciar una orquestación  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea iniciar.  
  
3.  Haga clic en **orquestaciones**, haga clic en la orquestación y, a continuación, haga clic en **iniciar**.  
  
    > [!IMPORTANT]
    >  Si, antes de iniciar la orquestación, no ha dado de alta el puerto de envío o los grupos de puertos de envío asociados, aparecerá un mensaje de error.  
  
    > [!NOTE]
    >  Para iniciar varias orquestaciones a la vez, mantenga presionada la tecla MAYÚS y seleccione cada orquestación, haga clic en una orquestación y, a continuación, haga clic en **iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar orquestaciones](../core/managing-orchestrations.md)   
 [Cómo detener una orquestación](../core/how-to-stop-an-orchestration.md)   
 [Cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md)