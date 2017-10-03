---
title: "Prácticas recomendadas para administrar Certificates1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, certificates
- certificates, security
- security, certificates
- certificates, best practices
- best practices, security
- security, best practices
ms.assetid: cd182df4-0fcd-409c-9221-89f92e069f07
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e72d87530e5d080bd98ed55c2d29ca9554430375
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-managing-certificates"></a><span data-ttu-id="59ad5-102">Prácticas recomendadas para la administración de certificados</span><span class="sxs-lookup"><span data-stu-id="59ad5-102">Best Practices for Managing Certificates</span></span>
<span data-ttu-id="59ad5-103">Esta sección proporciona los procedimientos recomendados para administrar certificados en el entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59ad5-103">This section provides best practices for managing certificates in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="59ad5-104">**Realizar un análisis de modelo de amenazas de su entorno**</span><span class="sxs-lookup"><span data-stu-id="59ad5-104">**Do a Threat Model Analysis of your environment**</span></span>  
  
     <span data-ttu-id="59ad5-105">Lleve a cabo un análisis de modelo de amenazas (TMA) de su entorno para determinar si los certificados de firma o cifrado contribuirán a minimizar las amenazas para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="59ad5-105">Do a Threat Model Analysis (TMA) of your environment to determine whether signing or encryption certificates will help you mitigate security threats.</span></span>  
  
-   <span data-ttu-id="59ad5-106">**Crear un plan para certificados de clave pública con socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="59ad5-106">**Create a plan for public key certificates with partners**</span></span>  
  
     <span data-ttu-id="59ad5-107">Cree un plan para efectuar el envío y recepción de certificados de clave pública con socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="59ad5-107">Create a plan for sending and receiving public key certificates with partners.</span></span> <span data-ttu-id="59ad5-108">Si no utiliza certificados de firma para la resolución de entidades, el certificado público puede adjuntarse al mensaje, en cuyo caso no se necesitará una copia del certificado de antemano en su sistema.</span><span class="sxs-lookup"><span data-stu-id="59ad5-108">If you are not using signing certificates for party resolution, the public certificate can be attached to the message, in which case you do not need a copy of the certificate in your system beforehand.</span></span>  
  
-   <span data-ttu-id="59ad5-109">**Descargar la lista de revocación de certificados a intervalos establecidos**</span><span class="sxs-lookup"><span data-stu-id="59ad5-109">**Download the certificate revocation list at set intervals**</span></span>  
  
     <span data-ttu-id="59ad5-110">Descargue la lista de revocaciones de certificados (CRL) de su entidad emisora de certificados (CA) a intervalos determinados.</span><span class="sxs-lookup"><span data-stu-id="59ad5-110">Download the certificate revocation list (CRL) from your certification authority (CA) at set intervals.</span></span> <span data-ttu-id="59ad5-111">Se recomienda llevar esto a cabo una vez a la semana.</span><span class="sxs-lookup"><span data-stu-id="59ad5-111">We recommend doing this once a week.</span></span> <span data-ttu-id="59ad5-112">Las CRL se descargan automáticamente si hay una CA para el dominio al que se han unido los servidores BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="59ad5-112">The CRLs are downloaded automatically if there is a CA for the domain in which the BizTalk servers are joined.</span></span>  
  
-   <span data-ttu-id="59ad5-113">**Establezca directrices con socios comerciales para el envío de claves públicas**</span><span class="sxs-lookup"><span data-stu-id="59ad5-113">**Establish guidelines with partners for submitting public keys**</span></span>  
  
     <span data-ttu-id="59ad5-114">Como parte del contrato de nivel de servicio (SLA) con el socio comercial, establezca directrices para el envío de claves públicas, con lo que se le notificará el momento de revocación y de inminente caducidad de los certificados.</span><span class="sxs-lookup"><span data-stu-id="59ad5-114">As part of your Service Level Agreement (SLA) with your partner, establish guidelines for submitting public keys, notifying you when their certificates are about to expire, and notifying you when they revoke a certificate.</span></span>  
  
