---
title: Cómo ver información de instancia de un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], viewing
- receive ports, viewing
- viewing, receive ports
ms.assetid: dad038bc-1202-489b-b144-a93bf1f53c0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ece5525e18eda82d480adec407f92f9f632453e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970253"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a>Cómo ver información de instancia de un puerto de recepción
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para ver instancias de servicio de un puerto de recepción. Siempre que el puerto de recepción recibe un mensaje, se crea una instancia de servicio para procesar ese mensaje. Al seguir el procedimiento que se detalla en este tema, la información de instancia se muestra en la página Información general del grupo del puerto de recepción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-view-instance-information-for-a-receive-port"></a>Para ver información de instancia de un puerto de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee ver la información de instancia de un puerto de recepción.  
  
3. Haga clic en **puertos de recepción**, seleccione el puerto de recepción, haga clic en **vista**y, a continuación, haga clic en **información de la instancia**.  
  
    En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias del puerto de recepción.  
  
4. Para refinar la consulta y ver información de instancia diferentes para el puerto de recepción, haga clic en el cuadro en **valor** para el **buscar** , seleccione el tipo de instancia para ver y, a continuación, haga clic en **ejecutar Consulta**. Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de recepción](../core/managing-receive-ports.md)   
 [Cómo buscar instancias de servicio de ejecución](../core/how-to-search-for-running-service-instances.md)   
 [Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md)   
 [Cómo buscar mensajes](../core/how-to-search-for-messages.md)   
 [Cómo buscar suscripciones](../core/how-to-search-for-subscriptions.md)