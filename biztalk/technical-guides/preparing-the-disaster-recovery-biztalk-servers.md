---
title: Preparación de los servidores de BizTalk de recuperación ante desastres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14c2c25d-30c5-4e90-a744-f084befa2c1d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f9d806f3f757200e425b2f922032cb8f8d26bc6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981573"
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a>Preparación de los servidores de BizTalk de recuperación ante desastres
Instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución en el sitio de recuperación ante desastres, siga las recomendaciones de [BizTalk Server 2010 Installation and Upgrade Guides](http://go.microsoft.com/fwlink/?LinkID=194815) (<http://go.microsoft.com/fwlink/?LinkID=194815>). Configure estos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución mediante el Asistente para configuración de BizTalk para unirlos al grupo de BizTalk de producción. Al configurar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no olvide los servidores de tiempo de ejecución en el sitio de recuperación ante desastres (incluido el servidor de Enterprise Single Sign-On secreto principal de recuperación ante desastres):  
  
- Seleccione **No** a la pregunta "¿es este el servidor secreto principal?"  
  
- Seleccione **combinación** a la pregunta "¿desea crear o unirse a un grupo de BizTalk Server?"  
  
  Después de configurar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de recuperación ante desastres de tiempo de ejecución, crear instancias de host de BizTalk en el sitio de recuperación ante desastres que corresponden a las instancias de host del sitio de producción, pero no comienzan a estas instancias de host. Por ejemplo, si el sitio de producción tiene tres Hosts **enviar**, **recepción**, y **orquestación** con instancias en Servidor1, servidor2 y server3, crear tres correspondiente instancias de host DRserver1, DRserver2, DRserver3.  
  
> [!NOTE]
>  Todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionadas con servicios de Windows, como la instancia de Host de BizTalk y el servicio de motor de reglas en el sitio de recuperación ante desastres deben establecerse en "disabled" en el Administrador de servicios para evitar que el sitio de recuperación ante desastres de realizar cualquier procesamiento.  
  
 Puede instalar y configurar un número diferente de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución en el sitio de recuperación ante desastres que se ejecutan en producción. Tenga cuidado al adoptar este enfoque sin embargo, con el fin de evitar la sobrecarga de los servidores del sitio de recuperación ante desastres si se produce un evento de recuperación ante desastres. Una vez que el grupo de BizTalk, tal como está representada por el conjunto de bases de datos esté completamente restaurado y se realizan todos los cambios del sistema necesarios para el grupo de BizTalk, se pueden ejecutar scripts para unir el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores de tiempo de ejecución para el grupo de BizTalk.