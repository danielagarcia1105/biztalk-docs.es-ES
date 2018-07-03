---
title: Se ha revocado el certificado usado para firmar un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f822235a-8ad8-4b63-94de-9b7f9361a071
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2e05acaa5a1bca68952072f90364ac3890be9af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022722"
---
# <a name="the-certificate-used-for-signing-a-message-has-been-revoked"></a><span data-ttu-id="31620-102">El certificado usado para firmar un mensaje se ha revocado</span><span class="sxs-lookup"><span data-stu-id="31620-102">The certificate used for signing a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="31620-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="31620-103">Details</span></span>  
  
|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  <span data-ttu-id="31620-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="31620-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="31620-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="31620-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    <span data-ttu-id="31620-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="31620-106">Event ID</span></span>     |                                            -                                             |
|  <span data-ttu-id="31620-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="31620-107">Event Source</span></span>   |  <span data-ttu-id="31620-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31620-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>  |
|    <span data-ttu-id="31620-109">Componente</span><span class="sxs-lookup"><span data-stu-id="31620-109">Component</span></span>    |                                        <span data-ttu-id="31620-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="31620-110">AS2 Engine</span></span>                                        |
|  <span data-ttu-id="31620-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="31620-111">Symbolic Name</span></span>  |                          <span data-ttu-id="31620-112">SigningCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="31620-112">SigningCertificateHasBeenRevokedError</span></span>                           |
|  <span data-ttu-id="31620-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="31620-113">Message Text</span></span>   | <span data-ttu-id="31620-114">El certificado usado para firmar un mensaje se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="31620-114">The certificate used for signing a message has been revoked.</span></span> <span data-ttu-id="31620-115">Huella digital del certificado: {0}</span><span class="sxs-lookup"><span data-stu-id="31620-115">Certificate thumbprint: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="31620-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="31620-116">Explanation</span></span>  
 <span data-ttu-id="31620-117">Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje saliente porque se ha recovado el certificado identificado como certificado de firma.</span><span class="sxs-lookup"><span data-stu-id="31620-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the signing certificate has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31620-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="31620-118">User Action</span></span>  
 <span data-ttu-id="31620-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="31620-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="31620-120">Cree un certificado nuevo para reemplazar al certificado revocado.</span><span class="sxs-lookup"><span data-stu-id="31620-120">Create a new certificate to replaced the revoked certificate.</span></span> <span data-ttu-id="31620-121">Agregue el certificado al almacén de certificados de usuario actual, identifíquelo como certificado de firma en la página Certificado del cuadro de diálogo Propiedades de grupo y envíe la clave pública del certificado al destinatario del mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="31620-121">Add the certificate to the Current User certificate store, identify it as the signing certificate in the Certificate page of the Group Properties dialog box, and then send the public key of the certificate to the recipient of the AS2 message.</span></span>  
  
-   <span data-ttu-id="31620-122">Deshabilite la comprobación de la lista de revocación. Para ello, abra la consola de administración de BizTalk Server y el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje saliente, haga clic en el nodo General y, a continuación, desactive la propiedad Comprobar lista de revocaciones de certificados.</span><span class="sxs-lookup"><span data-stu-id="31620-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>