---
title: Supervisar el uso de espacio en disco | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25035d50c6e69fcf74e1cf75e8f073b19cc0b47f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986933"
---
# <a name="monitoring-disk-space-usage"></a>Supervisar el uso de espacio en disco
Como parte del proceso de supervisión de disponibilidad operativa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], supervisar el uso de espacio en disco como sigue:  

- **Determinar el disco de espacio necesario.**  

   Cuando utilizando el archivo o MSMQ enviar / recibir ubicaciones, asegúrese de que hay espacio suficiente dar cabida a las interrupciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de los sistemas de recepción. Por ejemplo, si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es escribir archivos en un recurso compartido en una red SAN y el sistema de recepción está inactivo durante dos días, determine si hay suficiente espacio en disco para permitir que los archivos para poner en cola.  

- **Limpie periódicamente el directorio de archivos de copia de seguridad de BizTalk Server.**  

   Puede realizar esta limpieza mediante un script que se llama desde un trabajo del Agente SQL Server.  

- **Limpie periódicamente el directorio de archivos de archivo de base de datos de seguimiento de BizTalk.**  

- **Asegúrese de que hay suficiente espacio en disco disponible para dar cabida a más grandes bases de datos de BizTalk Server (.mdf) y los archivos de registro (.ldf) de transacciones durante las horas pico del flujo de datos.**
