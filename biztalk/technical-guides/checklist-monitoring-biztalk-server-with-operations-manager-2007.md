---
title: "Lista de comprobación: Supervise BizTalk Server con Operations Manager 2007 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e1f7f57-1501-473f-af5f-15f3e1ddaf8e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810ede830f7142181c4bec1f727cbc496049ce03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-monitoring-biztalk-server-with-operations-manager-2007"></a>Lista de comprobación: Supervise BizTalk Server con Operations Manager 2007
Este tema enumeran los pasos generales que puede seguir cuando se prepare para supervisar su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
|Paso|Referencia|  
|----------|---------------|  
|Asegúrese de que tiene los permisos adecuados para instalar y configurar el software en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos.|[Derechos de usuario mínimos de seguridad](http://go.microsoft.com/fwlink/?LinkID=154374) (http://go.microsoft.com/fwlink/?LinkID=154374)|  
|Instalar el agente Operations Manager 2007 en cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo que desea supervisar y haga que señale al servidor de Operations Manager 2007.|Hacer referencia a [implementación de Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkId=110030) (http://go.microsoft.com/fwlink/?LinkId=110030)|  
|Descargue e importe la versión adecuada de los módulos de administración para lo siguiente:<br /><br /> -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](obligatorio)<br />-Enterprise Single Sign-On (obligatorio)<br />-Base de sistema operativo de Windows (servidor) (opcional)<br />-Clúster de Microsoft Windows Server (si clústeres son usados, opcional)<br />-SQL Server 2008, SQL Server 2005 (opcional)<br />-Internet Information Services (IIS) 2008, IIS 2003 (opcional)<br />-Message Queuing (MSMQ) 3.0 (opcional)|-Descargar los módulos de administración de [System Center Management Pack Catalog](http://go.microsoft.com/fwlink/?LinkId=203227) (http://go.microsoft.com/fwlink/?LinkId=203227).<br />-Importar el módulo de administración siguiendo las instrucciones en [cómo importar un módulo de administración en Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=98348) (http://go.microsoft.com/fwlink/?LinkID=98348).|  
|Lea las prácticas recomendadas para el uso de Operations Manager 2010 para supervisar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|[Prácticas recomendadas para la supervisión con Operations Manager 2007](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)|  
|Habilitar o deshabilitar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reglas del módulo de administración según corresponda.|[Prácticas recomendadas para la supervisión con Operations Manager 2007](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)|  
|Agregar los equipos de inicio de sesión único (SSO) empresarial independiente a la lista de equipos que va a supervisar mediante el módulo de administración de BizTalk Server.|[Cómo agregar equipos de inicio de sesión único de Enterprise a la lista de equipos supervisados por el módulo de administración de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=157263) (http://go.microsoft.com/fwlink/?LinkId=157263).|  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server con System Center Operations Manager 2007](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)