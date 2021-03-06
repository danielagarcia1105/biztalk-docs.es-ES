---
title: Actualizar la configuración de la instancia de Host | Microsoft Docs
description: Cambiar la configuración de la instancia de host en el Administrador de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2338255b-cc13-4f6a-86c3-9ecc666c43e5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6102e4cce6a850c7e2ed5656a8fd5aacfd5d5a09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011717"
---
# <a name="update-biztalk-host-instance-settings"></a>Actualizar la configuración de instancia de host de BizTalk

## <a name="overview"></a>Información general
Mediante el uso del [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], puede modificar la información de configuración de un host dado en todo un grupo de BizTalk. En este tema se proporciona el procedimiento paso a paso para modificar la configuración de rendimiento de nivel de instancia en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 A menudo tienen la configuración de BizTalk (desde un entorno de origen) guardada como archivo XML. El archivo XML contiene información que le permite replicar la configuración en el equipo de destino. Puede importar dicha configuración al Panel de configuración, en lugar de configurar nuevos valores. Por otro lado, después de configurar nuevos valores para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede exportarlos a un archivo XML para su uso en otro equipo.  
  
 Para obtener información sobre cómo importar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración, consulte [importación o exportación usando configuración de panel de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) y [importación o exportación de configuración de BizTalk mediante BTSTask](how-to-import-biztalk-settings-using-btstask.md). 
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe iniciado sesión como miembro del grupo Administradores de BizTalk Server.  
  
## <a name="update-the-host-instance-level-settings"></a>Actualizar la configuración de nivel de instancia de host  
  
1. En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2. En el **panel de configuración de BizTalk** cuadro de diálogo el **instancias de Host** ficha, realice cualquiera de las siguientes acciones:  
  
   -   Modificar la configuración de .NET CLR para una instancia de host. Consulte [cambiar la configuración de .NET CLR](../core/how-to-modify-net-clr-settings.md).  
  
   -   Modificar configuración de la limitación de la memoria de orquestación. Consulte [cambiar la configuración de la limitación de memoria de orquestación](../core/how-to-modify-orchestration-memory-throttling-settings.md).  
  
## <a name="see-also"></a>Vea también  
 [Uso del panel de configuración para ajustar el rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)