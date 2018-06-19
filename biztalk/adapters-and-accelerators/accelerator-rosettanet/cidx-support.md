---
title: Compatibilidad con CIDX | Documentos de Microsoft
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
ms.openlocfilehash: 224d2b50d132efa67e1cfc24dda2df77fa7d29e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210700"
---
# <a name="cidx-support"></a><span data-ttu-id="46dff-102">Compatibilidad con CIDX</span><span class="sxs-lookup"><span data-stu-id="46dff-102">CIDX Support</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="46dff-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona compatibilidad para el intercambio de mensajes XML CIDX (intercambio de datos de la industria química).</span><span class="sxs-lookup"><span data-stu-id="46dff-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides support for CIDX (Chemical Industry Data Exchange) XML message exchange.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="46dff-104">es compatible con normas europeas de química CIDX las versiones 2.0 y 3.0, ambos de los cuales utilizan RosettaNet Implementation Framework (RNIF) 1.1.</span><span class="sxs-lookup"><span data-stu-id="46dff-104"> supports CIDX Chem eStandards versions 2.0 and 3.0, both of which use the RosettaNet Implementation Framework (RNIF) 1.1.</span></span>  
  
 <span data-ttu-id="46dff-105">El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesos públicos simples asincrónicos (compatibilidad con mensajes de acción única y doble acción) utilizar y distribuir contenido de servicio CIDX.</span><span class="sxs-lookup"><span data-stu-id="46dff-105">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] asynchronous simple public processes (supporting single-action and double-action messages) consume and route CIDX service content.</span></span>  
  
 <span data-ttu-id="46dff-106">Para un acuerdo según un PIP CIDX, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] validará lo siguiente en un mensaje:</span><span class="sxs-lookup"><span data-stu-id="46dff-106">For an agreement based on a CIDX PIP, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will validate the following in a message:</span></span>  
  
-   <span data-ttu-id="46dff-107">Solo la versión de RNIF 1.1</span><span class="sxs-lookup"><span data-stu-id="46dff-107">RNIF 1.1 version only</span></span>  
  
-   <span data-ttu-id="46dff-108">No hay 0A1</span><span class="sxs-lookup"><span data-stu-id="46dff-108">No 0A1</span></span>  
  
-   <span data-ttu-id="46dff-109">Solo acción única</span><span class="sxs-lookup"><span data-stu-id="46dff-109">Only Single Action</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="46dff-110">no podrá configuración el `Standard` propiedad para una configuración del proceso en "CIDX", después de haber establecido el `0A1 agreement` propiedad para un acuerdo que utilizará dicho perfil a "0A1" (que no se admite para CIDX).</span><span class="sxs-lookup"><span data-stu-id="46dff-110"> will not prevent you from setting the `Standard` property for a process configuration to "CIDX", after you have set the `0A1 agreement` property for an agreement that uses that profile to "0A1" (which is not supported for CIDX).</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="46dff-111">no lleva a cabo la validación de campos cruzados que impedirían que esto.</span><span class="sxs-lookup"><span data-stu-id="46dff-111"> does not perform the cross-field validation that would prevent this.</span></span>  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a><span data-ttu-id="46dff-112">Aplicar un PIP a una implementación CIDX</span><span class="sxs-lookup"><span data-stu-id="46dff-112">Applying a PIP to a CIDX Implementation</span></span>  
 <span data-ttu-id="46dff-113">Para aplicar un PIP a una implementación CIDX, establezca el `Standard` propiedad en el perfil de configuración de proceso a **CIDX**.</span><span class="sxs-lookup"><span data-stu-id="46dff-113">To apply a PIP to a CIDX implementation, set the `Standard` property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="46dff-114">Cuando haya terminado, podrá especificar valores para el estándar de mensajes, la versión estándar y el identificador de enlace de carga.</span><span class="sxs-lookup"><span data-stu-id="46dff-114">After you have finished, you will be able to enter values for the Message standard, Standard version, and Payload binding ID.</span></span> <span data-ttu-id="46dff-115">Puede encontrar estos valores en la especificación de normas europeas de química CIDX.</span><span class="sxs-lookup"><span data-stu-id="46dff-115">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="46dff-116">Conectarse a la red Elemica</span><span class="sxs-lookup"><span data-stu-id="46dff-116">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="46dff-117">Puede habilitar una instalación de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para conectarse a la Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] proveedor (ESP).</span><span class="sxs-lookup"><span data-stu-id="46dff-117">You can enable an installation of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to connect to the Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] Provider (ESP).</span></span> <span data-ttu-id="46dff-118">Puede usar la red Elemica para la industria química compra, venta y administración de la cadena de suministro mediante CIDX intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="46dff-118">You can use the Elemica network for chemical-industry buying, selling, and supply-chain management using CIDX message exchange.</span></span>  
  
 <span data-ttu-id="46dff-119">Personalizar [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica con archivos de proyecto en el módulo de conectividad Elemica.</span><span class="sxs-lookup"><span data-stu-id="46dff-119">You customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="46dff-120">Puede descargar el módulo de conectividad de [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span><span class="sxs-lookup"><span data-stu-id="46dff-120">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="46dff-121">Para obtener más información, vea las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span><span class="sxs-lookup"><span data-stu-id="46dff-121">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46dff-122">La información en las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dff-122">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="cidx-procedures"></a><span data-ttu-id="46dff-123">Procedimientos CIDX</span><span class="sxs-lookup"><span data-stu-id="46dff-123">CIDX Procedures</span></span>  
 <span data-ttu-id="46dff-124">En las siguientes secciones se describen cómo configurar el intercambio de mensajes CIDX:</span><span class="sxs-lookup"><span data-stu-id="46dff-124">The following sections described how to set up CIDX message exchange:</span></span>  
  
-   [<span data-ttu-id="46dff-125">Normas europeas de configuración seguridad CIDX intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="46dff-125">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [<span data-ttu-id="46dff-126">Crear o editar un acuerdo</span><span class="sxs-lookup"><span data-stu-id="46dff-126">Creating or Editing an Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [<span data-ttu-id="46dff-127">Importar una PIP basado en XSD</span><span class="sxs-lookup"><span data-stu-id="46dff-127">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a><span data-ttu-id="46dff-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="46dff-128">See Also</span></span>  
 <span data-ttu-id="46dff-129">[Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="46dff-129">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="46dff-130">Estándares de mensajería CIDX</span><span class="sxs-lookup"><span data-stu-id="46dff-130">CIDX Messaging Standards</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)