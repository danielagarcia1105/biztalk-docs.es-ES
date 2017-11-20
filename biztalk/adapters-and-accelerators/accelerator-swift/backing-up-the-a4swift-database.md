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
# <a name="backing-up-the-a4swift-database"></a><span data-ttu-id="0e124-102">Copia de seguridad de la base de datos de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="0e124-102">Backing Up the A4SWIFT Database</span></span>
<span data-ttu-id="0e124-103">Habitualmente debe realizar la copia de seguridad de las bases de datos en el sistema de BizTalk Server y A4SWIFT para reducir los riesgos de un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="0e124-103">You should routinely back up the databases in your BizTalk Server and A4SWIFT system to lower the risks of a catastrophic failure.</span></span> <span data-ttu-id="0e124-104">Estas bases de datos son las de su sistema de origen de BizTalk Server y la base de datos de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0e124-104">These databases include those in your BizTalk Server source system, and the A4SWIFT database.</span></span> <span data-ttu-id="0e124-105">Además de reducir los riesgos, esto también habilitará purgar los archivos de historial de A4SWIFT que pueden alcanzar un tamaño considerable.</span><span class="sxs-lookup"><span data-stu-id="0e124-105">In addition to lowering risks, this will also enable you to purge A4SWIFT history files that can grow to a significant size.</span></span>  
  
 <span data-ttu-id="0e124-106">Para obtener más información acerca de la copia de seguridad de las bases de datos en el sistema de origen de BizTalk Server, vea el tema "Realizar una copia de seguridad y restaurar BizTalk Server bases de datos" en la [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="0e124-106">For more information about backing up the databases in your BizTalk Server source system, see the "Backing Up and Restoring BizTalk Server Databases" topic in the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span> <span data-ttu-id="0e124-107">Este tema describe el trabajo de copia de seguridad de BizTalk Server que utiliza para las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0e124-107">This topic describes the Backup BizTalk Server job that you use to back up BizTalk databases.</span></span>  
  
 <span data-ttu-id="0e124-108">Para obtener información acerca de la copia de seguridad de la base de datos de A4SWIFT, vea el tema "How to volver seguridad personalizada Databases" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="0e124-108">For information about backing up the A4SWIFT database, see the "How to Back Up Custom Databases" topic in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span> <span data-ttu-id="0e124-109">En este tema se describe cómo modificar el trabajo de copia de seguridad de BizTalk Server para incluir la base de datos personalizada de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0e124-109">This topic describes how to modify the Backup BizTalk Server job to include the custom A4SWIFT database.</span></span>