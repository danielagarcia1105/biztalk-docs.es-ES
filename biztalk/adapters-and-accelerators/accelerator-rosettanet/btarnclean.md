---
title: BtarnClean | Microsoft Docs
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f94c69552a59cf8cae8a12e056502ae405638e69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992845"
---
# <a name="btarnclean"></a><span data-ttu-id="dfff0-102">BtarnClean</span><span class="sxs-lookup"><span data-stu-id="dfff0-102">BtarnClean</span></span>
<span data-ttu-id="dfff0-103">Use la utilidad BtarnClean para limpiar Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artefactos desactivado de un equipo.</span><span class="sxs-lookup"><span data-stu-id="dfff0-103">You use the BtarnClean utility to clean Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artifacts off a computer.</span></span> <span data-ttu-id="dfff0-104">Esto incluye las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dfff0-104">This includes the following actions:</span></span>  
  
- <span data-ttu-id="dfff0-105">Detener y dar de baja todas las [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orquestaciones</span><span class="sxs-lookup"><span data-stu-id="dfff0-105">Stopping and unenlisting all the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orchestrations</span></span>  
  
- <span data-ttu-id="dfff0-106">Detener y eliminar todos los puertos asociados</span><span class="sxs-lookup"><span data-stu-id="dfff0-106">Stopping and deleting all the associated ports</span></span>  
  
- <span data-ttu-id="dfff0-107">Anular la implementación de todas las DLL. Ensamblados Solutions.btarn</span><span class="sxs-lookup"><span data-stu-id="dfff0-107">Undeploying all the Microsoft .Solutions.BTARN.\* assemblies</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="dfff0-108">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="dfff0-108">Location in SDK</span></span>  
 <span data-ttu-id="dfff0-109">\<*unidad*\>archivos \Program (x86) \ Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="dfff0-109">\<*drive*\>\Program Files (x86)\ Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-btarnclean"></a><span data-ttu-id="dfff0-110">Ejecutar BtarnClean</span><span class="sxs-lookup"><span data-stu-id="dfff0-110">Running BtarnClean</span></span>  
  
#### <a name="to-run-btarnclean"></a><span data-ttu-id="dfff0-111">Para ejecutar BtarnClean</span><span class="sxs-lookup"><span data-stu-id="dfff0-111">To run BtarnClean</span></span>  
  
1.  <span data-ttu-id="dfff0-112">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="dfff0-112">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="dfff0-113">Mover a \< *unidad*\>\ archivos de programa (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.</span><span class="sxs-lookup"><span data-stu-id="dfff0-113">Move to \<*drive*\>\ Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="dfff0-114">En el símbolo del sistema, escriba **BtarnClean**y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dfff0-114">At the command prompt, type **BtarnClean**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="dfff0-115">La utilidad le pedirá que confirme que desea continuar.</span><span class="sxs-lookup"><span data-stu-id="dfff0-115">The utility prompts you to verify that you want to continue.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfff0-116">Notas</span><span class="sxs-lookup"><span data-stu-id="dfff0-116">Remarks</span></span>  
 <span data-ttu-id="dfff0-117">Si ejecuta la utilidad BtarnClean en un equipo que tiene un artefacto de BizTalk que depende de otros artefactos, BtarnClean indicará que no puede quitar el artefacto.</span><span class="sxs-lookup"><span data-stu-id="dfff0-117">If you run the BtarnClean utility on a computer that has a BizTalk artifact that depends on other artifacts, BtarnClean will indicate that it cannot remove the artifact.</span></span> <span data-ttu-id="dfff0-118">La utilidad dejar dicho artefacto en su lugar y continuará para quitar otros artefactos.</span><span class="sxs-lookup"><span data-stu-id="dfff0-118">The utility will leave that artifact in place and continue to remove other artifacts.</span></span> <span data-ttu-id="dfff0-119">Puede quitar las dependencias y, a continuación, volver a ejecutar la utilidad.</span><span class="sxs-lookup"><span data-stu-id="dfff0-119">You can remove dependencies, and then run the utility again.</span></span>  
  
 <span data-ttu-id="dfff0-120">Si ejecuta la utilidad BtarnClean en un equipo que forma parte de una implementación de varios equipos, el resto de los servidores de dicha implementación se verá afectado cuando se quiten los artefactos.</span><span class="sxs-lookup"><span data-stu-id="dfff0-120">If you run the BtarnClean utility on a computer that is part of a multi-computer deployment, removing the artifacts will affect the rest of the servers in that deployment.</span></span>  
  
 <span data-ttu-id="dfff0-121">Si ejecuta la utilidad BtarnClean cuando existen varios procesos creados por los desarrolladores, la utilidad no quitará los procesos que estén en uso.</span><span class="sxs-lookup"><span data-stu-id="dfff0-121">If you run the BtarnClean utility when multiple processes created by developers exist, the utility will not remove processes that are still in use.</span></span>  
  
 <span data-ttu-id="dfff0-122">La utilidad BtarnClean no quitará una ubicación de recepción primaria si el artefacto de un usuario usa dicha ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="dfff0-122">The BtarnClean utility will not remove a primary receive location if a user's artifact uses that receive location.</span></span> <span data-ttu-id="dfff0-123">Si este es el caso, debe eliminar el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="dfff0-123">If this is the case, you must delete the receive port.</span></span>  
  
 <span data-ttu-id="dfff0-124">Si desea quitar la configuración de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] después de ejecutar la utilidad, ejecute Configuration.exe /u desde la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta.</span><span class="sxs-lookup"><span data-stu-id="dfff0-124">If you want to unconfigure [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] after running the utility, run Configuration.exe /u from the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfff0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfff0-125">See Also</span></span>  
 [<span data-ttu-id="dfff0-126">Utilidades</span><span class="sxs-lookup"><span data-stu-id="dfff0-126">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
