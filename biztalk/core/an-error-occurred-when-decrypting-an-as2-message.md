---
title: Se produjo un error al descifrar un mensaje AS2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bfb1d2a-c79d-4541-8a6d-bab0986f456b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 183933ae48468569cdd89f1d051f4bf961c71e05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="an-error-occurred-when-decrypting-an-as2-message"></a><span data-ttu-id="09bbd-102">Error al descifrar un mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="09bbd-102">An error occurred when decrypting an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="09bbd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="09bbd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09bbd-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="09bbd-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="09bbd-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="09bbd-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="09bbd-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="09bbd-106">Event ID</span></span>|-|  
|<span data-ttu-id="09bbd-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="09bbd-107">Event Source</span></span>|<span data-ttu-id="09bbd-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09bbd-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="09bbd-109">Componente</span><span class="sxs-lookup"><span data-stu-id="09bbd-109">Component</span></span>|<span data-ttu-id="09bbd-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="09bbd-110">AS2 Engine</span></span>|  
|<span data-ttu-id="09bbd-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="09bbd-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="09bbd-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="09bbd-112">Message Text</span></span>|<span data-ttu-id="09bbd-113">Error al descifrar un mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="09bbd-113">An error occurred when decrypting an AS2 message.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="09bbd-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="09bbd-114">Explanation</span></span>  
 <span data-ttu-id="09bbd-115">Este evento de error,  indica que la canalización de recepción o el componente de descodificador AS2 no pudo descifrar el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="09bbd-115">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decrypt the AS2 message.</span></span> <span data-ttu-id="09bbd-116">Esto puede tener lugar si el certificado usado en el proceso de descifrado no es válido, no se almacena en la ubicación adecuada o no coincide con el certificado usado en el proceso de descifrado.</span><span class="sxs-lookup"><span data-stu-id="09bbd-116">This can occur if the certificate used in the decryption process is not valid, is not stored in the appropriate location, or does not match the certificate used in the encryption process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="09bbd-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="09bbd-117">User Action</span></span>  
 <span data-ttu-id="09bbd-118">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="09bbd-118">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="09bbd-119">Compruebe que el contenedor de cifrado del mensaje AS2 es válido.</span><span class="sxs-lookup"><span data-stu-id="09bbd-119">Verify that the encryption wrapper in the AS2 message is valid.</span></span> <span data-ttu-id="09bbd-120">Si no es así, determine por qué el codificador ha codificado el mensaje de manera incorrecta.</span><span class="sxs-lookup"><span data-stu-id="09bbd-120">If not, determine why the message was encoded improperly by the encoder.</span></span>  
  
-   <span data-ttu-id="09bbd-121">Compruebe que coinciden la clave pública usada en el proceso de cifrado y la clave privada usada en el proceso de descifrado.</span><span class="sxs-lookup"><span data-stu-id="09bbd-121">Verify that the public key used in the encryption process and the private key used in the decryption process match.</span></span>  
  
-   <span data-ttu-id="09bbd-122">Compruebe que la propiedad Uso de la clave del certificado usado para el cifrado y el descifrado se ha establecido en "Cifrado de datos".</span><span class="sxs-lookup"><span data-stu-id="09bbd-122">Verify that the Key Usage property of the certificate used for encryption and decryption is set to "data encipherment".</span></span>  
  
-   <span data-ttu-id="09bbd-123">Compruebe que no haya ninguna cadena rota de entidades de certificación intermedias.</span><span class="sxs-lookup"><span data-stu-id="09bbd-123">Verify that there is not a broken chain of intermediate certificate authorities.</span></span> <span data-ttu-id="09bbd-124">Si es así, borre el certificado antiguo, y cree y use uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="09bbd-124">If there is, delete the old certificate, and create and use a new certificate.</span></span>  
  
-   <span data-ttu-id="09bbd-125">Compruebe que el certificado no ha expirado. Para ello, compruebe su fecha de expiración en el almacén de certificados (mediante MMC con un complemento de certificados).</span><span class="sxs-lookup"><span data-stu-id="09bbd-125">Verify that the certificate has not timed out by checking its expiration date in the Certificates store (using MMC with a certificates snap-in.).</span></span>  
  
-   <span data-ttu-id="09bbd-126">Compruebe que el certificado no se haya revocado. Para ello, compruebe la lista de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="09bbd-126">Verify that the certificate has not been revoked by checking the Certification Revocation List.</span></span> <span data-ttu-id="09bbd-127">(Puede hacer que BizTalk Server compruebe esto automáticamente si activa la propiedad Comprobar lista de revocaciones de certificados en las propiedades generales de AS2 de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="09bbd-127">(You can have BizTalk Server check this automatically by checking the Check Certification Revocation List property in the General AS2 properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.)</span></span>  
  
-   <span data-ttu-id="09bbd-128">Compruebe que el certificado usado para el descifrado se almacena en el almacén Usuario actual/Personal de cada servidor BizTalk que hospeda una canalización del descodificador de MIME/SMIME como cada cuenta de servicio de instancia de host.</span><span class="sxs-lookup"><span data-stu-id="09bbd-128">Verify that the certificate used for decryption is stored in the Current User\Personal store of each BizTalk server that hosts a MIME/SMIME decoder pipeline as each host instance service account.</span></span>