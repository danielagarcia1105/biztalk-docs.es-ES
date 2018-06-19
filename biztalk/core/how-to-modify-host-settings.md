---
title: Cómo modificar la configuración de Host | Documentos de Microsoft
description: Cambiar la configuración de host de BizTalk en administración de BizTalk Server para mejorar el rendimiento y limitación
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0759b3a0-560e-4a11-92e6-9de0e15f463b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 998c668bf787c9db260597c3a350e0e571492212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254556"
---
# <a name="update-biztalk-host-settings"></a>Actualizar la configuración de host de BizTalk

## <a name="overview"></a>Información general
Mediante el uso del Panel de configuración, puede modificar la información de configuración de un host dado en todo un grupo de BizTalk. En este tema se proporciona el procedimiento paso a paso para modificar la configuración de rendimiento de nivel de host en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  También puede modificar la configuración de instancia de host y de grupo. Para obtener información sobre cómo modificar la configuración, consulte [uso del panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).  
  
 La configuración actual de BizTalk Server puede exportarse a un archivo XML. Posteriormente, puede importarse dicha configuración en el panel de configuraciones, en lugar de configurar nuevos valores. Para obtener información acerca de cómo importar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración, consulte [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) y [importación o exportación BTSTask de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-btstask.md). 
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe iniciar sesión como miembro del grupo Administradores de BizTalk Server.  
  
## <a name="update-the-host-level-settings"></a>Actualizar la configuración de nivel de host  
  
1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo, en la **Hosts** página, realice una o varias de las acciones siguientes.  
  
    -   Modificar la configuración de rendimiento general del host de BizTalk. Vea [cómo modificar la configuración General](../core/how-to-modify-general-settings.md).  
  
    -   Modificar la configuración de limitación basada en recursos del host de BizTalk. Vea [modificar recursos basada en valores de límite](../core/how-to-modify-resource-based-throttling-settings.md).  
  
    -   Modifique la configuración de limitación según la velocidad del host de BizTalk. Vea [Modificar tasa basada en valores de límite](../core/how-to-modify-rate-based-throttling-settings.md).  
  
    -   Modificar la configuración de limitación de orquestación del host de BizTalk. Vea [cómo modificar la configuración de limitación de orquestación](../core/how-to-modify-orchestration-throttling-settings.md).  
  
## <a name="see-also"></a>Vea también  
 [Usar el panel de configuración para el servidor BizTalk Server ajuste del rendimiento](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)