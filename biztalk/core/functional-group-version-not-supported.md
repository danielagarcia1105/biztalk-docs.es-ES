---
title: Versión de grupo funcional no compatible | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715e6585-a07a-4060-a15b-0c9603fbef19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b92b7844c750d9a709ac2376bb8f126a32119f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246452"
---
# <a name="functional-group-version-not-supported"></a><span data-ttu-id="e58b6-102">Versión de grupo funcional no compatible.</span><span class="sxs-lookup"><span data-stu-id="e58b6-102">Functional Group Version Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="e58b6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e58b6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e58b6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e58b6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e58b6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e58b6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e58b6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e58b6-106">Event ID</span></span>|-|  
|<span data-ttu-id="e58b6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e58b6-107">Event Source</span></span>|<span data-ttu-id="e58b6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e58b6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="e58b6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e58b6-109">Component</span></span>|<span data-ttu-id="e58b6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e58b6-110">EDI Engine</span></span>|  
|<span data-ttu-id="e58b6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e58b6-111">Symbolic Name</span></span>|<span data-ttu-id="e58b6-112">X12FaGroupVersionNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="e58b6-112">X12FaGroupVersionNotSupportedDescription</span></span>|  
|<span data-ttu-id="e58b6-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e58b6-113">Message Text</span></span>|<span data-ttu-id="e58b6-114">Versión de grupo funcional no compatible.</span><span class="sxs-lookup"><span data-stu-id="e58b6-114">Functional Group Version Not Supported</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e58b6-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e58b6-115">Explanation</span></span>  
 <span data-ttu-id="e58b6-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque BizTalk Server no admite el número de versión en el segmento GS08 de un grupo funcional.</span><span class="sxs-lookup"><span data-stu-id="e58b6-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because BizTalk Server does not support the version number in segment GS08 of a functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e58b6-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e58b6-117">User Action</span></span>  
 <span data-ttu-id="e58b6-118">Para resolver este error, asegúrese de que los números de versión de cada instancia del segmento GS08 en todos los grupos funcionales del intercambio son compatibles con BizTalk Server y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e58b6-118">To resolve this error, ensure that the version numbers in each instance of segment GS08 in all functional groups in the interchange are supported by BizTalk Server, and then have the interchange resent.</span></span> <span data-ttu-id="e58b6-119">Tenga en cuenta que las versiones estándar que admite BizTalk Server aparecen en el tema "Compatibilidad con el esquema de documento EDI" de la Ayuda del producto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e58b6-119">Note that the standard versions that BizTalk Server supports are listed in the "EDI Document Schema Support" topic of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product help.</span></span>