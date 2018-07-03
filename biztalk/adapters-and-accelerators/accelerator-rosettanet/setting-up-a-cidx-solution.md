---
title: Configuración de una solución CIDX | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770691b2862aba307e6f1cc444c8d38adce4aeb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984293"
---
# <a name="setting-up-a-cidx-solution"></a><span data-ttu-id="cda78-102">Configuración de una solución CIDX</span><span class="sxs-lookup"><span data-stu-id="cda78-102">Setting Up a CIDX Solution</span></span>
<span data-ttu-id="cda78-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] compatibilidad con intercambio de mensajes XML CIDX (intercambio de datos de la industria química) (normas europeas de química CIDX las versiones 2.0 y 3.0).</span><span class="sxs-lookup"><span data-stu-id="cda78-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] support for CIDX (Chemical Industry Data Exchange) XML message exchange (CIDX Chem eStandards versions 2.0 and 3.0).</span></span> <span data-ttu-id="cda78-104">Este tema describe cómo configurar una solución CIDX haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cda78-104">This topic describes how to set up a CIDX solution by doing the following:</span></span>  
  
-   <span data-ttu-id="cda78-105">Configuración de una configuración de procesos</span><span class="sxs-lookup"><span data-stu-id="cda78-105">Setting up a process configuration</span></span>  
  
-   <span data-ttu-id="cda78-106">Configuración de un acuerdo</span><span class="sxs-lookup"><span data-stu-id="cda78-106">Setting up an agreement</span></span>  
  
-   <span data-ttu-id="cda78-107">Aplicar un PIP</span><span class="sxs-lookup"><span data-stu-id="cda78-107">Applying a PIP</span></span>  
  
-   <span data-ttu-id="cda78-108">Importar un PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="cda78-108">Importing an XSD-based PIP</span></span>  
  
-   <span data-ttu-id="cda78-109">Conectarse a la red Elemica</span><span class="sxs-lookup"><span data-stu-id="cda78-109">Connecting to the Elemica Network</span></span>  
  
## <a name="setting-up-a-cidx-process-configuration"></a><span data-ttu-id="cda78-110">Una configuración de proceso CIDX</span><span class="sxs-lookup"><span data-stu-id="cda78-110">Setting Up a CIDX Process Configuration</span></span>  
 <span data-ttu-id="cda78-111">Para configurar un intercambio de mensajes de las normas europeas CIDX, deberá crear una configuración de proceso que tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="cda78-111">To set up a CIDX eStandards message exchange, you need to create a process configuration that has the following properties:</span></span>  
  
- <span data-ttu-id="cda78-112">**Estándar** propiedad en las opciones de configuración de proceso establecido en **CIDX**</span><span class="sxs-lookup"><span data-stu-id="cda78-112">**Standard** property in the process configuration settings set to **CIDX**</span></span>  
  
- <span data-ttu-id="cda78-113">**Es la única acción** propiedad en las opciones de configuración de proceso establecido en **True**</span><span class="sxs-lookup"><span data-stu-id="cda78-113">**Is Single Action** property in the process configuration settings set to **True**</span></span>  
  
