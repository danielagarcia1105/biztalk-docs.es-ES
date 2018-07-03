---
title: Configurar propiedades de canalización de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.AS2.pipeline.properties
ms.assetid: 7faf6b05-710a-4d00-8c77-590ce9d9f962
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2bb679e4e150382cd8ff3e80c838d269ba908f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988877"
---
# <a name="configuring-as2-pipeline-properties"></a><span data-ttu-id="a1a0f-102">Configurar propiedades de canalización de AS2</span><span class="sxs-lookup"><span data-stu-id="a1a0f-102">Configuring AS2 Pipeline Properties</span></span>
<span data-ttu-id="a1a0f-103">Las propiedades de canalización se usan en el proceso de mensajes AS2 entrantes y salientes cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha podido determinar el acuerdo que resuelve el intercambio de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-103">Pipeline properties are used in processing an incoming or outgoing AS2 message when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not been able to determine the agreement that resolves to the sent or received interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1a0f-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a1a0f-104">Prerequisites</span></span>  
 <span data-ttu-id="a1a0f-105">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1a0f-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="as2-pipeline-properties"></a><span data-ttu-id="a1a0f-106">Propiedades de canalización AS2</span><span class="sxs-lookup"><span data-stu-id="a1a0f-106">AS2 Pipeline Properties</span></span>  
 <span data-ttu-id="a1a0f-107">Se puede establecer la siguiente propiedad en las canalizaciones AS2:</span><span class="sxs-lookup"><span data-stu-id="a1a0f-107">The following property can be set in AS2 pipelines:</span></span>  
  
|<span data-ttu-id="a1a0f-108">Property</span><span class="sxs-lookup"><span data-stu-id="a1a0f-108">Property</span></span>|<span data-ttu-id="a1a0f-109">Utilice</span><span class="sxs-lookup"><span data-stu-id="a1a0f-109">Use</span></span>|<span data-ttu-id="a1a0f-110">Valores</span><span class="sxs-lookup"><span data-stu-id="a1a0f-110">Values</span></span>|<span data-ttu-id="a1a0f-111">Canalización/Fase</span><span class="sxs-lookup"><span data-stu-id="a1a0f-111">Pipeline/Stage</span></span>|  
|--------------|---------|------------|---------------------|  
|<span data-ttu-id="a1a0f-112">ContentTransferEncoding</span><span class="sxs-lookup"><span data-stu-id="a1a0f-112">ContentTransferEncoding</span></span>|<span data-ttu-id="a1a0f-113">Indica el método que se usará para representar los datos binarios en formato de texto ASCII.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-113">Indicates which method will be used for representing binary data in ASCII text format.</span></span>|<span data-ttu-id="a1a0f-114">8 bits (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="a1a0f-114">8bit (default)</span></span><br /><br /> <span data-ttu-id="a1a0f-115">7 bits</span><span class="sxs-lookup"><span data-stu-id="a1a0f-115">7bit</span></span><br /><br /> <span data-ttu-id="a1a0f-116">8 bits</span><span class="sxs-lookup"><span data-stu-id="a1a0f-116">8bit</span></span>|<span data-ttu-id="a1a0f-117">AS2EdiSend/Encode</span><span class="sxs-lookup"><span data-stu-id="a1a0f-117">AS2EdiSend/Encode</span></span><br /><br /> <span data-ttu-id="a1a0f-118">AS2Send/Encode</span><span class="sxs-lookup"><span data-stu-id="a1a0f-118">AS2Send/Encode</span></span>|  
  
### <a name="to-set-a-pipeline-property"></a><span data-ttu-id="a1a0f-119">Para establecer una propiedad de canalización</span><span class="sxs-lookup"><span data-stu-id="a1a0f-119">To set a pipeline property</span></span>  
  
1. <span data-ttu-id="a1a0f-120">En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], haga clic con el botón secundario en la ubicación de recepción o puerto de envío mediante la canalización para la que desee establecer las propiedades.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="a1a0f-121">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-121">Click **Properties**.</span></span>  
  
2. <span data-ttu-id="a1a0f-122">Haga clic en el botón de elipsis (…) junto a la canalización para la que desee establecer las propiedades.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-122">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
3. <span data-ttu-id="a1a0f-123">Escriba el valor de la propiedad y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1a0f-123">Enter the value for the property, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a0f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1a0f-124">See Also</span></span>  
 [<span data-ttu-id="a1a0f-125">Desarrollo y configuración de soluciones AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a1a0f-125">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)