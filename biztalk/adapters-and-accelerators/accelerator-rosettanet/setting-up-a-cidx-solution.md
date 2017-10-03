---
title: "Configurar una solución CIDX | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CIDX, process configuration
- creating, CIDX solutions
- CIDX, connecting to Elemica network
- agreements, CIDX
- process configuration, CIDX
- CIDX, agreements
- PIPs, importing for CIDX
- CIDX, PIPs
- CIDX, creating solutions
- CIDX, importing PIPs
- PIPs, CIDX
ms.assetid: 7f1f159f-3b09-4efd-907b-9a75f7f3ecd1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab617efc701551f1d5bcbae2a292676cc4f33251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-up-a-cidx-solution"></a><span data-ttu-id="4cc49-102">Cómo configurar una solución CIDX</span><span class="sxs-lookup"><span data-stu-id="4cc49-102">Setting Up a CIDX Solution</span></span>
<span data-ttu-id="4cc49-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] compatibilidad con intercambio de mensajes XML CIDX (intercambio de datos de la industria química) (normas europeas de química CIDX las versiones 2.0 y 3.0).</span><span class="sxs-lookup"><span data-stu-id="4cc49-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] support for CIDX (Chemical Industry Data Exchange) XML message exchange (CIDX Chem eStandards versions 2.0 and 3.0).</span></span> <span data-ttu-id="4cc49-104">Este tema describe cómo configurar una solución CIDX haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cc49-104">This topic describes how to set up a CIDX solution by doing the following:</span></span>  
  
-   <span data-ttu-id="4cc49-105">Cómo configurar una configuración de procesos</span><span class="sxs-lookup"><span data-stu-id="4cc49-105">Setting up a process configuration</span></span>  
  
-   <span data-ttu-id="4cc49-106">Cómo configurar un acuerdo</span><span class="sxs-lookup"><span data-stu-id="4cc49-106">Setting up an agreement</span></span>  
  
-   <span data-ttu-id="4cc49-107">Aplicar un PIP</span><span class="sxs-lookup"><span data-stu-id="4cc49-107">Applying a PIP</span></span>  
  
-   <span data-ttu-id="4cc49-108">Importar un PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="4cc49-108">Importing an XSD-based PIP</span></span>  
  
-   <span data-ttu-id="4cc49-109">Conectarse a la red Elemica</span><span class="sxs-lookup"><span data-stu-id="4cc49-109">Connecting to the Elemica Network</span></span>  
  
## <a name="setting-up-a-cidx-process-configuration"></a><span data-ttu-id="4cc49-110">Cómo configurar una configuración de procesos CIDX</span><span class="sxs-lookup"><span data-stu-id="4cc49-110">Setting Up a CIDX Process Configuration</span></span>  
 <span data-ttu-id="4cc49-111">Para configurar un intercambio de mensajes de normas europeas CIDX, debe crear una configuración de proceso que tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4cc49-111">To set up a CIDX eStandards message exchange, you need to create a process configuration that has the following properties:</span></span>  
  
-   <span data-ttu-id="4cc49-112">**Estándar** propiedad en los valores de configuración de proceso establecido en **CIDX**</span><span class="sxs-lookup"><span data-stu-id="4cc49-112">**Standard** property in the process configuration settings set to **CIDX**</span></span>  
  
-   <span data-ttu-id="4cc49-113">**Es la única acción** propiedad en los valores de configuración de proceso establecido en **es True**</span><span class="sxs-lookup"><span data-stu-id="4cc49-113">**Is Single Action** property in the process configuration settings set to **True**</span></span>  
  
