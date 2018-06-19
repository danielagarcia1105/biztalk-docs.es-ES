---
title: Copia de seguridad de la base de datos de A4SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4102d459d5b579491f42747f1d3fe0dd3d381b71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005861"
---
# <a name="backing-up-the-a4swift-database"></a><span data-ttu-id="f4b52-102">Copia de seguridad de la base de datos de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="f4b52-102">Backing Up the A4SWIFT Database</span></span>
<span data-ttu-id="f4b52-103">Habitualmente debe realizar la copia de seguridad de las bases de datos en el sistema de BizTalk Server y A4SWIFT para reducir los riesgos de un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="f4b52-103">You should routinely back up the databases in your BizTalk Server and A4SWIFT system to lower the risks of a catastrophic failure.</span></span> <span data-ttu-id="f4b52-104">Estas bases de datos son las de su sistema de origen de BizTalk Server y la base de datos de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="f4b52-104">These databases include those in your BizTalk Server source system, and the A4SWIFT database.</span></span> <span data-ttu-id="f4b52-105">Además de reducir los riesgos, esto también habilitará purgar los archivos de historial de A4SWIFT que pueden alcanzar un tamaño considerable.</span><span class="sxs-lookup"><span data-stu-id="f4b52-105">In addition to lowering risks, this will also enable you to purge A4SWIFT history files that can grow to a significant size.</span></span>  
  
 <span data-ttu-id="f4b52-106">Para obtener más información acerca de la copia de seguridad de las bases de datos en el sistema de origen de BizTalk Server, vea el tema "Realizar una copia de seguridad y restaurar BizTalk Server bases de datos" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f4b52-106">For more information about backing up the databases in your BizTalk Server source system, see the "Backing Up and Restoring BizTalk Server Databases" topic in the BizTalk Server Help.</span></span> <span data-ttu-id="f4b52-107">Este tema describe el trabajo de copia de seguridad de BizTalk Server que utiliza para las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f4b52-107">This topic describes the Backup BizTalk Server job that you use to back up BizTalk databases.</span></span>  
  
 <span data-ttu-id="f4b52-108">Para obtener información acerca de la copia de seguridad de la base de datos de A4SWIFT, vea el tema "How to volver seguridad personalizada Databases" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f4b52-108">For information about backing up the A4SWIFT database, see the "How to Back Up Custom Databases" topic in BizTalk Server Help.</span></span> <span data-ttu-id="f4b52-109">En este tema se describe cómo modificar el trabajo de copia de seguridad de BizTalk Server para incluir la base de datos personalizada de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="f4b52-109">This topic describes how to modify the Backup BizTalk Server job to include the custom A4SWIFT database.</span></span>