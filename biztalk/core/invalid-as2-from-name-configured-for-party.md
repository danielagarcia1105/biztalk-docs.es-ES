---
title: 'AS2 no válido: nombre configurado para la entidad | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde739bd-f6f7-4e4a-8f02-9a99e9d82fc9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c370476eeccc085783c761cefb41a52eead8e208
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256980"
---
# <a name="invalid-as2-from-name-configured-for-party"></a><span data-ttu-id="eef84-102">Nombre AS2-From no válido configurado para Entidad</span><span class="sxs-lookup"><span data-stu-id="eef84-102">Invalid AS2-From name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="eef84-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eef84-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eef84-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="eef84-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="eef84-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="eef84-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="eef84-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="eef84-106">Event ID</span></span>|-|  
|<span data-ttu-id="eef84-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="eef84-107">Event Source</span></span>|<span data-ttu-id="eef84-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eef84-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="eef84-109">Componente</span><span class="sxs-lookup"><span data-stu-id="eef84-109">Component</span></span>|<span data-ttu-id="eef84-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="eef84-110">AS2 Engine</span></span>|  
|<span data-ttu-id="eef84-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eef84-111">Symbolic Name</span></span>|<span data-ttu-id="eef84-112">InvalidAS2FromNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="eef84-112">InvalidAS2FromNameConfiguredError</span></span>|  
|<span data-ttu-id="eef84-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eef84-113">Message Text</span></span>|<span data-ttu-id="eef84-114">AS2 no válido: nombre configurado para la entidad: {0} valor: {1}</span><span class="sxs-lookup"><span data-stu-id="eef84-114">Invalid AS2-From name configured for Party: {0}   Value: {1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eef84-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="eef84-115">Explanation</span></span>  
 <span data-ttu-id="eef84-116">Este evento de error,  indica que el codificador o descodificador de AS2 no pudo procesar el mensaje AS2 porque el valor del encabezado AS2-From configurado para la entidad identificada no se ajustaba a las especificaciones de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="eef84-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-From header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eef84-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eef84-117">User Action</span></span>  
 <span data-ttu-id="eef84-118">Para resolver este error, asegúrese de que el encabezado AS2-From configurado para la entidad se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130 y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="eef84-118">To resolve this error, make sure that the AS2-From header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>