---
title: Copia de seguridad de la base de datos de A4SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cd2cd1eadf3dc6f11a6e3178258caaaf88006d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-the-a4swift-database"></a>Copia de seguridad de la base de datos de A4SWIFT
Habitualmente debe realizar la copia de seguridad de las bases de datos en el sistema de BizTalk Server y A4SWIFT para reducir los riesgos de un error catastrófico. Estas bases de datos son las de su sistema de origen de BizTalk Server y la base de datos de A4SWIFT. Además de reducir los riesgos, esto también habilitará purgar los archivos de historial de A4SWIFT que pueden alcanzar un tamaño considerable.  
  
 Para obtener más información acerca de la copia de seguridad de las bases de datos en el sistema de origen de BizTalk Server, vea el tema "Realizar una copia de seguridad y restaurar BizTalk Server bases de datos" en la [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda. Este tema describe el trabajo de copia de seguridad de BizTalk Server que utiliza para las bases de datos de BizTalk.  
  
 Para obtener información acerca de la copia de seguridad de la base de datos de A4SWIFT, vea el tema "How to volver seguridad personalizada Databases" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda. En este tema se describe cómo modificar el trabajo de copia de seguridad de BizTalk Server para incluir la base de datos personalizada de A4SWIFT.