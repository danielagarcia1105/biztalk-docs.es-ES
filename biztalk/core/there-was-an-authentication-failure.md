---
title: Se produjo un error de autenticación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36524da9-da91-41e7-bf73-7781cde20c80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180645d30c5cccc64eacd57730539bbca220f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278692"
---
# <a name="there-was-an-authentication-failure"></a><span data-ttu-id="2a763-102">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="2a763-102">There was an authentication failure</span></span>
## <a name="details"></a><span data-ttu-id="2a763-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2a763-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a763-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2a763-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2a763-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2a763-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2a763-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2a763-106">Event ID</span></span>|-|  
|<span data-ttu-id="2a763-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2a763-107">Event Source</span></span>|<span data-ttu-id="2a763-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a763-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="2a763-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2a763-109">Component</span></span>|<span data-ttu-id="2a763-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2a763-110">EDI Engine</span></span>|  
|<span data-ttu-id="2a763-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2a763-111">Symbolic Name</span></span>|<span data-ttu-id="2a763-112">DescPartyNotFound</span><span class="sxs-lookup"><span data-stu-id="2a763-112">DescPartyNotFound</span></span>|  
|<span data-ttu-id="2a763-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2a763-113">Message Text</span></span>|<span data-ttu-id="2a763-114">Se produjo un error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="2a763-114">There was an authentication failure.</span></span> <span data-ttu-id="2a763-115">Asegúrese de que existe una entidad que coincida con el mensaje que se está procesando,</span><span class="sxs-lookup"><span data-stu-id="2a763-115">Make sure that a matching party exists for the message being processed.</span></span> <span data-ttu-id="2a763-116">y que la información de seguridad y contraseña del mensaje coincide con la configuración de la entidad.</span><span class="sxs-lookup"><span data-stu-id="2a763-116">And the security/password information in the message matches the Party configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2a763-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="2a763-117">Explanation</span></span>  
 <span data-ttu-id="2a763-118">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque BizTalk Server no pudo autenticar al remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2a763-118">This Error/Warning/Information event indicates that the receive pipeline was unable to process the incoming interchange because BizTalk Server was unable to authenticate the sender of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a763-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2a763-119">User Action</span></span>  
 <span data-ttu-id="2a763-120">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2a763-120">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="2a763-121">Compruebe que el calificador e identificador del remitente que aparece en el encabezado del intercambio (campos ISA5 e ISA6 para X12 o UNB2.1 y UNB2.2 para EDIFACT) coincide con el calificador e identificador del remitente que aparece en las propiedades de una entidad (tal como se define en la página Propiedades de procesamiento de intercambio del cuadro de diálogo Propiedades de EDI).</span><span class="sxs-lookup"><span data-stu-id="2a763-121">Verify that the sender qualifier and identifier in the interchange header (fields ISA5 and ISA6 for X12 or UNB2.1 and UNB2.2 for EDIFACT) match the sender qualifier and identifier in the properties of a party (as defined in the Interchange Processing Properties page of the EDI Properties dialog box).</span></span>  
  
-   <span data-ttu-id="2a763-122">Compruebe que la información de seguridad y de contraseña que aparece en el encabezado del intercambio (campos IISA3 e ISA4 para X12 o UNB6.1 y UNB6.2 para EDIFACT) coincide con la información de seguridad y de contraseña que aparece en las propiedades de una entidad (tal como se define en la página Propiedades de procesamiento de intercambio del cuadro de diálogo Propiedades de EDI).</span><span class="sxs-lookup"><span data-stu-id="2a763-122">Verify that the security/password information in the header of the interchange (fields ISA3 and ISA4 for X12 or UNB6.1 and UNB6.2 for EDIFACT) match the security/password information in the properties of a party (as defined in the Interchange Processing Properties page of the EDI Properties dialog box).</span></span>