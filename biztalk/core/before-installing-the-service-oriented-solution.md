---
title: Antes de instalar el servicio de la solución orientada a servicios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, deployment prerequisites
ms.assetid: 865bd21c-e49a-4647-af91-fefee07ee806
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a735ed832051c24e5ccd253df61c42c07ed6e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982389"
---
# <a name="before-installing-the-service-oriented-solution"></a><span data-ttu-id="f00b1-102">Antes de instalar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="f00b1-102">Before Installing the Service Oriented Solution</span></span>
<span data-ttu-id="f00b1-103">Para instalar la versión de código auxiliar de la solución orientada a servicios en un único equipo, éste debe reunir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="f00b1-103">The following prerequisites must be available to install the stub version of the service-oriented solution on a single computer:</span></span>  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]<span data-ttu-id="f00b1-104">.</span><span class="sxs-lookup"><span data-stu-id="f00b1-104">.</span></span>  
  
- <span data-ttu-id="f00b1-105">Software compatible para [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f00b1-105">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
- <span data-ttu-id="f00b1-106">La última versión del cliente IBM WebSphere MQ para Windows</span><span class="sxs-lookup"><span data-stu-id="f00b1-106">The latest version of IBM WebSphere MQ Client for Windows</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f00b1-107">Para la versión de código auxiliar de la solución no se necesita MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f00b1-107">MQSeries Server is not required for the stub version of the solution.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f00b1-108">Puede descargar el cliente IBM WebSphere MQ para Windows desde el sitio Web de IBM.</span><span class="sxs-lookup"><span data-stu-id="f00b1-108">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
  <span data-ttu-id="f00b1-109">Para instalar las versiones de adaptador y en línea de la solución orientada a servicios en un único equipo:</span><span class="sxs-lookup"><span data-stu-id="f00b1-109">For installing the inline and adapter version of the service oriented solution on a single computer:</span></span>  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]<span data-ttu-id="f00b1-110">.</span><span class="sxs-lookup"><span data-stu-id="f00b1-110">.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f00b1-111">Necesita una cuenta de dominio para asignar credenciales para el inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="f00b1-111">A domain account is required to map credentials for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="f00b1-112">Se recomienda utilizar cuentas de dominio para el servicio de BizTalk y para las cuentas de servicio ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="f00b1-112">We recommend using domain accounts for the BizTalk service and for the ENTSSO service accounts.</span></span>  
  
- <span data-ttu-id="f00b1-113">Software compatible para [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f00b1-113">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
- <span data-ttu-id="f00b1-114">MQSeries Server en el equipo local o acceso al equipo en el que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f00b1-114">MQSeries Server on the local computer or access to the computer running the MQSeries Server.</span></span> <span data-ttu-id="f00b1-115">Para la versión en línea, las API de cliente de MQSeries deben estar disponibles en el servidor que ejecuta las orquestaciones de la solución.</span><span class="sxs-lookup"><span data-stu-id="f00b1-115">For the inline version, MQSeries client APIs must be available on the BizTalk server running the solution’s orchestrations.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f00b1-116">La versión de MQSeries Server debe coincidir con la versión requerida por el adaptador de MQSeries de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f00b1-116">The version of MQSeries Server must match the version required by the BizTalk Server MQSeries Adapter.</span></span> <span data-ttu-id="f00b1-117">Esto puede incluir IBM WebSphere MQ para Windows, versión 5.3, con Fix Pack 10 (CSD10) o posterior.</span><span class="sxs-lookup"><span data-stu-id="f00b1-117">This can include IBM WebSphere MQ for Windows Version 5.3 with Fix Pack 10 (CSD10) or later.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f00b1-118">Cuando se usan características como MQSeries que hacen llamadas del Modelo de objetos componentes distribuido (DCOM) al servidor, asegúrese de que no tiene un servidor de seguridad con NAT (Traducción de direcciones de red) habilitado.</span><span class="sxs-lookup"><span data-stu-id="f00b1-118">When using features such as MQSeries which make Distributed Component Object Model (DCOM) calls to the server, make sure you do not have a Network Address Translation (NAT)-based firewall enabled.</span></span> <span data-ttu-id="f00b1-119">El cliente debe poder obtener acceso al servidor mediante su dirección IP real y los servidores de seguridad con NAT traducen esta dirección en algo que el cliente no reconoce.</span><span class="sxs-lookup"><span data-stu-id="f00b1-119">The client must be able to access the server by its actual IP address, and NAT-based firewalls translate this address to something the client will not recognize.</span></span>  
  
- <span data-ttu-id="f00b1-120">Si va a utilizar una variación de la solución que requiere un gran sistema (mainframe), necesitará IBM Mainframe con CICS y Transaction X.</span><span class="sxs-lookup"><span data-stu-id="f00b1-120">IBM Mainframe with CICS and Transaction X if you are using a variation of the solution that requires a mainframe.</span></span> <span data-ttu-id="f00b1-121">En este caso, hay que instalar la aplicación CICS (código COBOL) en el gran sistema y necesitará Microsoft Host Integration Server (HIS) para obtener acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="f00b1-121">In this case, the CICS application (COBOL code) must be installed on the mainframe and Microsoft Host Integration Server (HIS) is required to access the mainframe.</span></span>  
  
   <span data-ttu-id="f00b1-122">Si la solución no requiere un gran sistema, puede modificar el enlace de puertos para utilizar el servicio Web de código auxiliar para las transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="f00b1-122">If you don’t have a mainframe for the solution, you can modify the port binding to use the stub Web service for Pending Transactions.</span></span> <span data-ttu-id="f00b1-123">El servicio Web genera transacciones localmente para emular las transacciones de gran sistema.</span><span class="sxs-lookup"><span data-stu-id="f00b1-123">The Web service generates transactions locally to emulate the mainframe transactions.</span></span> <span data-ttu-id="f00b1-124">Para obtener más información sobre cómo modificar el enlace de puerto para el servicio Web de transacciones pendientes de código auxiliar, consulte [cómo instalar las versiones de adaptador de la solución orientada a servicios y en línea](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="f00b1-124">For more information about how to modify the port binding for the stub Pending Transactions Web service, see [How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md).</span></span>  
  
- <span data-ttu-id="f00b1-125">Se requiere Host Integration Server para conectarse al gran sistema.</span><span class="sxs-lookup"><span data-stu-id="f00b1-125">Host Integration Server is required to connect to the mainframe.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f00b1-126">Host Integration Server se incluye como parte de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f00b1-126">Host Integration Server is included as part of BizTalk Server.</span></span>  
  
- <span data-ttu-id="f00b1-127">Un servidor Web configurado con un certificado para realizar conexiones HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f00b1-127">Web server configured with a certificate for HTTPS connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00b1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f00b1-128">See Also</span></span>  
 <span data-ttu-id="f00b1-129">[Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="f00b1-129">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="f00b1-130">[Solución orientada a servicios de instalación de las versiones de adaptador del servicio y en línea](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="f00b1-130">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="f00b1-131">[Cómo ejecutar el servicio de la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="f00b1-131">[How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="f00b1-132">Configurar el equipo del desarrollador para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="f00b1-132">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)