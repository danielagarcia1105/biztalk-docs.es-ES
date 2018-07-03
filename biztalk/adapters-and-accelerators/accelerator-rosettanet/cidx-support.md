---
title: Compatibilidad con CIDX | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, procedures
- CIDX, about CIDX
- CIDX, Elemica Exchange Server Provider (ESP)
- CIDX, PIPs
- CIDX
- Elemica Exchange Server Provider (ESP)
- procedures [CIDX]
- PIPs, CIDX
ms.assetid: 58b75ad3-f6b9-47c0-8dbf-506a3eaf010b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57500dc25e719d7ef693975b74850cbc04289dec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997813"
---
# <a name="cidx-support"></a><span data-ttu-id="faf8c-102">Compatibilidad con CIDX</span><span class="sxs-lookup"><span data-stu-id="faf8c-102">CIDX Support</span></span>
<span data-ttu-id="faf8c-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona compatibilidad para el intercambio de mensajes XML CIDX (intercambio de datos de la industria química).</span><span class="sxs-lookup"><span data-stu-id="faf8c-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides support for CIDX (Chemical Industry Data Exchange) XML message exchange.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="faf8c-104"> es compatible con las normas europeas de química CIDX las versiones 2.0 y 3.0, que utilizan el marco de implementación de RosettaNet (RNIF) 1.1.</span><span class="sxs-lookup"><span data-stu-id="faf8c-104"> supports CIDX Chem eStandards versions 2.0 and 3.0, both of which use the RosettaNet Implementation Framework (RNIF) 1.1.</span></span>  
  
 <span data-ttu-id="faf8c-105">El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] asincrónicos simple los procesos públicos (compatibilidad con mensajes de acción única y de doble acción), consumir y enrutar el contenido del servicio CIDX.</span><span class="sxs-lookup"><span data-stu-id="faf8c-105">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] asynchronous simple public processes (supporting single-action and double-action messages) consume and route CIDX service content.</span></span>  
  
 <span data-ttu-id="faf8c-106">Para un contrato basado en un PIP CIDX, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] validará lo siguiente en un mensaje:</span><span class="sxs-lookup"><span data-stu-id="faf8c-106">For an agreement based on a CIDX PIP, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will validate the following in a message:</span></span>  
  
- <span data-ttu-id="faf8c-107">Solo la versión de RNIF 1.1</span><span class="sxs-lookup"><span data-stu-id="faf8c-107">RNIF 1.1 version only</span></span>  
  
- <span data-ttu-id="faf8c-108">No hay 0A1</span><span class="sxs-lookup"><span data-stu-id="faf8c-108">No 0A1</span></span>  
  
- <span data-ttu-id="faf8c-109">Acción de un solo</span><span class="sxs-lookup"><span data-stu-id="faf8c-109">Only Single Action</span></span>  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="faf8c-110"> no le impedirá configuración la `Standard` propiedad para una configuración de procesos para "CIDX" después de haber establecido el `0A1 agreement` propiedad para un acuerdo que utilizará dicho perfil a "0A1" (que no se admite para CIDX).</span><span class="sxs-lookup"><span data-stu-id="faf8c-110"> will not prevent you from setting the `Standard` property for a process configuration to "CIDX", after you have set the `0A1 agreement` property for an agreement that uses that profile to "0A1" (which is not supported for CIDX).</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="faf8c-111"> no se realiza la validación de campos cruzados que lo impedirían.</span><span class="sxs-lookup"><span data-stu-id="faf8c-111"> does not perform the cross-field validation that would prevent this.</span></span>  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a><span data-ttu-id="faf8c-112">Aplicar un PIP a una implementación de CIDX</span><span class="sxs-lookup"><span data-stu-id="faf8c-112">Applying a PIP to a CIDX Implementation</span></span>  
 <span data-ttu-id="faf8c-113">Para aplicar un PIP a una implementación CIDX, establezca el `Standard` propiedad en el perfil de configuración de proceso a **CIDX**.</span><span class="sxs-lookup"><span data-stu-id="faf8c-113">To apply a PIP to a CIDX implementation, set the `Standard` property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="faf8c-114">Cuando haya terminado, podrá especificar valores para el estándar de mensajes, la versión estándar y el identificador de enlace de carga.</span><span class="sxs-lookup"><span data-stu-id="faf8c-114">After you have finished, you will be able to enter values for the Message standard, Standard version, and Payload binding ID.</span></span> <span data-ttu-id="faf8c-115">Puede encontrar estos valores en la especificación de las normas europeas de química CIDX.</span><span class="sxs-lookup"><span data-stu-id="faf8c-115">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="faf8c-116">Conectarse a la red Elemica</span><span class="sxs-lookup"><span data-stu-id="faf8c-116">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="faf8c-117">Puede permitir que una instalación de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para conectarse a la Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] proveedor (ESP).</span><span class="sxs-lookup"><span data-stu-id="faf8c-117">You can enable an installation of Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to connect to the Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] Provider (ESP).</span></span> <span data-ttu-id="faf8c-118">Puede usar la red Elemica para la industria de sustancias químicas comprar, vender y administración de la cadena de suministro mediante CIDX intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="faf8c-118">You can use the Elemica network for chemical-industry buying, selling, and supply-chain management using CIDX message exchange.</span></span>  
  
 <span data-ttu-id="faf8c-119">Personaliza [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica mediante archivos de proyecto en el módulo de conectividad Elemica.</span><span class="sxs-lookup"><span data-stu-id="faf8c-119">You customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="faf8c-120">Puede descargar el módulo de conectividad del [ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195).</span><span class="sxs-lookup"><span data-stu-id="faf8c-120">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="faf8c-121">Para obtener más información, consulte las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539).</span><span class="sxs-lookup"><span data-stu-id="faf8c-121">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="faf8c-122">La información de las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faf8c-122">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="cidx-procedures"></a><span data-ttu-id="faf8c-123">Procedimientos CIDX</span><span class="sxs-lookup"><span data-stu-id="faf8c-123">CIDX Procedures</span></span>  
 <span data-ttu-id="faf8c-124">Las secciones siguientes describen cómo configurar el intercambio de mensajes CIDX:</span><span class="sxs-lookup"><span data-stu-id="faf8c-124">The following sections described how to set up CIDX message exchange:</span></span>  
  
-   [<span data-ttu-id="faf8c-125">Configuración del intercambio de mensajes de normas europeas de intercambio de datos para CIDX</span><span class="sxs-lookup"><span data-stu-id="faf8c-125">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [<span data-ttu-id="faf8c-126">Creación o edición de un acuerdo</span><span class="sxs-lookup"><span data-stu-id="faf8c-126">Creating or Editing an Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [<span data-ttu-id="faf8c-127">Importación de un PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="faf8c-127">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a><span data-ttu-id="faf8c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="faf8c-128">See Also</span></span>  
 <span data-ttu-id="faf8c-129">[Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="faf8c-129">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="faf8c-130">Estándares de mensajería de CIDX</span><span class="sxs-lookup"><span data-stu-id="faf8c-130">CIDX Messaging Standards</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)