- <span data-ttu-id="cda78-114">**Acuerdo de 0A1** propiedad en el acuerdo entre socios comerciales que se establece en **ningún 0A1**</span><span class="sxs-lookup"><span data-stu-id="cda78-114">**0A1 agreement** property in the trading partner agreement set to **No 0A1**</span></span>  
  
  <span data-ttu-id="cda78-115">Para obtener más información, consulte [configuración CIDX las normas europeas de intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span><span class="sxs-lookup"><span data-stu-id="cda78-115">For more information, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
## <a name="creating-a-cidx-agreement"></a><span data-ttu-id="cda78-116">Creación de un acuerdo CIDX</span><span class="sxs-lookup"><span data-stu-id="cda78-116">Creating a CIDX Agreement</span></span>  
 <span data-ttu-id="cda78-117">Para configurar un intercambio de mensajes de las normas europeas CIDX, deberá crear un acuerdo que tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="cda78-117">To set up a CIDX eStandards message exchange, you need to create an agreement that has the following properties:</span></span>  
  
- <span data-ttu-id="cda78-118">**Versión de RNIF** propiedad en la configuración del contrato establecido en **V01.10.00**</span><span class="sxs-lookup"><span data-stu-id="cda78-118">**RNIF Version** property in the agreement settings set to **V01.10.00**</span></span>  
  
- <span data-ttu-id="cda78-119">**Acuerdo de 0A1** propiedad en la configuración del contrato establecido en **No 0A1**</span><span class="sxs-lookup"><span data-stu-id="cda78-119">**0A1 agreement** property in the agreement settings set to **No 0A1**</span></span>  
  
  <span data-ttu-id="cda78-120">Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span><span class="sxs-lookup"><span data-stu-id="cda78-120">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
## <a name="applying-a-pip-for-cidx"></a><span data-ttu-id="cda78-121">Aplicar un PIP para CIDX</span><span class="sxs-lookup"><span data-stu-id="cda78-121">Applying a PIP for CIDX</span></span>  
 <span data-ttu-id="cda78-122">Para aplicar un PIP a una implementación CIDX, establezca el **estándar** propiedad en el perfil de configuración de proceso a **CIDX**.</span><span class="sxs-lookup"><span data-stu-id="cda78-122">To apply a PIP to a CIDX implementation, set the **Standard** property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="cda78-123">Cuando haya terminado, podrá especificar valores para el **estándar de mensajes**, **versión estándar**, y **Id. de enlace de carga**.</span><span class="sxs-lookup"><span data-stu-id="cda78-123">After you have finished, you will be able to enter values for the **Message standard**, **Standard version**, and **Payload binding ID**.</span></span> <span data-ttu-id="cda78-124">Puede encontrar estos valores en la especificación de las normas europeas de química CIDX.</span><span class="sxs-lookup"><span data-stu-id="cda78-124">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a><span data-ttu-id="cda78-125">Importar un PIP basado en XSD para CIDX</span><span class="sxs-lookup"><span data-stu-id="cda78-125">Importing an XSD-based PIP for CIDX</span></span>  
 <span data-ttu-id="cda78-126">Para importar un PIP basado en XSD para CIDX, deberá descargar el archivo ZIP del PIP de CIDX.org en [ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=62361).</span><span class="sxs-lookup"><span data-stu-id="cda78-126">To import an XSD-based PIP for CIDX, you need to download the PIP's ZIP file from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="cda78-127">Siga el procedimiento de importación se describe en [importar un PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).</span><span class="sxs-lookup"><span data-stu-id="cda78-127">Follow the import procedure described in [Importing an XSD-based PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="cda78-128">Conectarse a la red Elemica</span><span class="sxs-lookup"><span data-stu-id="cda78-128">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="cda78-129">Puede personalizar [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica mediante archivos de proyecto en el módulo de conectividad Elemica.</span><span class="sxs-lookup"><span data-stu-id="cda78-129">You can customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="cda78-130">Puede descargar el módulo de conectividad del [ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195).</span><span class="sxs-lookup"><span data-stu-id="cda78-130">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="cda78-131">Para obtener más información, consulte las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539).</span><span class="sxs-lookup"><span data-stu-id="cda78-131">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cda78-132">La información de las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cda78-132">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda78-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="cda78-133">See Also</span></span>  
 <span data-ttu-id="cda78-134">[Compatibilidad con CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span><span class="sxs-lookup"><span data-stu-id="cda78-134">[CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span></span>  
 <span data-ttu-id="cda78-135">[Estándares de mensajería de CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="cda78-135">[CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="cda78-136">[Configuración CIDX las normas europeas de intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="cda78-136">[Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span></span>  
 <span data-ttu-id="cda78-137">[Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="cda78-137">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 [<span data-ttu-id="cda78-138">Importación de un PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="cda78-138">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)