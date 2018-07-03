---
title: Administrar la configuración de rendimiento de servidor BizTalk Server | Microsoft Docs
description: Utilice el panel de configuración para actualizar el grupo, host y las instancias de host en BizTalk Server de BizTalk
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca56a981-a255-4c4d-82f8-a57d390e425e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19acfa50ecbcaf46cb796630e88d292283f4631e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999773"
---
# <a name="manage-biztalk-server-performance-settings"></a>Administrar la configuración de rendimiento de servidor BizTalk Server
  
 El [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] en BizTalk Server recopila la configuración de rendimiento y proporciona una consola central para administrar esta configuración. Esto ayuda a:  
  
-   Mejorar la detectabilidad de las propiedades que se pueden establecer
  
-   Reducir el tiempo de solución porque todas las configuraciones están accesibles ahora en un solo lugar y se pueden exportar/importar fácilmente
  
-   Ofrece una visión holística del nivel de optimización del rendimiento realizado en una determinada implementación de BizTalk
  
## <a name="why-use-it"></a>¿Por qué usarla?  
 El [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] está dirigido a los administradores de TI que necesitan modificar extensivamente la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para optimizar el rendimiento.  
  
 Puede usar el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] para modificar la configuración del grupo de BizTalk y todos los hosts de BizTalk y las instancias de host de BizTalk de dicho grupo.  
  
 Para obtener más información sobre el grupo, el host y la configuración de la instancia de host, consulte [cómo modificar la configuración del grupo](../core/how-to-modify-group-settings.md), [cómo modificar la configuración del Host](../core/how-to-modify-host-settings.md), y [cómo modificar opciones de instancia de Host](../core/how-to-modify-host-instance-settings.md).  
  
## <a name="prerequisites"></a>Requisitos previos 
 Puede iniciar el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener información sobre cómo administrar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración de rendimiento mediante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, consulte [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md).  
  
## <a name="where-do-i-start"></a>¿Por dónde comenzar?  
 Puede obtener acceso al [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] de cualquiera de las maneras siguientes:  
  
- Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **grupo de BizTalk** en el árbol de consola y, a continuación, seleccione **configuración**.  
  
- A la derecha, haga clic en cualquier host bajo el **configuración de plataforma** nodo en MMC y haga clic en **configuración**. Esto inicia el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] y puede modificar la configuración relativa a ese host.  
  
- Haga clic en cualquier instancia de host la **configuración de plataforma** nodo en MMC y haga clic en **configuración**. Esto inicia el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] y puede modificar la configuración relativa a esa instancia de host.  
  
## <a name="export-and-import-settings"></a>Exportar e importar configuraciones  
 El [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] se puede usar para exportar la configuración de un entorno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e importarla a otro entorno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], reduciendo de esta manera el tiempo para la solución global. Esto es especialmente práctico en aquellas situaciones en las que los administradores intentan ajustar el rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de prueba y, una vez obtenidos los resultados deseados, pueden importar la configuración a un entorno de producción.  
  
 Para obtener información acerca de cómo usar import/export el [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] interfaz de usuario, consulte [importación o exportación usando configuración de panel de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md).
  
## <a name="scripting-support"></a>Compatibilidad con scripting
 El [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] no únicamente proporciona una interfaz de usuario central para administrar la configuración de BizTalk sino que también asegura que se pueda obtener acceso a toda la configuración y las tareas de importación y exportación mediante las API y las opciones de la línea de comandos. Esto permite a los administradores de BizTalk Server automatizar las tareas relacionadas con la configuración de BizTalk Server. Como parte de la compatibilidad de creación de scripts:  
  
- Todas las configuraciones de grupo se pueden obtener acceso y modificar mediante la clase WMI: `MSBTS_GroupSetting`  
  
- Todas las configuraciones de host se pueden obtener acceso y modificar mediante la clase WMI: `MSBTS_HostSetting`  
  
- Todas las configuraciones de la instancia de host se pueden obtener acceso y modificar mediante la clase WMI: `MSBTS_HostInstanceSetting`  
  
- Operaciones de importación y exportación se pueden acceder mediante **BTSTask.exe** comandos: `ExportSettings` y `ImportSettings`  
  
  Para obtener más información acerca de cómo importar y exportar mediante la utilidad de línea de comandos de BTSTask.exe, consulte [importación o exportación de configuración de BizTalk mediante BTSTask](how-to-import-biztalk-settings-using-btstask.md).  
  
## <a name="next"></a>Siguiente  
  
-   [Uso del panel de configuración para ajustar el rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)  
  
-   [Automatizar el ajuste de rendimiento de BizTalk Server](../core/automating-biztalk-server-performance-tuning.md)  
  
## <a name="see-also"></a>Vea también  
 [Administrar BizTalk Server](../core/use-groups-create-artifacts-optimize-performance-and-more-in-biztalk-server.md)