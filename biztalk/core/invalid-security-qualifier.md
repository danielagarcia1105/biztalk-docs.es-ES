---
title: Calificador de seguridad no válido. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dce36f4b-ab59-41c0-8b92-3020f6393db9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8b0bd8b96d493641f58e445c4b45bd9f5df63e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986941"
---
# <a name="invalid-security-qualifier"></a><span data-ttu-id="870f0-102">Calificador de seguridad no válido.</span><span class="sxs-lookup"><span data-stu-id="870f0-102">Invalid Security Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="870f0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="870f0-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="870f0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="870f0-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="870f0-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="870f0-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="870f0-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="870f0-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="870f0-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="870f0-107">Event Source</span></span>   | <span data-ttu-id="870f0-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="870f0-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="870f0-109">Componente</span><span class="sxs-lookup"><span data-stu-id="870f0-109">Component</span></span>    |                                       <span data-ttu-id="870f0-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="870f0-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="870f0-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="870f0-111">Symbolic Name</span></span>  |                       <span data-ttu-id="870f0-112">X12Ta1InvalidSecurityQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="870f0-112">X12Ta1InvalidSecurityQualifierDescription</span></span>                        |
|  <span data-ttu-id="870f0-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="870f0-113">Message Text</span></span>   |                               <span data-ttu-id="870f0-114">Calificador de seguridad no válido.</span><span class="sxs-lookup"><span data-stu-id="870f0-114">Invalid Security Qualifier</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="870f0-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="870f0-115">Explanation</span></span>  
 <span data-ttu-id="870f0-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el calificador de seguridad en el campo ISA03 o el calificador de la contraseña de referencia de destinatario en el campo UNB6.2 no coincidían con un valor en la enumeración que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="870f0-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Security Qualifier in the ISA03 field or the Recipient Reference Password Qualifier in the UNB6.2 field did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="870f0-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="870f0-117">User Action</span></span>  
 <span data-ttu-id="870f0-118">Para resolver este error, asegúrese de que el campo ISA03 o el campo UNB6.2 coincide con uno de los valores de la enumeración que establece el esquema de servicio.</span><span class="sxs-lookup"><span data-stu-id="870f0-118">To resolve this error, make sure that the ISA03 field or the UNB6.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="870f0-119">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="870f0-119">Have the interchange resent.</span></span>