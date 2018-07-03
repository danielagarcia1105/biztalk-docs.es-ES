---
title: El certificado de firma no se configuró para la entidad AS2 | Microsoft Docs
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
ms.openlocfilehash: 4d26323670f0229377b304e5f51671de8ef10021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967549"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a><span data-ttu-id="74620-102">El certificado de firma no se ha configurado para la entidad AS2</span><span class="sxs-lookup"><span data-stu-id="74620-102">The Signing Certificate has not been configured for AS2 party</span></span>
## <a name="details"></a><span data-ttu-id="74620-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="74620-103">Details</span></span>  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="74620-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="74620-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| <span data-ttu-id="74620-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="74620-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    <span data-ttu-id="74620-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="74620-106">Event ID</span></span>     |                                             -                                             |
|  <span data-ttu-id="74620-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="74620-107">Event Source</span></span>   |  <span data-ttu-id="74620-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74620-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>   |
|    <span data-ttu-id="74620-109">Componente</span><span class="sxs-lookup"><span data-stu-id="74620-109">Component</span></span>    |                                        <span data-ttu-id="74620-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="74620-110">AS2 Engine</span></span>                                         |
|  <span data-ttu-id="74620-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="74620-111">Symbolic Name</span></span>  |                               <span data-ttu-id="74620-112">SigningCertNotConfiguredError</span><span class="sxs-lookup"><span data-stu-id="74620-112">SigningCertNotConfiguredError</span></span>                               |
|  <span data-ttu-id="74620-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="74620-113">Message Text</span></span>   | <span data-ttu-id="74620-114">El certificado de firma no se ha configurado para la entidad AS2.</span><span class="sxs-lookup"><span data-stu-id="74620-114">The Signing Certificate has not been configured for AS2 party.</span></span>  <span data-ttu-id="74620-115">AS2-de: {0} AS2-para: {1}</span><span class="sxs-lookup"><span data-stu-id="74620-115">AS2-From: {0} AS2-To: {1}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="74620-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="74620-116">Explanation</span></span>  
 <span data-ttu-id="74620-117">Este evento de error,  indica que la canalización de envío no pudo procesar el mensaje saliente porque el certificado de firma no se ha configurado para el grupo.</span><span class="sxs-lookup"><span data-stu-id="74620-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the signing certificate was not configured for the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74620-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="74620-118">User Action</span></span>  
 <span data-ttu-id="74620-119">Para resolver este error, realice el procedimiento siguiente para configurar el certificado de firma:</span><span class="sxs-lookup"><span data-stu-id="74620-119">To resolve this error, configure signing certificate by doing the following:</span></span>  
  
1.  <span data-ttu-id="74620-120">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="74620-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="74620-121">Vaya al nodo Grupo y haga clic en el nodo Certificado.</span><span class="sxs-lookup"><span data-stu-id="74620-121">Move to the Group node, and click the Certificate node.</span></span>  
  
3.  <span data-ttu-id="74620-122">Especifique el nombre común y la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="74620-122">Enter the common name and thumbprint of the certificate.</span></span>