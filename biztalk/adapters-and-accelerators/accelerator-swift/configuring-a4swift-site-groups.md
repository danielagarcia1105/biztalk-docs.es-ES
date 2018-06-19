---
title: Configuración de grupos de sitio de A4SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0070f10819ebbde18cdeab9c3bd534ca74bfbcd9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209012"
---
# <a name="configuring-a4swift-site-groups"></a><span data-ttu-id="251b9-102">Configuración de grupos de sitio de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="251b9-102">Configuring A4SWIFT Site Groups</span></span>
<span data-ttu-id="251b9-103">Debe crear los grupos de sitio correspondiente para restringir los permisos en las bibliotecas de documentos que se crearon durante la configuración de reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="251b9-103">You need to create the corresponding site groups to lock down the permissions on the document libraries created during Message Repair and New Submission configuration.</span></span> <span data-ttu-id="251b9-104">Para realizar esta acción con el ejemplo en la sección anterior, un administrador de A4SWIFT ¿vaya al sitio MRSR y configurar los grupos de sitio siguientes:</span><span class="sxs-lookup"><span data-stu-id="251b9-104">To do so with the example in the preceding section, an A4SWIFT Administrator would go to the MRSR site and set up the following site groups:</span></span>  
  
-   <span data-ttu-id="251b9-105">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="251b9-105">Payments_Creators</span></span>  
  
-   <span data-ttu-id="251b9-106">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="251b9-106">Payments_Repairers</span></span>  
  
-   <span data-ttu-id="251b9-107">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="251b9-107">Payments_Approvers</span></span>  
  
 <span data-ttu-id="251b9-108">Para cada uno de estos grupos de sitio se deben aplicar los permisos siguientes:</span><span class="sxs-lookup"><span data-stu-id="251b9-108">For each of these site groups the following permissions should be applied:</span></span>  
  
-   <span data-ttu-id="251b9-109">**Ver elementos.**</span><span class="sxs-lookup"><span data-stu-id="251b9-109">**View Items.**</span></span> <span data-ttu-id="251b9-110">Ver elementos en listas, documentos en bibliotecas de documentos, ver comentarios de discusión Web y configurar alertas de correo electrónico para las listas.</span><span class="sxs-lookup"><span data-stu-id="251b9-110">View items in lists, documents in document libraries, view Web discussion comments, and set up e-mail alerts for lists.</span></span>  
  
-   <span data-ttu-id="251b9-111">**Páginas de vista.**</span><span class="sxs-lookup"><span data-stu-id="251b9-111">**View Pages.**</span></span> <span data-ttu-id="251b9-112">Ver páginas en un sitio Web.</span><span class="sxs-lookup"><span data-stu-id="251b9-112">View pages in a Web site.</span></span>  
  
 <span data-ttu-id="251b9-113">Para cada usuario que participa en los roles para el departamento de pagos, debe crear un nuevo usuario del sitio y asignar ese usuario al grupo de sitio que se corresponde con [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles que se crearon durante la configuración de MMC.</span><span class="sxs-lookup"><span data-stu-id="251b9-113">For each user who participates in the roles for the Payments department, you need to create a new site user and assign that user to the site group that corresponds to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles created during MMC configuration.</span></span>