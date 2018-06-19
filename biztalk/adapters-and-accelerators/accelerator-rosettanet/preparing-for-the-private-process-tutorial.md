---
title: Requisitos previos para el tutorial de procesos de RosettaNet privados en BizTalk Server | Documentos de Microsoft
description: Requisitos previos para recorrer el tutorial de procesos privados para el Acelerador para RosettaNet (BTARN) en BizTalk Server
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
ms.openlocfilehash: 580edcc7a8d779067895fb5aac99d81a1ad76872
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963418"
---
# <a name="prepare-for-the-private-process-tutorial"></a><span data-ttu-id="10603-103">Prepararse para el tutorial de procesos privado</span><span class="sxs-lookup"><span data-stu-id="10603-103">Prepare for the Private Process tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10603-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="10603-104">Prerequisites</span></span>
<span data-ttu-id="10603-105">Antes de iniciar el tutorial:</span><span class="sxs-lookup"><span data-stu-id="10603-105">Before starting the tutorial:</span></span>
  
-   <span data-ttu-id="10603-106">Realice una instalación completa de BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en dos equipos.</span><span class="sxs-lookup"><span data-stu-id="10603-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="10603-107">Para obtener más información, consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="10603-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="10603-108">Asegúrese de configurar totalmente el Acelerador para RosettaNet, incluido el inicio de las orquestaciones de BTARN.</span><span class="sxs-lookup"><span data-stu-id="10603-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="10603-109">Vea [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="10603-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span> <span data-ttu-id="10603-110">También es podrán que deba agregar la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] directorios virtuales (incluidos los btarnhttpreceive) a la lista de exclusión de la ruta de acceso administrado de Microsoft Windows® SharePoint™ Services.</span><span class="sxs-lookup"><span data-stu-id="10603-110">You may also have to add the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] virtual directories (including btarnhttpreceive) to the Microsoft Windows® SharePoint™ Services managed path exclusion list.</span></span> 
  
-   <span data-ttu-id="10603-111">Este tutorial simula un escenario real mediante el uso de dos equipos en lugar de un único equipo con un contrato de bucle invertido.</span><span class="sxs-lookup"><span data-stu-id="10603-111">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loop-back agreement.</span></span> <span data-ttu-id="10603-112">Cada vez que este tutorial usa nombres de equipo, utiliza un marcador de posición como el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="10603-112">Whenever this tutorial uses computer names, it uses a placeholder as the computer name.</span></span> <span data-ttu-id="10603-113">Reemplace ese marcador de posición con el nombre real del equipo elegido.</span><span class="sxs-lookup"><span data-stu-id="10603-113">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="10603-114">Por ejemplo, si el equipo que está ejecutando la solución de Contoso se denomina **Contoso**, reemplace las apariciones en el tutorial de \\ \\< contoso **_**  *equipo* \> con ese nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="10603-114">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso **_***computer*\> with that computer name.</span></span>  
  
 <span data-ttu-id="10603-115">Este tutorial promueve una comunicación segura a través de certificados entre Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="10603-115">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="10603-116">Debe generar los certificados que requiere e instalarlos en los equipos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="10603-116">You must generate any certificates you require, and install them on the respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="10603-117">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="10603-117">Next steps</span></span>
  
-   [<span data-ttu-id="10603-118">Restauración de la base de datos de Contoso</span><span class="sxs-lookup"><span data-stu-id="10603-118">Restoring the Contoso Database</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [<span data-ttu-id="10603-119">Generación y habilitación de certificados</span><span class="sxs-lookup"><span data-stu-id="10603-119">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)