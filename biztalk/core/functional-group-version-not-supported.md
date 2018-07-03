---
title: Versión de grupo funcional no compatible | Microsoft Docs
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
ms.openlocfilehash: 8ce3ff1cfb525b98e646c31180aa6668d3173cb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997717"
---
# <a name="functional-group-version-not-supported"></a><span data-ttu-id="36e4e-102">Versión de grupo funcional no compatible.</span><span class="sxs-lookup"><span data-stu-id="36e4e-102">Functional Group Version Not Supported</span></span>
## <a name="details"></a><span data-ttu-id="36e4e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="36e4e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="36e4e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="36e4e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="36e4e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="36e4e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="36e4e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="36e4e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="36e4e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="36e4e-107">Event Source</span></span>   | <span data-ttu-id="36e4e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36e4e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="36e4e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="36e4e-109">Component</span></span>    |                                       <span data-ttu-id="36e4e-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="36e4e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="36e4e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="36e4e-111">Symbolic Name</span></span>  |                        <span data-ttu-id="36e4e-112">X12FaGroupVersionNotSupportedDescription</span><span class="sxs-lookup"><span data-stu-id="36e4e-112">X12FaGroupVersionNotSupportedDescription</span></span>                        |
|  <span data-ttu-id="36e4e-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="36e4e-113">Message Text</span></span>   |                         <span data-ttu-id="36e4e-114">Versión de grupo funcional no compatible.</span><span class="sxs-lookup"><span data-stu-id="36e4e-114">Functional Group Version Not Supported</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="36e4e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="36e4e-115">Explanation</span></span>  
 <span data-ttu-id="36e4e-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque BizTalk Server no admite el número de versión en el segmento GS08 de un grupo funcional.</span><span class="sxs-lookup"><span data-stu-id="36e4e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because BizTalk Server does not support the version number in segment GS08 of a functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36e4e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="36e4e-117">User Action</span></span>  
 <span data-ttu-id="36e4e-118">Para resolver este error, asegúrese de que los números de versión de cada instancia del segmento GS08 en todos los grupos funcionales del intercambio son compatibles con BizTalk Server y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="36e4e-118">To resolve this error, ensure that the version numbers in each instance of segment GS08 in all functional groups in the interchange are supported by BizTalk Server, and then have the interchange resent.</span></span> <span data-ttu-id="36e4e-119">Tenga en cuenta que las versiones estándar que admite BizTalk Server aparecen en el tema "Compatibilidad con el esquema de documento EDI" de la Ayuda del producto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36e4e-119">Note that the standard versions that BizTalk Server supports are listed in the "EDI Document Schema Support" topic of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product help.</span></span>