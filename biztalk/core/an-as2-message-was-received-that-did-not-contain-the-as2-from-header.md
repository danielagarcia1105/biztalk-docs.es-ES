---
title: "Se recibió un mensaje AS2 que no contenía AS2-de encabezado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 899f9b21-b321-49a3-84bd-a5410c883968
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a63829b8a52088893a595549637f82be67efcd59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-from-header"></a><span data-ttu-id="5d1cf-102">Se recibió un mensaje AS2 que no contenía AS2-de encabezado</span><span class="sxs-lookup"><span data-stu-id="5d1cf-102">An AS2 message was received that did not contain the AS2-From header</span></span>
## <a name="details"></a><span data-ttu-id="5d1cf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d1cf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d1cf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5d1cf-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5d1cf-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5d1cf-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5d1cf-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5d1cf-106">Event ID</span></span>|-|  
|<span data-ttu-id="5d1cf-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5d1cf-107">Event Source</span></span>|<span data-ttu-id="5d1cf-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d1cf-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="5d1cf-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5d1cf-109">Component</span></span>|<span data-ttu-id="5d1cf-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="5d1cf-110">AS2 Engine</span></span>|  
|<span data-ttu-id="5d1cf-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5d1cf-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="5d1cf-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5d1cf-112">Message Text</span></span>|<span data-ttu-id="5d1cf-113">Se recibió un mensaje AS2 que no contenía AS2-de encabezado</span><span class="sxs-lookup"><span data-stu-id="5d1cf-113">An AS2 message was received that did not contain the AS2-From header</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d1cf-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="5d1cf-114">Explanation</span></span>  
 <span data-ttu-id="5d1cf-115">Este evento de error,  indica que BizTalk Server no pudo procesar el mensaje AS2 entrante porque el mensaje no contiene un encabezado AS2-From que indique su origen.</span><span class="sxs-lookup"><span data-stu-id="5d1cf-115">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message did not contain an AS2-From header indicating the source of the message.</span></span> <span data-ttu-id="5d1cf-116">Los mensajes AS2 deben tener un encabezado AS2-From.</span><span class="sxs-lookup"><span data-stu-id="5d1cf-116">An AS2 message must have an AS2-From header.</span></span> <span data-ttu-id="5d1cf-117">El mensaje se suspenderá si no tiene un encabezado AS2-From.</span><span class="sxs-lookup"><span data-stu-id="5d1cf-117">The message will be suspended if it does not have an AS2-From header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d1cf-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5d1cf-118">User Action</span></span>  
 <span data-ttu-id="5d1cf-119">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d1cf-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="5d1cf-120">Asegúrese de que la entidad remitente agrega un encabezado AS2-To al encabezado HTTP, AS2 y MIME del mensaje AS2 antes de enviarlo.</span><span class="sxs-lookup"><span data-stu-id="5d1cf-120">Ensure the sending party adds an AS2-To header to the HTTP, AS2, and MIME header of the AS2 message before sending it.</span></span>