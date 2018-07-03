---
title: Identificar las posibles amenazas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd2feb0b6a09905efb7275b1cc6f0e6ef2b13d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972573"
---
# <a name="identifying-potential-threats"></a><span data-ttu-id="e0484-102">Identificar las posibles amenazas</span><span class="sxs-lookup"><span data-stu-id="e0484-102">Identifying Potential Threats</span></span>
<span data-ttu-id="e0484-103">Puede utilizar el modelo STRIDE para identificar posibles amenazas para la implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e0484-103">You can use the STRIDE model to identify potential threats to your BizTalk Server deployment.</span></span> <span data-ttu-id="e0484-104">STRIDE es un acrónimo derivado de las siguientes categorías: *S*identidad uplantación, *T*anipulación de datos, *R*epudio, *me* revelación de información *d.* enegación de servicio y elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="e0484-104">STRIDE is an acronym derived from the following categories: *S*poofing identity, *T*ampering with data, *R*epudiation, *I*nformation disclosure, *D*enial of service, and Elevation of privileges.</span></span> <span data-ttu-id="e0484-105">Esta sección contiene ejemplo de posibles amenazas para el entorno de BizTalk Server y mecanismos para mitigarlas.</span><span class="sxs-lookup"><span data-stu-id="e0484-105">This section contains examples of potential threats to a BizTalk Server environment, and mechanisms to mitigate them.</span></span>  
  
 <span data-ttu-id="e0484-106">**Suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="e0484-106">**Spoofing identity**</span></span>  
  
- <span data-ttu-id="e0484-107">Si se guardan las contraseñas en los archivos de enlace y éstos se guardan, los usuarios no autorizados podrían leerlas y usarlas para conectarse a los servidores de BizTalk y causar daños en éstos.</span><span class="sxs-lookup"><span data-stu-id="e0484-107">If you save passwords in the binding files, and save these binding files, unauthorized users could read the passwords and use them to connect to the BizTalk Servers, and possibly cause harm.</span></span> <span data-ttu-id="e0484-108">Evite guardar las contraseñas en archivos de enlace y use listas de control de acceso discrecional (DACL) para restringir el acceso a archivos que puedan contener datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="e0484-108">You should not save passwords in binding files, and you should use discretionary access control lists (DACLs) to restrict access to files that may contain sensitive data.</span></span>  
  
  <span data-ttu-id="e0484-109">**Manipulación de datos**</span><span class="sxs-lookup"><span data-stu-id="e0484-109">**Tampering with data**</span></span>  
  
- <span data-ttu-id="e0484-110">Los usuarios malintencionados pueden interceptar mensajes de los socios a BizTalk Server y modificar su contenido.</span><span class="sxs-lookup"><span data-stu-id="e0484-110">Malicious users can intercept messages from partners to BizTalk Server, and modify the content of the message.</span></span> <span data-ttu-id="e0484-111">Use firmas digitales para impedir que los usuarios malintencionados manipulen los mensajes mientras están en tránsito.</span><span class="sxs-lookup"><span data-stu-id="e0484-111">You can use digital signatures to prevent malicious users from tampering with messages while they are in transit.</span></span>  
  
  <span data-ttu-id="e0484-112">**Rechazo**</span><span class="sxs-lookup"><span data-stu-id="e0484-112">**Repudiation**</span></span>  
  
- <span data-ttu-id="e0484-113">Es necesario realizar un seguimiento de los mensajes que envía y recibe BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e0484-113">You need to keep track of messages that BizTalk sends and receives.</span></span> <span data-ttu-id="e0484-114">Puede usar firmas digitales para probar que ha enviado, y que los socios le han enviado, mensajes.</span><span class="sxs-lookup"><span data-stu-id="e0484-114">You can use digital signatures to prove that you sent a message and that your partners sent you a message.</span></span>  
  
  <span data-ttu-id="e0484-115">**Divulgación de información**</span><span class="sxs-lookup"><span data-stu-id="e0484-115">**Information disclosure**</span></span>  
  
- <span data-ttu-id="e0484-116">Los usuarios malintencionados pueden leer la comunicación de texto sin cifrar entre BizTalk Server y Microsoft SQL Server™.</span><span class="sxs-lookup"><span data-stu-id="e0484-116">Malicious users can read clear-text communication between BizTalk Server and Microsoft SQL Server™.</span></span> <span data-ttu-id="e0484-117">Utilice la seguridad de Protocolo Internet (IPSec) o la Capa de sockets seguros (SSL) para garantizar la protección de las comunicaciones entre servidores.</span><span class="sxs-lookup"><span data-stu-id="e0484-117">You can use Internet Protocol security (IPSec), or Secure Sockets Layer (SSL) to help secure the communication between servers.</span></span> <span data-ttu-id="e0484-118">Puede usar servidores de seguridad para limitar el acceso a cada servidor.</span><span class="sxs-lookup"><span data-stu-id="e0484-118">You can use firewalls to limit access to each server.</span></span> <span data-ttu-id="e0484-119">Puede usar el cifrado para garantizar la privacidad del mensaje mientras está en tránsito.</span><span class="sxs-lookup"><span data-stu-id="e0484-119">You can use encryption to help ensure the privacy of the message while it is in transit.</span></span>  
  
