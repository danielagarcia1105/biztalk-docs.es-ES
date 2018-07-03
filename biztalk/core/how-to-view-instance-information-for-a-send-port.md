---
title: Cómo ver información de instancia de un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, viewing
- managing [send ports], viewing
- viewing, send ports
ms.assetid: 37cf6561-5341-4a05-b531-33ab0334966e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc1ae4401303845f92b95e6cdf7f4903c165b07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975149"
---
# <a name="how-to-view-instance-information-for-a-send-port"></a>Cómo ver información de instancia de un puerto de envío
En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para ver una lista de las instancias de servicio en ejecución de un puerto de envío. Una instancia de servicio es una instancia de servicio del puerto de envío que se crea al enviar un mensaje al puerto de envío. Al seguir el procedimiento que se detalla en este tema, la información de instancia se muestra en la página Información general del grupo del puerto de envío.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-view-instance-information-for-a-send-port"></a>Para ver información de instancia de un puerto de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea ver la información de instancia de servicio de un puerto de envío.  
  
3. Haga clic en **puertos de envío**, haga clic en el puerto de envío, seleccione **vista**y, a continuación, haga clic en **información de la instancia**.  
  
    En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias en ejecución del puerto de envío.  
  
4. Para refinar la consulta y ver la información de la instancia de servicio diferente para el puerto de envío, haga clic en el cuadro en **valor** para el campo Buscar y seleccionar el tipo de instancia para ver y, a continuación, haga clic en **Ejecutar consulta**. Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)   
 [Cómo buscar instancias de servicio de ejecución](../core/how-to-search-for-running-service-instances.md)   
 [Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md)   
 [Cómo buscar mensajes](../core/how-to-search-for-messages.md)   
 [Cómo buscar suscripciones](../core/how-to-search-for-subscriptions.md)