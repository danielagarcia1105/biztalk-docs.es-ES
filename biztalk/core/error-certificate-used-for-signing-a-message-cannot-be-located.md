---
title: No se encuentra el certificado usado para firmar un mensaje en el almacén de certificados local | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff3c7a2-954c-4c62-a7b2-06f7a38d61b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94049a0ecca4e7aec89c5163231c0b9bf4c9e3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239964"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a><span data-ttu-id="dd9e7-102">El certificado usado para firmar un mensaje no puede ubicarse en el almacén local de certificados</span><span class="sxs-lookup"><span data-stu-id="dd9e7-102">The certificate used for signing a message cannot be located in the local certificate store</span></span>
## <a name="details"></a><span data-ttu-id="dd9e7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dd9e7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd9e7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="dd9e7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="dd9e7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="dd9e7-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="dd9e7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="dd9e7-106">Event ID</span></span>|-|  
|<span data-ttu-id="dd9e7-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="dd9e7-107">Event Source</span></span>|<span data-ttu-id="dd9e7-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd9e7-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="dd9e7-109">Componente</span><span class="sxs-lookup"><span data-stu-id="dd9e7-109">Component</span></span>|<span data-ttu-id="dd9e7-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="dd9e7-110">AS2 Engine</span></span>|  
|<span data-ttu-id="dd9e7-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dd9e7-111">Symbolic Name</span></span>|<span data-ttu-id="dd9e7-112">CertificateMissingError</span><span class="sxs-lookup"><span data-stu-id="dd9e7-112">CertificateMissingError</span></span>|  
|<span data-ttu-id="dd9e7-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dd9e7-113">Message Text</span></span>|<span data-ttu-id="dd9e7-114">El certificado usado para firmar un mensaje no puede ubicarse en el almacén local de certificados.</span><span class="sxs-lookup"><span data-stu-id="dd9e7-114">The certificate used for signing a message cannot be located in the local certificate store.</span></span> <span data-ttu-id="dd9e7-115">Huella digital del certificado: {0}</span><span class="sxs-lookup"><span data-stu-id="dd9e7-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dd9e7-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="dd9e7-116">Explanation</span></span>  
 <span data-ttu-id="dd9e7-117">Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje saliente porque el certificado identificado como certificado de firma no se encontraba en el almacén de certificados requerido.</span><span class="sxs-lookup"><span data-stu-id="dd9e7-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the signing certificate was not in the required certificate store.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dd9e7-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dd9e7-118">User Action</span></span>  
 <span data-ttu-id="dd9e7-119">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd9e7-119">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="dd9e7-120">Identifique el certificado de firma. Para ello, abra la consola de administración de BizTalk Server, haga clic con el botón secundario en Grupo de BizTalk y, a continuación, haga clic en el nodo Certificado.</span><span class="sxs-lookup"><span data-stu-id="dd9e7-120">Identify the signing certificate by opening the BizTalk Server Administration Console, right-clicking the BizTalk Group, and then clicking the Certificate node.</span></span>  
  
2.  <span data-ttu-id="dd9e7-121">Abra MMC, agregue el complemento para Mi cuenta de usuario y abra el nodo Certificados, Personal y Certificados.</span><span class="sxs-lookup"><span data-stu-id="dd9e7-121">Open MMC, add the snap-in for the My user account, and then open the Certificates, Personal, and Certificates node.</span></span>  
  
3.  <span data-ttu-id="dd9e7-122">Asegúrese de que el almacén de certificados Usuario actual contiene la clave privada para dicho certificado de firma y consulte la huella digital identificada en el texto de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="dd9e7-122">Make sure that the Current User certificate store contains the private key for that signing certificate by looking for the thumbprint identified in the error message text.</span></span>