-   <span data-ttu-id="59ad5-115">**Comprobar los certificados de firmas**</span><span class="sxs-lookup"><span data-stu-id="59ad5-115">**Verify signing certificates**</span></span>  
  
     <span data-ttu-id="59ad5-116">Asegúrese de efectuar una comprobación de los certificados de firma con respecto a la lista de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="59ad5-116">Make sure you verify the signing certificates against the certificate revocation list.</span></span> <span data-ttu-id="59ad5-117">Para obtener más información acerca de cómo comprobar los certificados de firma, vea [cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="59ad5-117">For more information about how to verify the signing certificates, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="59ad5-118">**Evite la denegación de ataques de servicio para las firmas digitales**</span><span class="sxs-lookup"><span data-stu-id="59ad5-118">**Avoid denial of service attacks for digital signatures**</span></span>  
  
     <span data-ttu-id="59ad5-119">Determine qué desea hacer con los mensajes cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no pueda validar la firma digital.</span><span class="sxs-lookup"><span data-stu-id="59ad5-119">Determine what you want to do with messages when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot validate the digital signature.</span></span> <span data-ttu-id="59ad5-120">Establecer el **autenticación** propiedad del puerto de recepción le ayudará a evitar la denegación de servicio ataques.</span><span class="sxs-lookup"><span data-stu-id="59ad5-120">Setting the **Authentication** property on the receive port will help prevent denial of service attacks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59ad5-121">El **autenticación - quitar mensajes** y **autenticación - mantener mensajes** marcas en el puerto de recepción requieren que el componente de canalización de resolución de entidades se ha configurado correctamente y que las partes son definido en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="59ad5-121">The **Authentication - Drop messages** and **Authentication - Keep messages** flags on the receive port require that the Party Resolution pipeline component be configured correctly, and that the parties are defined in BizTalk Server.</span></span> <span data-ttu-id="59ad5-122">Para obtener más información acerca de cómo configurar el componente de canalización de resolución de entidades, vea [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="59ad5-122">For more information about configuring the Party Resolution pipeline component, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="59ad5-123">**Crear diferentes ubicaciones de recepción de mensajes cifrados y sin cifrar**</span><span class="sxs-lookup"><span data-stu-id="59ad5-123">**Create separate receive locations for encrypted and unencrypted messages**</span></span>  
  
     <span data-ttu-id="59ad5-124">Si planea recibir mensajes con cifrado MIME de algunos socios comerciales y mensajes sin cifrar de otros, cree ubicaciones de recepción independientes en hosts diferentes para mensajes cifrados y sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="59ad5-124">If you plan to receive MIME-encrypted messages from some partners and unencrypted messages from other partners, create separate receive locations in different hosts for encrypted and unencrypted messages.</span></span> <span data-ttu-id="59ad5-125">Cuando se espera que sólo los mensajes cifrados con MIME, configure la **permitir mensaje no MIME** opción en el componente de canalización de descodificación MIME/SMIME para **No**.</span><span class="sxs-lookup"><span data-stu-id="59ad5-125">When you expect only MIME-encrypted messages, configure the **Allow Non MIME Message** option in the Decode MIME/SMIME pipeline component to **No**.</span></span>  
  
-   <span data-ttu-id="59ad5-126">**Administrar certificados con socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="59ad5-126">**Manage certificates with partners**</span></span>  
  
     <span data-ttu-id="59ad5-127">Haga que la administración de certificados forme parte de las prácticas de administración de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="59ad5-127">Make certificate management part of your partner management practices.</span></span> <span data-ttu-id="59ad5-128">Al agregar una entidad al entorno de BizTalk Server o quitarla de éste, resulta recomendable agregar o quitar certificados asociados con el socio comercial.</span><span class="sxs-lookup"><span data-stu-id="59ad5-128">When you add or remove a party from the BizTalk Server environment, we recommend that you add or remove the certificates associated with that partner.</span></span>  
  
-   <span data-ttu-id="59ad5-129">**Quite certificados antes de quitar una instancia de host**</span><span class="sxs-lookup"><span data-stu-id="59ad5-129">**Remove certificates before removing a host instance**</span></span>  
  
     <span data-ttu-id="59ad5-130">Antes de quitar una instancia de host de un servidor BizTalk Server, quite los certificados del almacén personal de la cuenta en la que se ejecuta la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="59ad5-130">Before removing a host instance from a BizTalk server, remove the certificates in the personal store of the account under which the host instance is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ad5-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="59ad5-131">See Also</span></span>  
 <span data-ttu-id="59ad5-132">[Administrar la seguridad de servidor BizTalk Server](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="59ad5-132">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 [<span data-ttu-id="59ad5-133">Prácticas recomendadas para administrar las cuentas de usuario y grupos de Windows</span><span class="sxs-lookup"><span data-stu-id="59ad5-133">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)