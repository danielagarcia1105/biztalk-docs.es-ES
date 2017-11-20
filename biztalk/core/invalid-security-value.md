---
title: "Valor de seguridad no válido. | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee380da7-c05e-4b9b-84ee-f7ffee90eb0e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e41315400ee2b0eae099439237356b61676b26cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-security-value"></a><span data-ttu-id="ddbd2-102">Valor de seguridad no válido.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-102">Invalid Security Value</span></span>
## <a name="details"></a><span data-ttu-id="ddbd2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ddbd2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddbd2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ddbd2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ddbd2-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ddbd2-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ddbd2-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ddbd2-106">Event ID</span></span>|-|  
|<span data-ttu-id="ddbd2-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ddbd2-107">Event Source</span></span>|<span data-ttu-id="ddbd2-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddbd2-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="ddbd2-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ddbd2-109">Component</span></span>|<span data-ttu-id="ddbd2-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ddbd2-110">EDI Engine</span></span>|  
|<span data-ttu-id="ddbd2-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ddbd2-111">Symbolic Name</span></span>|<span data-ttu-id="ddbd2-112">X12Ta1InvalidSecurityValueDescription</span><span class="sxs-lookup"><span data-stu-id="ddbd2-112">X12Ta1InvalidSecurityValueDescription</span></span>|  
|<span data-ttu-id="ddbd2-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ddbd2-113">Message Text</span></span>|<span data-ttu-id="ddbd2-114">Valor de seguridad no válido.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-114">Invalid Security Value</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ddbd2-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="ddbd2-115">Explanation</span></span>  
 <span data-ttu-id="ddbd2-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque la información de seguridad en el campo ISA04 o el valor de contraseña de referencia de destinatario en el campo UNB6.1 no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).</span><span class="sxs-lookup"><span data-stu-id="ddbd2-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Security Information in the ISA04 field or the Recipient Reference Password Value in the UNB6.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddbd2-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ddbd2-117">User Action</span></span>  
 <span data-ttu-id="ddbd2-118">Para resolver este error, asegúrese de que el campo ISA04 es del tipo de datos X12_AN y es de 10 caracteres (con o sin espacios finales) o que el campo UNB6.1 es del tipo de datos EDIFACT_AN y tenga entre 1 y 14 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-118">To resolve this error, make sure that the ISA04 field is of the X12_AN data type and is 10 characters long (with or without trailing spaces) or that the UNB6.1 field is of the EDIFACT_AN data type and is between 1 and 14 characters long.</span></span> <span data-ttu-id="ddbd2-119">Vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="ddbd2-119">Have the interchange resent.</span></span>