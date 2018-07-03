---
title: Supervisión de trabajos del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fb4026b95a5f368c265b49425ab1d3e1ec776cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015395"
---
# <a name="monitoring-sql-server-agent-jobs"></a>Supervisión de trabajos del Agente SQL Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye varios trabajos del Agente SQL Server que realizan funciones importantes para mantener los servidores operativos y en buen estado. Por ello, debe supervisar el estado de funcionamiento de estos trabajos y garantizar que no se producen errores en su ejecución.  

## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a>Directrices para supervisar los trabajos del Agente SQL Server  
 Las siguientes son directrices para la supervisión de los trabajos:  

- **Compruebe que se está ejecutando el servicio Agente SQL Server**  

- **Compruebe que los trabajos del Agente SQL Server instalados por BizTalk Server están habilitados y ejecutándose correctamente**  

   El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos del Agente SQL Server son fundamentales: si no se están ejecutando, se degradará el rendimiento del sistema con el tiempo.  

- **Compruebe que se completan los trabajos del Agente SQL Server de BizTalk Server de manera oportuna**  

   Configuración de Microsoft System Center Operations Manager para supervisar los trabajos.  

   Debe ser consciente de las programaciones que son específicas de determinados trabajos:  

  -   El trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb continuamente se ejecuta de forma predeterminada. Software de supervisión debe tener esta programación en la cuenta y no generan advertencias.  

  -   El trabajo MessageBox_Message_Cleanup_BizTalkMsgBoxDb no está habilitado o programado, pero se inicia el trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb cada 10 segundos. Por lo tanto, este trabajo debe no ser habilitado, programado o iniciar de forma manual.  

- **Compruebe que el tipo de inicio del servicio Agente SQL Server está configurado correctamente**  

   Compruebe que el servicio Agente SQL Server está configurado con un **Startuptype** de **automática** a menos que el servicio Agente SQL Server está configurado como un recurso de clúster en un clúster de Windows Server. Si el servicio Agente SQL Server está configurado como un recurso de clúster, se debe configurar el **Startuptype** como **Manual** puesto que el servicio se administrarán mediante el servicio de clúster.  

## <a name="additional-resources"></a>Recursos adicionales  

- Para obtener más información acerca de cómo supervisar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos del Agente SQL, consulte [trabajos del agente de supervisión de SQL Server y bases de datos](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md).  

- Para obtener más información acerca de los trabajos del Agente SQL Server que se incluyen con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vea ["Estructura de base de datos y trabajos"](http://go.microsoft.com/fwlink/?LinkID=153451) (<http://go.microsoft.com/fwlink/?LinkID=153451>).
