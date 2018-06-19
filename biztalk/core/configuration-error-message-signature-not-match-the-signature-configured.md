---
title: Error de configuración. El no de firma de mensaje &#39; t coincide con la firma configurada para esta entidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cea0016-12e8-4ee8-ac44-11024b5e74ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23214832300fe6125318ce67083f6bee0a364158
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232492"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a><span data-ttu-id="14549-103">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="14549-103">Configuration error.</span></span> <span data-ttu-id="14549-104">El no de firma de mensaje &#39; coincidencia t la firma configurada para esta entidad</span><span class="sxs-lookup"><span data-stu-id="14549-104">The message signature doesn&#39;t match the signature configured for this party</span></span>
## <a name="details"></a><span data-ttu-id="14549-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="14549-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14549-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="14549-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="14549-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="14549-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="14549-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="14549-108">Event ID</span></span>|-|  
|<span data-ttu-id="14549-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="14549-109">Event Source</span></span>|<span data-ttu-id="14549-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14549-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="14549-111">Componente</span><span class="sxs-lookup"><span data-stu-id="14549-111">Component</span></span>|<span data-ttu-id="14549-112">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="14549-112">AS2 Engine</span></span>|  
|<span data-ttu-id="14549-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="14549-113">Symbolic Name</span></span>|-|  
|<span data-ttu-id="14549-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="14549-114">Message Text</span></span>|<span data-ttu-id="14549-115">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="14549-115">Configuration error.</span></span> <span data-ttu-id="14549-116">La firma del mensaje no coincide con la firma configurada para esta entidad.</span><span class="sxs-lookup"><span data-stu-id="14549-116">The message signature doesn't match the signature configured for this party.</span></span> <span data-ttu-id="14549-117">Póngase en contacto con el socio remitente y verifique el certificado utilizado.</span><span class="sxs-lookup"><span data-stu-id="14549-117">Contact the sending partner and verify the certificate used.</span></span> <span data-ttu-id="14549-118">AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}"</span><span class="sxs-lookup"><span data-stu-id="14549-118">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14549-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="14549-119">Explanation</span></span>  
 <span data-ttu-id="14549-120">Este evento de error,  indica que la canalización de recepción AS2 no pudo comprobar la firma al realizar el procesamiento MIME.</span><span class="sxs-lookup"><span data-stu-id="14549-120">This Error/Warning/Information event indicates that the AS2 receive pipeline could not verify the signature when performing MIME processing.</span></span> <span data-ttu-id="14549-121">Esto puede deberse al uso de un certificado para procesar el mensaje recibido diferente del que usó el remitente para firmar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="14549-121">This could result from using a different certificate to process the received message than the sender used to sign the message.</span></span> <span data-ttu-id="14549-122">Esto puede producirse si BizTalk Server usa la configuración de una entidad equivocada para comprobar la firma del mensaje AS2 entrante.</span><span class="sxs-lookup"><span data-stu-id="14549-122">This can occur if BizTalk Server uses the settings of the wrong party to verify the signature of the incoming AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14549-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="14549-123">User Action</span></span>  
 <span data-ttu-id="14549-124">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="14549-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="14549-125">Asegúrese de que el proceso de resolución de entidades del mensaje AS2 entrante determina la entidad correcta.</span><span class="sxs-lookup"><span data-stu-id="14549-125">Ensure that the correct party is determined by the party resolution process for the incoming AS2 message.</span></span> <span data-ttu-id="14549-126">Para ello, compruebe que se resuelve la entidad correcta cuando BizTalk Server intenta encontrar una coincidencia entre el encabezado AS2-From del mensaje entrante y el valor para EDIINT-AS2 From de la lista Alias de la página General del cuadro de diálogo Propiedades de entidad.</span><span class="sxs-lookup"><span data-stu-id="14549-126">Do so by verifying that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From header in the incoming message and the value for EDIINT-AS2 From in the Aliases list in the General page of the Party Properties dialog box.</span></span> <span data-ttu-id="14549-127">Si de este modo no se resuelve la entidad, compruebe que se resuelve la entidad correcta cuando BizTalk Server trata de encontrar una coincidencia entre la propiedad de contexto AS2-From que se haya establecido para el mensaje entrante y el nombre de una entidad.</span><span class="sxs-lookup"><span data-stu-id="14549-127">If that does not resolve the party, verify that the correct party is resolved when BizTalk Server attempts to find a match between the AS2-From context property that is set for the incoming message and the name of a party.</span></span>  
  
-   <span data-ttu-id="14549-128">Asegúrese de que el certificado definido en la página Certificado del cuadro de diálogo Propiedades de entidad y almacenado en el almacén Equipo local\Otras personas corresponde al certificado usado para firmar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="14549-128">Ensure that the certificate defined in the Certificate page of the Party Properties dialog box, and stored in the Local computer\Other People store, corresponds to the certificate used to sign the message.</span></span>