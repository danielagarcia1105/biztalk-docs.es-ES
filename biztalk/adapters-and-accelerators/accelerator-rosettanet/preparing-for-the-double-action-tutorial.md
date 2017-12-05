---
title: "Requisitos previos para el tutorial de doble acción de RosettaNet en BizTalk Server | Documentos de Microsoft"
description: "Requisitos previos para recorrer el tutorial de doble acción para el Acelerador para RosettaNet (BTARN) en BizTalk Server"
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc247aa1ab9ec7cb6f056cd45df54bc324990ad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="prepare-for-the-double-action-tutorial"></a><span data-ttu-id="150ce-103">Prepararse para el tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="150ce-103">Prepare for the Double Action tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="150ce-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="150ce-104">Prerequisites</span></span>
<span data-ttu-id="150ce-105">Antes de iniciar el tutorial:</span><span class="sxs-lookup"><span data-stu-id="150ce-105">Before starting the tutorial:</span></span>
  
-   <span data-ttu-id="150ce-106">Realice una instalación completa de BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en dos equipos.</span><span class="sxs-lookup"><span data-stu-id="150ce-106">Do a full installation of BizTalk Server and [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on two computers.</span></span> <span data-ttu-id="150ce-107">Para obtener más información, consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="150ce-107">For more information, see [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="150ce-108">Asegúrese de configurar totalmente el Acelerador para RosettaNet, incluido el inicio de las orquestaciones de BTARN.</span><span class="sxs-lookup"><span data-stu-id="150ce-108">Be sure that you fully configure the RosettaNet accelerator, including starting the BTARN orchestrations.</span></span> <span data-ttu-id="150ce-109">Vea [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).</span><span class="sxs-lookup"><span data-stu-id="150ce-109">See [Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
-   <span data-ttu-id="150ce-110">Este tutorial simula un escenario real mediante el uso de dos equipos en lugar de un único equipo con un contrato de bucle invertido.</span><span class="sxs-lookup"><span data-stu-id="150ce-110">This tutorial simulates a real-world scenario by using two computers instead of a single computer with a loopback agreement.</span></span> <span data-ttu-id="150ce-111">Cada vez que este tutorial usa nombres de equipo, utiliza un marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="150ce-111">Whenever this tutorial uses computer names, it uses a placeholder.</span></span> <span data-ttu-id="150ce-112">Reemplace ese marcador de posición con el nombre real del equipo elegido.</span><span class="sxs-lookup"><span data-stu-id="150ce-112">Replace that placeholder with the actual computer name you chose.</span></span> <span data-ttu-id="150ce-113">Por ejemplo, si el equipo que está ejecutando la solución de Contoso se denomina **Contoso**, reemplace las apariciones en el tutorial de \\ \\< contoso**_**  *equipo* \> con ese nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="150ce-113">For example, if the computer that is running your Contoso solution is named **Contoso**, replace any occurrences in the tutorial of \\\\<contoso**_***computer*\> with that computer name.</span></span>  
  
-   <span data-ttu-id="150ce-114">Este tutorial promueve una comunicación segura a través de certificados entre Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="150ce-114">This tutorial promotes secure communication through certificates between Contoso and Fabrikam.</span></span> <span data-ttu-id="150ce-115">Debe generar los certificados que requiere e instalarlas en sus respectivos equipos.</span><span class="sxs-lookup"><span data-stu-id="150ce-115">You must generate any certificates you require, and install them on their respective computers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="150ce-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="150ce-116">Next steps</span></span> 
  
-   [<span data-ttu-id="150ce-117">Paso 1: Crear una entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="150ce-117">Step 1: Creating a Certification Authority</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [<span data-ttu-id="150ce-118">Paso 2: Crear certificados públicos y privados</span><span class="sxs-lookup"><span data-stu-id="150ce-118">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="150ce-119">Paso 3: Importar certificados públicos y privados</span><span class="sxs-lookup"><span data-stu-id="150ce-119">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [<span data-ttu-id="150ce-120">Paso 4: Habilitar Capa de sockets seguros en IIS</span><span class="sxs-lookup"><span data-stu-id="150ce-120">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)