---
title: Información general sobre la implementación de SSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying example
- SSO, deploying
- deploying, SSO
- SSO, multiple computers
- examples, deploying
ms.assetid: 6eccee26-c392-41fe-97fb-3afe1685540f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c98a12c11ae735945f4e69631e7211c05c0b9186
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022370"
---
# <a name="sso-deployment-overview"></a><span data-ttu-id="bfa01-102">Información general sobre la implementación de SSO</span><span class="sxs-lookup"><span data-stu-id="bfa01-102">SSO Deployment Overview</span></span>
<span data-ttu-id="bfa01-103">El sistema de este ejemplo se implementa en tres dominios que contienen los siguientes equipos:</span><span class="sxs-lookup"><span data-stu-id="bfa01-103">The system in this example is deployed over three domains, containing the following computers:</span></span>  
  
 <span data-ttu-id="bfa01-104">**Dominio ORCH.com**</span><span class="sxs-lookup"><span data-stu-id="bfa01-104">**Domain ORCH.com**</span></span>  
  
- <span data-ttu-id="bfa01-105">Controlador de dominio ORCH</span><span class="sxs-lookup"><span data-stu-id="bfa01-105">ORCH domain controller</span></span>  
  
- <span data-ttu-id="bfa01-106">HIS1, el servidor HISSO</span><span class="sxs-lookup"><span data-stu-id="bfa01-106">HIS1, the HISSO server</span></span>  
  
- <span data-ttu-id="bfa01-107">HIS2, el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="bfa01-107">HIS2, the Master Secret Server</span></span>  
  
- <span data-ttu-id="bfa01-108">HIS3, la base de datos de administración</span><span class="sxs-lookup"><span data-stu-id="bfa01-108">HIS3, the Admin database</span></span>  
  
  <span data-ttu-id="bfa01-109">**Dominio SQL.com**</span><span class="sxs-lookup"><span data-stu-id="bfa01-109">**Domain SQL.com**</span></span>  
  
- <span data-ttu-id="bfa01-110">Controlador de dominio SQL</span><span class="sxs-lookup"><span data-stu-id="bfa01-110">SQL domain controller</span></span>  
  
- <span data-ttu-id="bfa01-111">SQL2, la base de datos de SSO</span><span class="sxs-lookup"><span data-stu-id="bfa01-111">SQL2, the SSO database</span></span>  
  
  <span data-ttu-id="bfa01-112">**Dominio HIS.com**</span><span class="sxs-lookup"><span data-stu-id="bfa01-112">**Domain HIS.com**</span></span>  
  
- <span data-ttu-id="bfa01-113">Controlador de dominio HIS</span><span class="sxs-lookup"><span data-stu-id="bfa01-113">HIS domain controller</span></span>  
  
- <span data-ttu-id="bfa01-114">Base de datos HIS4</span><span class="sxs-lookup"><span data-stu-id="bfa01-114">HIS4 database</span></span>  
  
  <span data-ttu-id="bfa01-115">Los puntos clave que definen esta implementación son:</span><span class="sxs-lookup"><span data-stu-id="bfa01-115">The key points defining this deployment are as follows:</span></span>  
  
- <span data-ttu-id="bfa01-116">El domino ORCH.com y el dominio SQL.com tienen una relación de confianza selectiva bidireccional.</span><span class="sxs-lookup"><span data-stu-id="bfa01-116">Domain ORCH.com and domain SQL.com have a two-way selective trust relationship.</span></span>  
  
- <span data-ttu-id="bfa01-117">El dominio ORCH.com está configurado con nivel funcional [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] nativo.</span><span class="sxs-lookup"><span data-stu-id="bfa01-117">Domain ORCH.com is configured as native [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] functional level.</span></span>  
  
- <span data-ttu-id="bfa01-118">Todos los servicios SSO se ejecutan con una cuenta de usuario del dominio ORCH.com (Orch\SSOSvcUser).</span><span class="sxs-lookup"><span data-stu-id="bfa01-118">All SSO services are running on an ORCH.com domain user account (Orch\SSOSvcUser).</span></span> <span data-ttu-id="bfa01-119">El usuario está configurado con permiso de acceso en el equipo SQL2 del dominio SQL.com.</span><span class="sxs-lookup"><span data-stu-id="bfa01-119">The user is configured to have access permission on the SQL2 machine in the SQL.com domain.</span></span> <span data-ttu-id="bfa01-120">El usuario está configurado para transición de protocolo y delegación restringida en el dominio ORCH.com.</span><span class="sxs-lookup"><span data-stu-id="bfa01-120">The user is configured for protocol transition and constrain delegation within the ORCH.com domain.</span></span>  
  
- <span data-ttu-id="bfa01-121">Otro usuario del dominio ORCH.com (Orch\TestAppUser) está establecido para ejecutar programas de prueba.</span><span class="sxs-lookup"><span data-stu-id="bfa01-121">Another ORCH.com domain user (Orch\TestAppUser) is set for running test programs.</span></span> <span data-ttu-id="bfa01-122">Este usuario está también configurado para transición de protocolo y delegación restringida.</span><span class="sxs-lookup"><span data-stu-id="bfa01-122">This user is also configured for protocol transition and constrain delegation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa01-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfa01-123">See Also</span></span>  
 [<span data-ttu-id="bfa01-124">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="bfa01-124">Deployment Process</span></span>](../core/deployment-process.md)