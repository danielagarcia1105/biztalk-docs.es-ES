---
title: Instalar el Software necesario, utilidades y ejemplos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f92f4cc994b4139c1c33423cc7a94c9072e226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965909"
---
# <a name="install-the-required-software-utilities-and-samples"></a><span data-ttu-id="01afa-102">Instalar el Software necesario, utilidades y ejemplos</span><span class="sxs-lookup"><span data-stu-id="01afa-102">Install the Required Software, Utilities, and Samples</span></span>
<span data-ttu-id="01afa-103">Este tutorial requiere Microsoft Windows Server y Microsoft personalizado [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] instalación que incluye las herramientas de prueba de MLLP.</span><span class="sxs-lookup"><span data-stu-id="01afa-103">This tutorial requires Microsoft Windows Server, and a custom Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation that includes the MLLP Test Tools.</span></span> <span data-ttu-id="01afa-104">Además, debe estar familiarizado con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] desarrollo en Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] y [Obtenga información sobre el Acelerador de HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span><span class="sxs-lookup"><span data-stu-id="01afa-104">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>
  
 <span data-ttu-id="01afa-105">Debe tener las siguientes utilidades y ejemplos instalados en el equipo:</span><span class="sxs-lookup"><span data-stu-id="01afa-105">You must have the following utilities and samples installed on your computer:</span></span>  
  
- <span data-ttu-id="01afa-106">**Herramienta MllpSend**</span><span class="sxs-lookup"><span data-stu-id="01afa-106">**MllpSend Tool**</span></span>  
  
   <span data-ttu-id="01afa-107">Esta utilidad de línea de comandos envía un mensaje a través el protocolo de capa inferior (MLLP) mínima ubicación de recepción de protocolo para una MLLP.</span><span class="sxs-lookup"><span data-stu-id="01afa-107">This command-line utility sends a message over the Minimal Lower Layer Protocol (MLLP) protocol to an MLLP receive location.</span></span> <span data-ttu-id="01afa-108">Usarlo para probar los resultados del tutoriales.</span><span class="sxs-lookup"><span data-stu-id="01afa-108">You use it to test your tutorial results.</span></span> <span data-ttu-id="01afa-109">Para obtener más información, consulte [herramienta MllpSend](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).</span><span class="sxs-lookup"><span data-stu-id="01afa-109">For more information, see [MllpSend Tool](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).</span></span>  
  
- <span data-ttu-id="01afa-110">**Herramienta MllpPReceive**</span><span class="sxs-lookup"><span data-stu-id="01afa-110">**MllpPReceive Tool**</span></span>  
  
   <span data-ttu-id="01afa-111">Esta utilidad de línea de comandos recibe mensajes a través del protocolo MLLP, que actúa como un agente de escucha de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="01afa-111">This command-line utility receives messages over the MLLP protocol, serving as a receive-location listener.</span></span> <span data-ttu-id="01afa-112">Usa para probar los resultados del tutoriales, la presentación de mensajes y las confirmaciones recibidas.</span><span class="sxs-lookup"><span data-stu-id="01afa-112">You use it to test your tutorial results, displaying messages and acknowledgments received.</span></span> <span data-ttu-id="01afa-113">Para obtener más información, consulte [herramienta MllpReceive](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).</span><span class="sxs-lookup"><span data-stu-id="01afa-113">For more information, see [MllpReceive Tool](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).</span></span>  
  
- <span data-ttu-id="01afa-114">**Aplicación de ejemplo acepta ACK.txt**</span><span class="sxs-lookup"><span data-stu-id="01afa-114">**Sample Application Accept ACK.txt**</span></span>  
  
   <span data-ttu-id="01afa-115">Este archivo de ejemplo contiene el texto de un mensaje de confirmación de aceptación de aplicación.</span><span class="sxs-lookup"><span data-stu-id="01afa-115">This sample file contains the text of an application-accept acknowledgment message.</span></span> <span data-ttu-id="01afa-116">El ejemplo funciona con la herramienta MllpReceive, que recibe y muestra los mensajes y, a continuación, envía las confirmaciones de vuelta en el archivo de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="01afa-116">The sample works with the MllpReceive tool, which receives and displays messages, then sends back the acknowledgment(s) in the sample file.</span></span>  
  
  <span data-ttu-id="01afa-117">Deberá instalar las dos herramientas y el archivo de ejemplo mediante el proceso de instalación de BTAHL7 personalizado.</span><span class="sxs-lookup"><span data-stu-id="01afa-117">You need to install the two tools and the sample file by using the BTAHL7 Custom installation process.</span></span> <span data-ttu-id="01afa-118">El proceso de instalación típica no instala estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="01afa-118">The Typical installation process does not install these tools.</span></span> <span data-ttu-id="01afa-119">Para instalar estas herramientas, ejecute la instalación personalizada de BTAHL7, en el **instalación personalizada** pantalla, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **Las instancias de prueba** desde el **artefactos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="01afa-119">To install these tools, run the BTAHL7 custom installation, at the **Custom Setup** screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="01afa-120">Para obtener más información, consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span><span class="sxs-lookup"><span data-stu-id="01afa-120">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01afa-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="01afa-121">See Also</span></span>  
 [<span data-ttu-id="01afa-122">Preparación para usar el tutorial de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="01afa-122">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)