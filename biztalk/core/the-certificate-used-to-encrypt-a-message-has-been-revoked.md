---
title: Se ha revocado el certificado utilizado para cifrar un mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c90690-002a-43bc-85f2-8aa5e7511ffa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fbe34dcd2906d79a8d80ebdd00c3d9f293e6559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a><span data-ttu-id="ed105-102">El certificado utilizado para cifrar un mensaje se ha revocado</span><span class="sxs-lookup"><span data-stu-id="ed105-102">The certificate used to encrypt a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="ed105-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ed105-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed105-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ed105-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ed105-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ed105-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ed105-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ed105-106">Event ID</span></span>|-|  
|<span data-ttu-id="ed105-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ed105-107">Event Source</span></span>|<span data-ttu-id="ed105-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed105-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="ed105-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ed105-109">Component</span></span>|<span data-ttu-id="ed105-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="ed105-110">AS2 Engine</span></span>|  
|<span data-ttu-id="ed105-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ed105-111">Symbolic Name</span></span>|<span data-ttu-id="ed105-112">EncryptionCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="ed105-112">EncryptionCertificateHasBeenRevokedError</span></span>|  
|<span data-ttu-id="ed105-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ed105-113">Message Text</span></span>|<span data-ttu-id="ed105-114">El certificado utilizado para cifrar un mensaje se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="ed105-114">The certificate used to encrypt a message has been revoked.</span></span> <span data-ttu-id="ed105-115">Huella digital del certificado: {0}</span><span class="sxs-lookup"><span data-stu-id="ed105-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ed105-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ed105-116">Explanation</span></span>  
 <span data-ttu-id="ed105-117">Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje saliente porque se ha recovado el certificado identificado como certificado de cifrado.</span><span class="sxs-lookup"><span data-stu-id="ed105-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the encryption certificate has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed105-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ed105-118">User Action</span></span>  
 <span data-ttu-id="ed105-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ed105-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="ed105-120">Pida al receptor del mensaje que cree un certificado nuevo y le envíe la clave pública.</span><span class="sxs-lookup"><span data-stu-id="ed105-120">Have the receiver of the message create a new certificate and send the public key to you.</span></span> <span data-ttu-id="ed105-121">Agregue el certificado al almacén de certificados Equipo local\Otras personas e identifique el certificado como certificado de cifrado en la página Certificado del cuadro de diálogo Propiedades de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="ed105-121">Add the certificate to the Local computer\Other People certificate store, and then identify the certificate as the encryption certificate in the Certificate page of the Send Port Properties dialog box.</span></span>  
  
-   <span data-ttu-id="ed105-122">Deshabilite la comprobación de la lista de revocación. Para ello, abra la consola de administración de BizTalk Server y el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje saliente, haga clic en el nodo General y, a continuación, desactive la propiedad Comprobar lista de revocaciones de certificados.</span><span class="sxs-lookup"><span data-stu-id="ed105-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>