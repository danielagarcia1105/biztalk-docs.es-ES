---
title: El certificado de firma no se ha configurado para la entidad AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61802b5e86319d0fe73f11c22249b72af1441b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279652"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a><span data-ttu-id="b23d7-102">El certificado de firma no se ha configurado para la entidad AS2</span><span class="sxs-lookup"><span data-stu-id="b23d7-102">The Signing Certificate has not been configured for AS2 party</span></span>
## <a name="details"></a><span data-ttu-id="b23d7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b23d7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b23d7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b23d7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b23d7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b23d7-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b23d7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b23d7-106">Event ID</span></span>|-|  
|<span data-ttu-id="b23d7-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b23d7-107">Event Source</span></span>|<span data-ttu-id="b23d7-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b23d7-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="b23d7-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b23d7-109">Component</span></span>|<span data-ttu-id="b23d7-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="b23d7-110">AS2 Engine</span></span>|  
|<span data-ttu-id="b23d7-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b23d7-111">Symbolic Name</span></span>|<span data-ttu-id="b23d7-112">SigningCertNotConfiguredError</span><span class="sxs-lookup"><span data-stu-id="b23d7-112">SigningCertNotConfiguredError</span></span>|  
|<span data-ttu-id="b23d7-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b23d7-113">Message Text</span></span>|<span data-ttu-id="b23d7-114">El certificado de firma no se ha configurado para la entidad AS2.</span><span class="sxs-lookup"><span data-stu-id="b23d7-114">The Signing Certificate has not been configured for AS2 party.</span></span>  <span data-ttu-id="b23d7-115">AS2-de: {0} AS2-a: {1}</span><span class="sxs-lookup"><span data-stu-id="b23d7-115">AS2-From: {0} AS2-To: {1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b23d7-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b23d7-116">Explanation</span></span>  
 <span data-ttu-id="b23d7-117">Este evento de error,  indica que la canalización de envío no pudo procesar el mensaje saliente porque el certificado de firma no se ha configurado para el grupo.</span><span class="sxs-lookup"><span data-stu-id="b23d7-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the signing certificate was not configured for the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b23d7-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b23d7-118">User Action</span></span>  
 <span data-ttu-id="b23d7-119">Para resolver este error, realice el procedimiento siguiente para configurar el certificado de firma:</span><span class="sxs-lookup"><span data-stu-id="b23d7-119">To resolve this error, configure signing certificate by doing the following:</span></span>  
  
1.  <span data-ttu-id="b23d7-120">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b23d7-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="b23d7-121">Vaya al nodo Grupo y haga clic en el nodo Certificado.</span><span class="sxs-lookup"><span data-stu-id="b23d7-121">Move to the Group node, and click the Certificate node.</span></span>  
  
3.  <span data-ttu-id="b23d7-122">Especifique el nombre común y la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="b23d7-122">Enter the common name and thumbprint of the certificate.</span></span>