---
title: Mantenimiento de bases de datos BTARN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maintaining databases
- databases, maintaining
ms.assetid: b048f68c-1e12-42e3-b7bb-2a87fe977f4e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 496e83311c4ede6446bad8893fbe37b22cf8420d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000773"
---
# <a name="maintaining-btarn-databases"></a><span data-ttu-id="c42ac-102">Mantener bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="c42ac-102">Maintaining BTARN Databases</span></span>
<span data-ttu-id="c42ac-103">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] bases de datos pueden crecer hasta que su tamaño puede afectar al rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="c42ac-103">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] databases can grow so large that their size can affect system performance.</span></span> <span data-ttu-id="c42ac-104">Esto puede producir en circunstancias concretas que dejan las entradas no utilizadas en las tablas, como datos adjuntos huérfanos o resúmenes sin usar.</span><span class="sxs-lookup"><span data-stu-id="c42ac-104">This can result from specific circumstances that leave unused entries in the tables, such as orphan attachments or unused digests.</span></span> <span data-ttu-id="c42ac-105">También puede producirse de no eliminar las entradas más antiguas en las tablas.</span><span class="sxs-lookup"><span data-stu-id="c42ac-105">It can also occur from not deleting old entries in the tables.</span></span> <span data-ttu-id="c42ac-106">Siga los procedimientos descritos en esta sección para mantener su [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] por lo que no hay ningún efecto en el rendimiento de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c42ac-106">Follow the procedures in this section to maintain your [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] databases so there is no effect on performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c42ac-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c42ac-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c42ac-108">Mantenimiento de las tablas de la base de datos sin repudio</span><span class="sxs-lookup"><span data-stu-id="c42ac-108">Maintaining the Non-Repudiation Database Tables</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-the-non-repudiation-database-tables.md)  
  
-   [<span data-ttu-id="c42ac-109">Eliminación de resúmenes</span><span class="sxs-lookup"><span data-stu-id="c42ac-109">Deleting Digests</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md)  
  
-   [<span data-ttu-id="c42ac-110">Eliminación de datos adjuntos huérfanos</span><span class="sxs-lookup"><span data-stu-id="c42ac-110">Deleting Orphan Attachments</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/deleting-orphan-attachments.md)