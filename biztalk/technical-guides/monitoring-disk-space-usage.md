---
title: Supervisar el uso de espacio de disco | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ae87de0b00e70ae03a30dd8ef20ede4a972388d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-disk-space-usage"></a>Supervisar el uso de espacio en disco
Como parte del proceso de supervisión de preparación operativa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], supervisar el uso de espacio en disco como sigue:  
  
-   **Determinar el disco espacio necesario.**  
  
     Al usar archivo o MSMQ enviar / ubicaciones de recepción, asegúrese de que hay espacio suficiente dar cabida a las interrupciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de los sistemas de recepción. Por ejemplo, si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es escribir archivos en un recurso compartido en una red SAN y el sistema receptor está inactivo durante dos días, determinar si hay suficiente espacio en disco para permitir que los archivos en cola.  
  
-   **Limpiar periódicamente el directorio de archivos de copia de seguridad de BizTalk Server.**  
  
     Puede realizar esta limpieza utilizando una secuencia de comandos que se llama desde un trabajo del Agente SQL Server.  
  
-   **Limpiar periódicamente el directorio de archivos de archivo de base de datos de seguimiento de BizTalk.**  
  
-   **Asegúrese de que hay suficiente espacio en disco disponible para acomodar la base de datos de BizTalk Server mayor (.mdf) y los archivos de registro (.ldf) de transacciones durante las horas pico del flujo de datos.**