-   <span data-ttu-id="4cc49-114">**Acuerdo de 0A1** propiedad en el acuerdo de socio comercial establecido en **No 0A1**</span><span class="sxs-lookup"><span data-stu-id="4cc49-114">**0A1 agreement** property in the trading partner agreement set to **No 0A1**</span></span>  
  
 <span data-ttu-id="4cc49-115">Para obtener más información, consulte [normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span><span class="sxs-lookup"><span data-stu-id="4cc49-115">For more information, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
## <a name="creating-a-cidx-agreement"></a><span data-ttu-id="4cc49-116">Crear un acuerdo CIDX</span><span class="sxs-lookup"><span data-stu-id="4cc49-116">Creating a CIDX Agreement</span></span>  
 <span data-ttu-id="4cc49-117">Para configurar un intercambio de mensajes de normas europeas CIDX, debe crear un acuerdo que tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4cc49-117">To set up a CIDX eStandards message exchange, you need to create an agreement that has the following properties:</span></span>  
  
-   <span data-ttu-id="4cc49-118">**Versión de RNIF** propiedad en la configuración del acuerdo establecido en **V01.10.00**</span><span class="sxs-lookup"><span data-stu-id="4cc49-118">**RNIF Version** property in the agreement settings set to **V01.10.00**</span></span>  
  
-   <span data-ttu-id="4cc49-119">**Acuerdo de 0A1** propiedad en la configuración del acuerdo establecido en **No 0A1**</span><span class="sxs-lookup"><span data-stu-id="4cc49-119">**0A1 agreement** property in the agreement settings set to **No 0A1**</span></span>  
  
 <span data-ttu-id="4cc49-120">Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span><span class="sxs-lookup"><span data-stu-id="4cc49-120">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
## <a name="applying-a-pip-for-cidx"></a><span data-ttu-id="4cc49-121">Aplicar un PIP para CIDX</span><span class="sxs-lookup"><span data-stu-id="4cc49-121">Applying a PIP for CIDX</span></span>  
 <span data-ttu-id="4cc49-122">Para aplicar un PIP a una implementación CIDX, establezca el **estándar** propiedad en el perfil de configuración de proceso a **CIDX**.</span><span class="sxs-lookup"><span data-stu-id="4cc49-122">To apply a PIP to a CIDX implementation, set the **Standard** property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="4cc49-123">Cuando haya terminado, podrá especificar valores para la **estándar de mensajes**, **versión estándar**, y **Id. de enlace de carga**.</span><span class="sxs-lookup"><span data-stu-id="4cc49-123">After you have finished, you will be able to enter values for the **Message standard**, **Standard version**, and **Payload binding ID**.</span></span> <span data-ttu-id="4cc49-124">Puede encontrar estos valores en la especificación de normas europeas de química CIDX.</span><span class="sxs-lookup"><span data-stu-id="4cc49-124">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a><span data-ttu-id="4cc49-125">Importar una PIP basado en XSD para CIDX</span><span class="sxs-lookup"><span data-stu-id="4cc49-125">Importing an XSD-based PIP for CIDX</span></span>  
 <span data-ttu-id="4cc49-126">Para importar una PIP basado en XSD para CIDX, necesitará descargar el archivo ZIP del PIP de CIDX.org en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span><span class="sxs-lookup"><span data-stu-id="4cc49-126">To import an XSD-based PIP for CIDX, you need to download the PIP's ZIP file from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="4cc49-127">Siga el procedimiento de importación se describe en [importar una PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).</span><span class="sxs-lookup"><span data-stu-id="4cc49-127">Follow the import procedure described in [Importing an XSD-based PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="4cc49-128">Conectarse a la red Elemica</span><span class="sxs-lookup"><span data-stu-id="4cc49-128">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="4cc49-129">Puede personalizar [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica con archivos de proyecto en el módulo de conectividad Elemica.</span><span class="sxs-lookup"><span data-stu-id="4cc49-129">You can customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="4cc49-130">Puede descargar el módulo de conectividad de [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span><span class="sxs-lookup"><span data-stu-id="4cc49-130">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="4cc49-131">Para obtener más información, vea las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span><span class="sxs-lookup"><span data-stu-id="4cc49-131">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cc49-132">La información en las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc49-132">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc49-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cc49-133">See Also</span></span>  
 <span data-ttu-id="4cc49-134">[Compatibilidad con CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span><span class="sxs-lookup"><span data-stu-id="4cc49-134">[CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span></span>  
 <span data-ttu-id="4cc49-135">[Estándares de mensajería CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="4cc49-135">[CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="4cc49-136">[Normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="4cc49-136">[Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span></span>  
 <span data-ttu-id="4cc49-137">[Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="4cc49-137">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 [<span data-ttu-id="4cc49-138">Importar una PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="4cc49-138">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)