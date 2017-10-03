---
title: Se produjo un error al validar un mensaje AS2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0cf97c63-2bff-4474-9cd8-f68634493dcc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73f1c9b7cf4e444e256aadc3ade717fcf30735bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-error-occurred-when-validating-an-as2-message"></a><span data-ttu-id="64757-102">Se produjo un error al validar un mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="64757-102">An error occurred when validating an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="64757-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="64757-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64757-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="64757-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="64757-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="64757-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="64757-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="64757-106">Event ID</span></span>|-|  
|<span data-ttu-id="64757-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="64757-107">Event Source</span></span>|<span data-ttu-id="64757-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64757-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="64757-109">Componente</span><span class="sxs-lookup"><span data-stu-id="64757-109">Component</span></span>|<span data-ttu-id="64757-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="64757-110">AS2 Engine</span></span>|  
|<span data-ttu-id="64757-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="64757-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="64757-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="64757-112">Message Text</span></span>|<span data-ttu-id="64757-113">Se produjo un error al validar un mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="64757-113">An error occurred when validating an AS2 message.</span></span> <span data-ttu-id="64757-114">Asegúrese de que los certificados no han caducado ni se han revocado.</span><span class="sxs-lookup"><span data-stu-id="64757-114">Make sure the certificates used have not timed out or been revoked.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64757-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="64757-115">Explanation</span></span>  
 <span data-ttu-id="64757-116">Este evento de error,  indica que la canalización de recepción AS2 o la canalización de envío AS2 no pudo procesar el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="64757-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not validate the AS2 message.</span></span> <span data-ttu-id="64757-117">Esto puede tener lugar si el certificado usado en el proceso de comprobación de firma no es válido, no se almacena en la ubicación adecuada o no coincide con el certificado usado en el proceso de firma.</span><span class="sxs-lookup"><span data-stu-id="64757-117">This can occur if the certificate used in the signature verification process is not valid, is not stored in the appropriate location, or does not match the certificate used in the signing process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64757-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="64757-118">User Action</span></span>  
 <span data-ttu-id="64757-119">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="64757-119">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="64757-120">Compruebe que el contenedor de firmas del mensaje AS2 es válido.</span><span class="sxs-lookup"><span data-stu-id="64757-120">Verify that the signature wrapper in the AS2 message is valid.</span></span> <span data-ttu-id="64757-121">Si no es así, determine por qué el codificador ha firmado el mensaje de manera incorrecta.</span><span class="sxs-lookup"><span data-stu-id="64757-121">If not, determine why the message was signed improperly by the encoder.</span></span>  
  
-   <span data-ttu-id="64757-122">Compruebe que coinciden la clave privada usada en el proceso de firma y la clave pública usada en el proceso de comprobación de firma.</span><span class="sxs-lookup"><span data-stu-id="64757-122">Verify that the private key used in the signing process and the public key used in the signature verification process match.</span></span>  
  
-   <span data-ttu-id="64757-123">Compruebe que la propiedad Uso de la clave del certificado usado para firmar y la comprobación de la firma se ha establecido en "Cifrado de datos".</span><span class="sxs-lookup"><span data-stu-id="64757-123">Verify that the Key Usage property of the certificate used for signing and signature verification is set to "data encipherment".</span></span>  
  
-   <span data-ttu-id="64757-124">Compruebe que no haya ninguna cadena rota de entidades de certificación intermedias.</span><span class="sxs-lookup"><span data-stu-id="64757-124">Verify that there is not a broken chain of intermediate certificate authorities.</span></span> <span data-ttu-id="64757-125">Si es así, borre el certificado antiguo, y cree y use uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="64757-125">If there is, delete the old certificate, and create and use a new certificate.</span></span>  
  
-   <span data-ttu-id="64757-126">Compruebe que el certificado no ha expirado. Para ello, compruebe su fecha de expiración en el almacén de certificados (mediante MMC con un complemento de certificados).</span><span class="sxs-lookup"><span data-stu-id="64757-126">Verify that the certificate has not timed out by checking its expiration date in the Certificates store (using MMC with a certificates snap-in.).</span></span>  
  
-   <span data-ttu-id="64757-127">Compruebe que el certificado no se haya revocado. Para ello, compruebe la lista de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="64757-127">Verify that the certificate has not been revoked by checking the Certification Revocation List.</span></span> <span data-ttu-id="64757-128">(Puede tener que BizTalk Server compruebe esto automáticamente mediante la comprobación de la propiedad Comprobar lista de revocación de certificados en las propiedades generales de AS2 en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.)</span><span class="sxs-lookup"><span data-stu-id="64757-128">(You can have BizTalk Server check this automatically by checking the Check Certification Revocation List property in the General AS2 properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.)</span></span>  
  
-   <span data-ttu-id="64757-129">Compruebe que el certificado usado para la comprobación de firmas se almacena en el almacén Equipo local/Otras personas de cada servidor BizTalk que hospeda una canalización del descodificador de MIME/SMIME como cada cuenta de servicio de instancia de host.</span><span class="sxs-lookup"><span data-stu-id="64757-129">Verify that the certificate used for signature verification is stored in the Local computer/Other People store of each BizTalk server that hosts a MIME/SMIME decoder pipeline as each host instance service account.</span></span>