- <span data-ttu-id="e0484-120">Puede que usuarios no autorizados obtengan acceso a información en recursos compartidos de red o directorios.</span><span class="sxs-lookup"><span data-stu-id="e0484-120">Unauthorized users may access information on network shares or directories.</span></span> <span data-ttu-id="e0484-121">Use listas seguras de control de acceso discrecional (DACL) para limitar el acceso a las cuentas que usan los recursos.</span><span class="sxs-lookup"><span data-stu-id="e0484-121">You can use strong discretionary access control lists (DACLs) to limit access to the accounts that use the resources.</span></span>  
  
- <span data-ttu-id="e0484-122">El administrador de Windows de un equipo que ejecuta una instancia de host de BizTalk podría llevar a cabo distintos niveles de ataques (por ejemplo, revelación de información o denegación del servicio).</span><span class="sxs-lookup"><span data-stu-id="e0484-122">The Windows administrator on a computer running a BizTalk Host instance can misbehave and carry out different levels of attacks (for example, information disclosure, or denial of service).</span></span> <span data-ttu-id="e0484-123">Sin embargo, en la mayoría de los casos, puede limitar estos ataques al host concreto cuyo equipo se ha visto comprometido por el atacante.</span><span class="sxs-lookup"><span data-stu-id="e0484-123">However, in most cases you can limit these attacks to the particular host whose computer the attacker compromised.</span></span>  
  
  <span data-ttu-id="e0484-124">**Denegación de servicio**</span><span class="sxs-lookup"><span data-stu-id="e0484-124">**Denial of service**</span></span>  
  
- <span data-ttu-id="e0484-125">Los usuarios malintencionados pueden enviar una gran cantidad de mensajes al servidor BizTalk Server para impedir que éste pueda recibir mensajes válidos.</span><span class="sxs-lookup"><span data-stu-id="e0484-125">A malicious user can send a large number of messages to BizTalk Server, which could prevent BizTalk from receiving valid messages.</span></span> <span data-ttu-id="e0484-126">Para obtener más información acerca de las técnicas de mitigación esta amenaza, consulte [mitigación de ataques de denegación de servicio](../core/mitigating-denial-of-service-attacks.md).</span><span class="sxs-lookup"><span data-stu-id="e0484-126">For more information about mitigation techniques to this threat, see [Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md).</span></span>  
  
  <span data-ttu-id="e0484-127">**Elevación de privilegios**</span><span class="sxs-lookup"><span data-stu-id="e0484-127">**Elevation of privileges**</span></span>  
  
- <span data-ttu-id="e0484-128">Las amenazas de elevación de privilegios suelen producirse cuando se ejecuta en un entorno de confianza un código en el que no se confía o cuando un usuario malintencionado explota un error de software o de configuración.</span><span class="sxs-lookup"><span data-stu-id="e0484-128">Elevation of privileges threats typically occur when code you do not trust runs in a trusted environment, or when a malicious user exploits a software or configuration flaw.</span></span> <span data-ttu-id="e0484-129">Debe asegurarse de que los ensamblados y los demás componentes que implementa en su entorno son de confianza.</span><span class="sxs-lookup"><span data-stu-id="e0484-129">You must ensure that you trust the assemblies and other components you deploy in your environment.</span></span> <span data-ttu-id="e0484-130">Para minimizar la posibilidad de un ataque de elevación de privilegios, utilice cuentas con permisos mínimos y que no se superpongan, y debería evitar el uso de cuentas administrativas para operaciones y servicios de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0484-130">To minimize the possibility of an elevation of privileges attack, you should use non-overlapping, least permission accounts, and you should avoid the use of administrative accounts for run time services and operations.</span></span> <span data-ttu-id="e0484-131">También debe minimizar el número de componentes, aplicaciones y servicios que se ejecutan en el entorno.</span><span class="sxs-lookup"><span data-stu-id="e0484-131">You should also minimize the number of components, applications, and services running in the environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0484-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0484-132">See Also</span></span>  
 <span data-ttu-id="e0484-133">[Denegación de servicio de mitigar los ataques](../core/mitigating-denial-of-service-attacks.md) </span><span class="sxs-lookup"><span data-stu-id="e0484-133">[Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md) </span></span>  
 <span data-ttu-id="e0484-134">[Recomendaciones de seguridad para una implementación de BizTalk Server](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="e0484-134">[Security Recommendations for a BizTalk Server Deployment](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span></span>  
 [<span data-ttu-id="e0484-135">Planear la seguridad</span><span class="sxs-lookup"><span data-stu-id="e0484-135">Planning for Security</span></span>](../core/planning-for-security.md)