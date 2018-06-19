---
title: Se ha revocado el certificado utilizado para descifrar un mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01767cb2-b16e-4b4b-ac4d-cd79b6c8860a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cd9404f13f737b4cb82317193344e006979d333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277916"
---
# <a name="the-certificate-used-to-decrypt-a-message-has-been-revoked"></a><span data-ttu-id="f070f-102">Se ha revocado el certificado usado para descifrar un mensaje</span><span class="sxs-lookup"><span data-stu-id="f070f-102">The certificate used to decrypt a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="f070f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f070f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f070f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f070f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f070f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f070f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f070f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f070f-106">Event ID</span></span>|-|  
|<span data-ttu-id="f070f-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f070f-107">Event Source</span></span>|<span data-ttu-id="f070f-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f070f-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f070f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f070f-109">Component</span></span>|<span data-ttu-id="f070f-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="f070f-110">AS2 Engine</span></span>|  
|<span data-ttu-id="f070f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f070f-111">Symbolic Name</span></span>|<span data-ttu-id="f070f-112">DecryptionCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="f070f-112">DecryptionCertificateHasBeenRevokedError</span></span>|  
|<span data-ttu-id="f070f-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f070f-113">Message Text</span></span>|<span data-ttu-id="f070f-114">Se ha revocado el certificado usado para descifrar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f070f-114">The certificate used to decrypt a message has been revoked.</span></span> <span data-ttu-id="f070f-115">Huella digital del certificado: {0}</span><span class="sxs-lookup"><span data-stu-id="f070f-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f070f-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f070f-116">Explanation</span></span>  
 <span data-ttu-id="f070f-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el mensaje entrante porque se ha revocado el certificado que debe usarse para descifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f070f-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming message because the certificate to be used to decrypt the message has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f070f-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f070f-118">User Action</span></span>  
 <span data-ttu-id="f070f-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f070f-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="f070f-120">Cree un nuevo certificado para reemplazar el certificado revocado.</span><span class="sxs-lookup"><span data-stu-id="f070f-120">Create a new certificate to replace the revoked certificate.</span></span> <span data-ttu-id="f070f-121">Agregue el certificado al almacén de certificados Usuario actual/Personal y envíe la clave pública del certificado a la entidad de envío del mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="f070f-121">Add the certificate to the Current User/Personal certificate store, and then send the public key of the certificate to the sending of the AS2 message.</span></span>  
  
-   <span data-ttu-id="f070f-122">Deshabilite la comprobación de la lista de revocación. Para ello, abra la consola de administración de BizTalk Server y el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje saliente, haga clic en el nodo General y, a continuación, desactive la propiedad Comprobar lista de revocaciones de certificados.</span><span class="sxs-lookup"><span data-stu-id="f070f-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>