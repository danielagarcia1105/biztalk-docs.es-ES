---
title: Requisitos previos del tutorial de procesos privados de RosettaNet en BizTalk Server | Microsoft Docs
description: Requisitos previos para recorrer el tutorial de procesos privados para el Acelerador de RosettaNet (BTARN) en BizTalk Server
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 823788385b659f5aa26d4aa92db1e234f2773600
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010933"
---
# <a name="prepare-for-the-private-process-tutorial"></a><span data-ttu-id="9d354-103">Prepararse para el tutorial de procesos privados</span><span class="sxs-lookup"><span data-stu-id="9d354-103">Prepare for the Private Process tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d354-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9d354-104">Prerequisites</span></span>
<span data-ttu-id="9d354-105">Antes de comenzar el tutorial:</span><span class="sxs-lookup"><span data-stu-id="9d354-105">Before starting the tutorial:</span></span>
  
- <span data-ttu-id="9d354-106">Realizar una instalación completa de BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en dos equipos.</span><span class="sxs-lookup"><span data-stu-id="9d354-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="9d354-107">Para obtener más información, consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="9d354-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="9d354-108">Asegúrese de que configurar completamente el Acelerador de RosettaNet, incluido el inicio de las orquestaciones de BTARN.</span><span class="sxs-lookup"><span data-stu-id="9d354-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="9d354-109">Consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="9d354-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span> <span data-ttu-id="9d354-110">También es posible que deba agregar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] directorios virtuales (incluidos btarnhttpreceive) a la lista de exclusión de ruta de acceso administrada de Microsoft Windows® SharePoint™ Services.</span><span class="sxs-lookup"><span data-stu-id="9d354-110">You may also have to add the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] virtual directories (including btarnhttpreceive) to the Microsoft Windows® SharePoint™ Services managed path exclusion list.</span></span> 
  
- <span data-ttu-id="9d354-111">Este tutorial simula un escenario del mundo real con dos equipos en lugar de un solo equipo con un acuerdo de bucle invertido.</span><span class="sxs-lookup"><span data-stu-id="9d354-111">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loop-back agreement.</span></span> <span data-ttu-id="9d354-112">Cada vez que este tutorial usa los nombres de equipo, utiliza un marcador de posición como el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="9d354-112">Whenever this tutorial uses computer names, it uses a placeholder as the computer name.</span></span> <span data-ttu-id="9d354-113">Reemplace el marcador de posición con el nombre real del equipo que eligió.</span><span class="sxs-lookup"><span data-stu-id="9d354-113">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="9d354-114">Por ejemplo, si el equipo que ejecuta la solución de Contoso se denomina **Contoso**, reemplace las apariciones en el tutorial de \\ \\< contoso<strong>_</strong>  *equipo* \> con ese nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="9d354-114">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso<strong>_</strong>*computer*\> with that computer name.</span></span>  
  
  <span data-ttu-id="9d354-115">En este tutorial se promueve una comunicación segura a través de certificados entre Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="9d354-115">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="9d354-116">Debe generar los certificados que requiere e instalarlos en los respectivos equipos.</span><span class="sxs-lookup"><span data-stu-id="9d354-116">You must generate any certificates you require, and install them on the respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9d354-117">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9d354-117">Next steps</span></span>
  
-   [<span data-ttu-id="9d354-118">Restauración de la base de datos de Contoso</span><span class="sxs-lookup"><span data-stu-id="9d354-118">Restoring the Contoso Database</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [<span data-ttu-id="9d354-119">Generación y habilitación de certificados</span><span class="sxs-lookup"><span data-stu-id="9d354-119">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)