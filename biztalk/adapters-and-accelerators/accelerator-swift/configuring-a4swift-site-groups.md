---
title: Configuración de grupos de sitio de A4SWIFT | Microsoft Docs
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
ms.openlocfilehash: 7f19db0461fc4dc5584fa0774ba0476e3ee471b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969773"
---
# <a name="configuring-a4swift-site-groups"></a><span data-ttu-id="9a999-102">Configuración de grupos de sitio de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="9a999-102">Configuring A4SWIFT Site Groups</span></span>
<span data-ttu-id="9a999-103">Deberá crear los grupos de sitio correspondiente a bloquear los permisos en las bibliotecas de documentos que se creó durante la configuración de reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="9a999-103">You need to create the corresponding site groups to lock down the permissions on the document libraries created during Message Repair and New Submission configuration.</span></span> <span data-ttu-id="9a999-104">Para hacer esto con el ejemplo en la sección anterior, un administrador de A4SWIFT podría ir al sitio MRSR y configurar los grupos de sitio siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a999-104">To do so with the example in the preceding section, an A4SWIFT Administrator would go to the MRSR site and set up the following site groups:</span></span>  
  
- <span data-ttu-id="9a999-105">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="9a999-105">Payments_Creators</span></span>  
  
- <span data-ttu-id="9a999-106">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="9a999-106">Payments_Repairers</span></span>  
  
- <span data-ttu-id="9a999-107">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="9a999-107">Payments_Approvers</span></span>  
  
  <span data-ttu-id="9a999-108">Para cada uno de estos grupos de sitio se deben aplicar los permisos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a999-108">For each of these site groups the following permissions should be applied:</span></span>  
  
- <span data-ttu-id="9a999-109">**Ver elementos.**</span><span class="sxs-lookup"><span data-stu-id="9a999-109">**View Items.**</span></span> <span data-ttu-id="9a999-110">Ver elementos de listas, documentos en bibliotecas de documentos, ver comentarios de discusiones Web y configurar alertas de correo electrónico para las listas.</span><span class="sxs-lookup"><span data-stu-id="9a999-110">View items in lists, documents in document libraries, view Web discussion comments, and set up e-mail alerts for lists.</span></span>  
  
- <span data-ttu-id="9a999-111">**Ver las páginas.**</span><span class="sxs-lookup"><span data-stu-id="9a999-111">**View Pages.**</span></span> <span data-ttu-id="9a999-112">Ver páginas en un sitio Web.</span><span class="sxs-lookup"><span data-stu-id="9a999-112">View pages in a Web site.</span></span>  
  
  <span data-ttu-id="9a999-113">Para cada usuario que participa en los roles para el departamento de pagos, deberá crear un nuevo usuario del sitio y asignar ese usuario al grupo de sitio que se corresponde con [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles creados durante la configuración de MMC.</span><span class="sxs-lookup"><span data-stu-id="9a999-113">For each user who participates in the roles for the Payments department, you need to create a new site user and assign that user to the site group that corresponds to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles created during MMC configuration.</span></span>