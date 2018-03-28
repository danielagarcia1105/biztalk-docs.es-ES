---
title: BtarnClean | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BtarnClean utility
- assemblies, undeploying
- BTARN, deleting artifacts
- orchestrations, unenlisting
- ports, stopping
- orchestrations, stopping
- ports, deleting
- BTARN, BtarnClean utility
ms.assetid: fbecbb88-9b18-4b4b-a286-0bfa783f2320
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa8e448d4799329a798cc7b33f222b42c4a28b4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="btarnclean"></a><span data-ttu-id="670e4-102">BtarnClean</span><span class="sxs-lookup"><span data-stu-id="670e4-102">BtarnClean</span></span>
<span data-ttu-id="670e4-103">Use la utilidad BtarnClean para limpiar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artefactos desactivado un equipo.</span><span class="sxs-lookup"><span data-stu-id="670e4-103">You use the BtarnClean utility to clean [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artifacts off a computer.</span></span> <span data-ttu-id="670e4-104">Esto incluye las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="670e4-104">This includes the following actions:</span></span>  
  
-   <span data-ttu-id="670e4-105">Detener y dar de baja todas las [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orquestaciones</span><span class="sxs-lookup"><span data-stu-id="670e4-105">Stopping and unenlisting all the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orchestrations</span></span>  
  
-   <span data-ttu-id="670e4-106">Detener y eliminar todos los puertos asociados</span><span class="sxs-lookup"><span data-stu-id="670e4-106">Stopping and deleting all the associated ports</span></span>  
  
-   <span data-ttu-id="670e4-107">Anular la implementación de todos los [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Ensamblados de Solutions.BTARN.\*</span><span class="sxs-lookup"><span data-stu-id="670e4-107">Undeploying all the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.BTARN.\* assemblies</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="670e4-108">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="670e4-108">Location in SDK</span></span>  
 <span data-ttu-id="670e4-109">\<*unidad*\>\Program Files\ Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="670e4-109">\<*drive*\>\Program Files\ Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-btarnclean"></a><span data-ttu-id="670e4-110">Ejecutar BtarnClean</span><span class="sxs-lookup"><span data-stu-id="670e4-110">Running BtarnClean</span></span>  
  
#### <a name="to-run-btarnclean"></a><span data-ttu-id="670e4-111">Para ejecutar BtarnClean</span><span class="sxs-lookup"><span data-stu-id="670e4-111">To run BtarnClean</span></span>  
  
1.  <span data-ttu-id="670e4-112">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="670e4-112">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="670e4-113">Mover a \< *unidad*\>\ programa comunes\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.</span><span class="sxs-lookup"><span data-stu-id="670e4-113">Move to \<*drive*\>\ Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="670e4-114">En el símbolo del sistema, escriba **BtarnClean**y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="670e4-114">At the command prompt, type **BtarnClean**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="670e4-115">La utilidad le pedirá que confirme que desea continuar.</span><span class="sxs-lookup"><span data-stu-id="670e4-115">The utility prompts you to verify that you want to continue.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="670e4-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="670e4-116">Remarks</span></span>  
 <span data-ttu-id="670e4-117">Si ejecuta la utilidad BtarnClean en un equipo que tiene un artefacto de BizTalk que depende de otros artefactos, BtarnClean indicará que no puede quitar el artefacto.</span><span class="sxs-lookup"><span data-stu-id="670e4-117">If you run the BtarnClean utility on a computer that has a BizTalk artifact that depends on other artifacts, BtarnClean will indicate that it cannot remove the artifact.</span></span> <span data-ttu-id="670e4-118">La utilidad dejar dicho artefacto en su lugar y continuará para quitar otros artefactos.</span><span class="sxs-lookup"><span data-stu-id="670e4-118">The utility will leave that artifact in place and continue to remove other artifacts.</span></span> <span data-ttu-id="670e4-119">Puede quitar las dependencias y, a continuación, volver a ejecutar la utilidad.</span><span class="sxs-lookup"><span data-stu-id="670e4-119">You can remove dependencies, and then run the utility again.</span></span>  
  
 <span data-ttu-id="670e4-120">Si ejecuta la utilidad BtarnClean en un equipo que forma parte de una implementación de varios equipos, el resto de los servidores de dicha implementación se verá afectado cuando se quiten los artefactos.</span><span class="sxs-lookup"><span data-stu-id="670e4-120">If you run the BtarnClean utility on a computer that is part of a multi-computer deployment, removing the artifacts will affect the rest of the servers in that deployment.</span></span>  
  
 <span data-ttu-id="670e4-121">Si ejecuta la utilidad BtarnClean cuando existen varios procesos creados por los desarrolladores, la utilidad no quitará los procesos que estén en uso.</span><span class="sxs-lookup"><span data-stu-id="670e4-121">If you run the BtarnClean utility when multiple processes created by developers exist, the utility will not remove processes that are still in use.</span></span>  
  
 <span data-ttu-id="670e4-122">La utilidad BtarnClean no quitará una ubicación de recepción primaria si el artefacto de un usuario usa dicha ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="670e4-122">The BtarnClean utility will not remove a primary receive location if a user's artifact uses that receive location.</span></span> <span data-ttu-id="670e4-123">Si este es el caso, debe eliminar el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="670e4-123">If this is the case, you must delete the receive port.</span></span>  
  
 <span data-ttu-id="670e4-124">Si desea quitar la configuración de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] después de ejecutar la utilidad, ejecute Configuration.exe /u desde el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta.</span><span class="sxs-lookup"><span data-stu-id="670e4-124">If you want to unconfigure [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] after running the utility, run Configuration.exe /u from the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="670e4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="670e4-125">See Also</span></span>  
 [<span data-ttu-id="670e4-126">Utilidades</span><span class="sxs-lookup"><span data-stu-id="670e4-126">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)