---
title: "Preparar los servidores de BizTalk de recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14c2c25d-30c5-4e90-a744-f084befa2c1d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9379136f0845c7c4c987170747a28bd3c50206c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a>Preparar los servidores de BizTalk de recuperación ante desastres
Instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución en el sitio de recuperación ante desastres, siga las recomendaciones de [BizTalk Server 2010 Installation and Upgrade Guides](http://go.microsoft.com/fwlink/?LinkID=194815) (http://go.microsoft.com/fwlink/?LinkID=194815). Configurar estas opciones [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución mediante el Asistente para configuración de BizTalk para unirlos al grupo de BizTalk de producción. Al configurar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución en el sitio de recuperación ante desastres (incluido el servidor de Enterprise Single Sign-On secreto principal de recuperación de desastres) asegúrese de:  
  
-   Seleccione **No** a la pregunta "¿es este el servidor secreto principal?"  
  
-   Seleccione **combinación** a la pregunta "¿desea crear o unirse a un grupo de BizTalk Server?"  
  
 Después de configurar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de recuperación ante desastres de tiempo de ejecución, crear instancias de host de BizTalk en el sitio de recuperación ante desastres que corresponden a las instancias de host del sitio de producción, pero no comience a estas instancias de host. Por ejemplo, si el sitio de producción tiene tres Hosts **enviar**, **recepción**, y **orquestación** con instancias en Servidor1, servidor2 y server3, cree tres correspondiente instancias de host en DRserver1, DRserver2, DRserver3.  
  
> [!NOTE]  
>  Todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionados con servicios de Windows, como la instancia de Host de BizTalk y el servicio de motor de reglas en el sitio de recuperación ante desastres deben establecerse en "disabled" en el Administrador de servicios para evitar que el sitio de recuperación ante desastres de realizar cualquier procesamiento.  
  
 Puede instalar y configurar un número diferente de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución en el sitio de recuperación ante desastres que se ejecutan en producción. Tenga cuidado al adoptar este enfoque, sin embargo, con el fin de evitar la sobrecarga de los servidores en el sitio de recuperación ante desastres si se produce un evento de recuperación ante desastres. Una vez que el grupo de BizTalk, tal como está representado por el conjunto de bases de datos se restaura totalmente y se llevan a cabo todos los cambios del sistema necesarios para el grupo de BizTalk, se pueden ejecutar scripts para unirse a la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución para el grupo de BizTalk.