---
title: Actualización del Acelerador para RosettaNet (BTARN) en BizTalk Server | Microsoft Docs"
description: Siga los pasos de actualización para actualizar BTARN a la versión actual de BizTalk Server
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 80e813ced767cdd56910027b655060e1db9f91fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011312"
---
# <a name="upgrade-the-rosettanet-accelerator"></a>Actualizar el Acelerador de RosettaNet

## <a name="upgrade-overview"></a>Información general sobre la actualización
Puede actualizar la versión anterior del Acelerador de BizTalk para la instalación de RosettaNet (BTARN) a la versión actual. El proceso de actualización implica la actualización del servidor BizTalk Server y, a continuación, BTARN.  
  
 Puede actualizar desde la versión anterior de BTARN en un ejecutando el programa de instalación de BTARN. El programa de instalación migra la información de configuración de BTRAN a la versión actual.  
  
 En un entorno de BTARN multiservidor, debe actualizar todos los servidores BizTalk primero y, a continuación, en BTARN. Migre los servidores en este orden:  
  
- Servidor que hospeda el grupo de BizTalk  
  
- Cada nodo de procesamiento  
  
- Servidor del portal de BAM  
  
  En el BTARN proceso de actualización, asegúrese de que haga lo siguiente:  
  
- Compruebe si el servicio SQL Server (MSSQLSERVER) está en ejecución.  
  
- No realice una instalación silenciosa.  
  
## <a name="upgrade-steps"></a>Pasos de la actualización  
  
1.  Actualización de BizTalk Server. Consulte [BizTalk Server Novedades, instalación, configuración y actualización](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).
  
2.  Realizar una copia de seguridad de la base de datos BTARN y esquemas de mensajes BTARN.  
  
    > [!NOTE]
    >  Debe realizar copias de seguridad de la base de datos BTARN por razones de seguridad. El programa de instalación migra la base de datos BTRAN a la versión más reciente.  
  
3.  Copia de seguridad de los archivos en el *< unidad\>*: \Program archivos\\Acelerador de Microsoft BizTalk para RosettaNet carpeta que haya realizado los cambios en, por ejemplo, los archivos del SDK.  
  
4.  Anule la implementación de los proyectos o ensamblados que tengan referencias a una o varias versiones anteriores de los ensamblados de BTARN.  
  
5.  En Visual Studio, manualmente anular la implementación de todos los ensamblados BTARN, en el orden siguiente:  
  
    -   Microsoft.Solutions.BTARN.CommonTypes  
  
    -   Microsoft.Solutions.BTARN.GlobalSchemas  
  
    -   Microsoft.Solutions.BTARN.PipelineReceive  
  
    -   Microsoft.Solutions.BTARN.PipelineSend  
  
    -   Microsoft.Solutions.BTARN.PrivateInitiator  
  
    -   Microsoft.Solutions.BTARN.PrivateResponder  
  
    -   Microsoft.Solutions.BTARN.PublicInitiator  
  
    -   Microsoft.Solutions.BTARN.PublicResponder  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv11  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv20  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs  
  
6.  Ejecute la instalación de BTARN. Consulte [instalar y configurar el Acelerador de RosettaNet](install-configure-biztalk-accelerator-for-rosettanet.md).
  
7.  Use **BTSTask.exe** (\Program Files\Microsoft BizTalk Server) volver a implementar manualmente los ensamblados BTARN en el orden siguiente:  
  
    -   Microsoft.Solutions.BTARN.CommonTypes  
  
    -   Microsoft.Solutions.BTARN.GlobalSchemas  
  
    -   Microsoft.Solutions.BTARN.PipelineReceive  
  
    -   Microsoft.Solutions.BTARN.PipelineSend  
  
    -   Microsoft.Solutions.BTARN.PrivateInitiator  
  
    -   Microsoft.Solutions.BTARN.PrivateResponder  
  
    -   Microsoft.Solutions.BTARN.PublicInitiator  
  
    -   Microsoft.Solutions.BTARN.PublicResponder  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv11  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv20  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs  
  
    > [!NOTE]
    >  Para obtener más información acerca de **BTSTask.exe**, vea el tema "Referencia de línea de comandos de BTSTask" en la Ayuda de BizTalk Server.  
  
8.  Volver a generar los proyectos o ensamblados que tienen una referencia a uno o varios de los [ensamblados BTARN. Use **BTSTask.exe** volver a implementar manualmente estos proyectos.  
  
9. Actualice las carpetas virtuales en IIS de ASP.NET 2.0 a ASP.NET 4.0 para lo siguiente:  
  
    -   BTARNApp  
  
    -   BTARNHttpReceive  
  
10. Reinicie el equipo para aplicar las modificaciones.  
  
