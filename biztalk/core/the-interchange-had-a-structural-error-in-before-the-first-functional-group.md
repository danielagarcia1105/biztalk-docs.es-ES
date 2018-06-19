---
title: El intercambio contenía un error estructural-antes del primer grupo funcional | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12202148-0a32-464e-8dbd-d01b9ba530eb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ab490de214f53e85ea32c1b243456f837c72e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278660"
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a><span data-ttu-id="38251-102">El intercambio contenía un error estructural-antes del primer grupo funcional</span><span class="sxs-lookup"><span data-stu-id="38251-102">The interchange had a structural error in-before the first functional group</span></span>
## <a name="details"></a><span data-ttu-id="38251-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="38251-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38251-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="38251-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="38251-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="38251-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="38251-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="38251-106">Event ID</span></span>|-|  
|<span data-ttu-id="38251-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="38251-107">Event Source</span></span>|<span data-ttu-id="38251-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38251-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="38251-109">Componente</span><span class="sxs-lookup"><span data-stu-id="38251-109">Component</span></span>|<span data-ttu-id="38251-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="38251-110">EDI Engine</span></span>|  
|<span data-ttu-id="38251-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="38251-111">Symbolic Name</span></span>|<span data-ttu-id="38251-112">X12InterchangeStructuralErrorBefore1stGroup</span><span class="sxs-lookup"><span data-stu-id="38251-112">X12InterchangeStructuralErrorBefore1stGroup</span></span>|  
|<span data-ttu-id="38251-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="38251-113">Message Text</span></span>|<span data-ttu-id="38251-114">El intercambio con el identificador '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural en o antes del primer grupo funcional</span><span class="sxs-lookup"><span data-stu-id="38251-114">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error in/before the first functional group</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="38251-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="38251-115">Explanation</span></span>  
 <span data-ttu-id="38251-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante por una de las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="38251-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, for one of the following reasons:</span></span>  
  
-   <span data-ttu-id="38251-117">Se produjo un error estructural en los segmentos ISA o IEA o en el primer grupo funcional del intercambio, de modo que el intercambio no se ajustaba al esquema aplicable.</span><span class="sxs-lookup"><span data-stu-id="38251-117">A structural error occurred in either the ISA and IEA segments or the first functional group of the interchange, so the interchange did not conform to the applicable schema.</span></span>  
  
-   <span data-ttu-id="38251-118">No se ha implementado X12ServiceSchema (en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="38251-118">The X12ServiceSchema (in BaseArtifacts.dll) was not deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="38251-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="38251-119">User Action</span></span>  
 <span data-ttu-id="38251-120">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="38251-120">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="38251-121">Pida al remitente del intercambio que cambie los segmentos ISA o IEA, o el primer grupo funcional de modo que se ajuste al esquema aplicable y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="38251-121">Have the sender of the interchange change the ISA and/or IEA segments or the first functional group so that it conforms to the applicable schema, and then resend the interchange.</span></span>  
  
-   <span data-ttu-id="38251-122">Asegúrese de que BaseArtifacts.dll incluye X12ServiceSchema y está implementado.</span><span class="sxs-lookup"><span data-stu-id="38251-122">Ensure that BaseArtifacts.dll includes the X12ServiceSchema and is deployed.</span></span> <span data-ttu-id="38251-123">Para ello, abra la consola de administración de BizTalk Server, abra el nodo aplicación EDI de BizTalk y el nodo de esquemas y compruebe que X12ServiceSchema aparece.</span><span class="sxs-lookup"><span data-stu-id="38251-123">You can do so by opening the BizTalk Server Administration Console, opening the BizTalk EDI Application node and the Schemas node, and verifying that X12ServiceSchema is listed.</span></span>