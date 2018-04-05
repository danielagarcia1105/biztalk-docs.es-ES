---
title: Adaptador de FTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FTP adapters
ms.assetid: 878dc0b0-d1d8-405a-a697-654dd18ba08e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc72b5166f8971392b41f275338bde593d325af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ftp-adapter"></a><span data-ttu-id="9a911-102">Adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="9a911-102">FTP Adapter</span></span>
<span data-ttu-id="9a911-103">El adaptador de FTP intercambia datos entre un servidor FTP y Microsoft BizTalk Server, y permite la integración de datos imprescindibles almacenados en una gran variedad de plataformas con aplicaciones de líneas de negocios.</span><span class="sxs-lookup"><span data-stu-id="9a911-103">The FTP adapter exchanges data between an FTP server and Microsoft BizTalk Server, and allows for the integration of vital data stored on a variety of platforms with line-of-business applications.</span></span> <span data-ttu-id="9a911-104">El adaptador se puede conectar con el servidor FTP a través de un servidor proxy SOCKS4 o SOCKS5.</span><span class="sxs-lookup"><span data-stu-id="9a911-104">The adapter can connect to the FTP server via SOCKS4 or SOCKS5 proxy server.</span></span>  
  
 <span data-ttu-id="9a911-105">El adaptador de FTP puede transferir un gran número de archivos desde un servidor FTP a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9a911-105">The FTP adapter can transfer a large number of files from an FTP server to BizTalk Server.</span></span> <span data-ttu-id="9a911-106">También puede transferir archivos como parte de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="9a911-106">It can also transfer files as part of an orchestration.</span></span>  
  
 <span data-ttu-id="9a911-107">El adaptador de FTP consta de dos adaptadores: un adaptador de recepción y un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="9a911-107">The FTP adapter consists of two adapters — a receive adapter and a send adapter.</span></span>  

<span data-ttu-id="9a911-108">En esta sección se describen los adaptadores de recepción y envío FTP, y se ofrece información de seguridad y de prácticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="9a911-108">This section describes the FTP receive and send adapters, as well as security and best-practice information.</span></span>  
  
 ## <a name="receive-adapter"></a><span data-ttu-id="9a911-109">Adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="9a911-109">Receive adapter</span></span>  
  
 <span data-ttu-id="9a911-110">El adaptador de recepción FTP permite mover datos desde un servidor FTP a un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a911-110">The FTP receive adapter enables you to move data from an FTP server to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="9a911-111">Las características clave incluyen:</span><span class="sxs-lookup"><span data-stu-id="9a911-111">Key features include:</span></span>  
  
-   <span data-ttu-id="9a911-112">Extracción de archivos del servidor FTP a petición.</span><span class="sxs-lookup"><span data-stu-id="9a911-112">Pulling files from the FTP server on demand</span></span>  
  
-   <span data-ttu-id="9a911-113">Ejecución de sondeos basados en una programación configurable</span><span class="sxs-lookup"><span data-stu-id="9a911-113">Running polls based on a configurable schedule</span></span>  
  
-   <span data-ttu-id="9a911-114">Realización de sondeos del servidor FTP y envío de datos directamente al servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a911-114">Polling the FTP server and sending data directly to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="9a911-115">Especificación del servidor FTP como dirección IP, puerto, contraseña y nombre de host.</span><span class="sxs-lookup"><span data-stu-id="9a911-115">Specifying the FTP server as an IP address, port, password, and host name</span></span>  
  
-   <span data-ttu-id="9a911-116">Garantiza la entrega de archivos</span><span class="sxs-lookup"><span data-stu-id="9a911-116">Guaranteed file delivery</span></span>  
  
     <span data-ttu-id="9a911-117">El adaptador de recepción FTP también trabaja con la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el explorador de BizTalk para configurar y administrar cada función de recepción, que se compone de los siguientes elementos de configuración:</span><span class="sxs-lookup"><span data-stu-id="9a911-117">The FTP receive adapter also works with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and BizTalk Explorer to configure and administer each receive function, which is composed of the following configuration items:</span></span>  
  
-   <span data-ttu-id="9a911-118">Intervalo de sondeo para ejecutar un comando FTP (por ejemplo, 60 minutos).</span><span class="sxs-lookup"><span data-stu-id="9a911-118">Poll interval to run an FTP command (for example, 60 minutes)</span></span>  
  
-   <span data-ttu-id="9a911-119">Información con la que se enruta el documento a una ubicación de recepción o a un puerto de envío de BizTalk específico.</span><span class="sxs-lookup"><span data-stu-id="9a911-119">Information with which to route the document to a specific BizTalk send port or receive location</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a911-120">El adaptador de recepción FTP no admite la recepción de archivos desde un conjunto de datos con particiones.</span><span class="sxs-lookup"><span data-stu-id="9a911-120">The FTP receive adapter does not support receiving files from a partitioned data set.</span></span>  
  
## <a name="send-adapter"></a><span data-ttu-id="9a911-121">Adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="9a911-121">Send adapter</span></span>  
  
 <span data-ttu-id="9a911-122">El adaptador de envío FTP permite mover datos desde un servidor FTP a un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a911-122">The FTP send adapter enables you to move data from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to an FTP server.</span></span> <span data-ttu-id="9a911-123">Las características clave incluyen:</span><span class="sxs-lookup"><span data-stu-id="9a911-123">Key features include:</span></span>  
  
-   <span data-ttu-id="9a911-124">Capacidad para efectuar envíos a petición</span><span class="sxs-lookup"><span data-stu-id="9a911-124">Ability to run sends on demand</span></span>  
  
-   <span data-ttu-id="9a911-125">Entrega garantizada</span><span class="sxs-lookup"><span data-stu-id="9a911-125">Guaranteed delivery</span></span>  
  
## <a name="supported-platforms"></a><span data-ttu-id="9a911-126">Plataformas compatibles</span><span class="sxs-lookup"><span data-stu-id="9a911-126">Supported platforms</span></span>  
<span data-ttu-id="9a911-127">Información de acceso almacenada en un servidor FTP en cualquiera de las siguientes plataformas:</span><span class="sxs-lookup"><span data-stu-id="9a911-127">Access information stored in an FTP server on any of the following platforms:</span></span>  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="9a911-128"> 2016</span><span class="sxs-lookup"><span data-stu-id="9a911-128"> 2016</span></span>

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="9a911-129"> R2</span><span class="sxs-lookup"><span data-stu-id="9a911-129"> R2</span></span>
  
-   [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
-   [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="9a911-130"> 2008</span><span class="sxs-lookup"><span data-stu-id="9a911-130"> 2008</span></span>  
  
-   [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="9a911-131"> 2000 Service Pack 3 (SP3) y posterior</span><span class="sxs-lookup"><span data-stu-id="9a911-131"> 2000 Service Pack 3 (SP3) and later</span></span>  
  
-   <span data-ttu-id="9a911-132">Sun Solaris 9.0</span><span class="sxs-lookup"><span data-stu-id="9a911-132">Sun Solaris 9.0</span></span>  
  
-   <span data-ttu-id="9a911-133">HP-UX</span><span class="sxs-lookup"><span data-stu-id="9a911-133">HP-UX</span></span>  
  
-   <span data-ttu-id="9a911-134">LINUX (Redhat 7.x)</span><span class="sxs-lookup"><span data-stu-id="9a911-134">LINUX (Redhat 7.x)</span></span>  
  
-   <span data-ttu-id="9a911-135">IBM z/OS v1.9 (MVS)</span><span class="sxs-lookup"><span data-stu-id="9a911-135">IBM z/OS v1.9 (MVS)</span></span>  
  
-   <span data-ttu-id="9a911-136">IBM O/S 390 que ejecuta MVS</span><span class="sxs-lookup"><span data-stu-id="9a911-136">IBM O/S 390 running MVS</span></span>  
  
-   <span data-ttu-id="9a911-137">AS/400 OS/400 V5R1</span><span class="sxs-lookup"><span data-stu-id="9a911-137">AS/400 OS/400 V5R1</span></span>  
  
-   <span data-ttu-id="9a911-138">i5/OS V5R4 (AS400)</span><span class="sxs-lookup"><span data-stu-id="9a911-138">i5/OS V5R4 (AS400)</span></span>  
  
-   <span data-ttu-id="9a911-139">i5/OS V6R1 (AS400)</span><span class="sxs-lookup"><span data-stu-id="9a911-139">i5/OS V6R1 (AS400)</span></span>  
  
-   <span data-ttu-id="9a911-140">GXS ICS</span><span class="sxs-lookup"><span data-stu-id="9a911-140">GXS ICS</span></span>  
  
-   <span data-ttu-id="9a911-141">AIX</span><span class="sxs-lookup"><span data-stu-id="9a911-141">AIX</span></span>  
  
 <span data-ttu-id="9a911-142">Se admiten todos los Service Packs, a menos que se indique específicamente.</span><span class="sxs-lookup"><span data-stu-id="9a911-142">All services packs are supported, unless the service pack is specifically listed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a911-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9a911-143">In This Section</span></span>  
  
[<span data-ttu-id="9a911-144">Prácticas recomendadas y recomendaciones para el adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="9a911-144">Best practices and recommendations for the FTP Adapter</span></span>](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[<span data-ttu-id="9a911-145">Configurar el adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="9a911-145">Configuring the FTP adapter</span></span>](../core/configuring-the-ftp-adapter.md)  

[<span data-ttu-id="9a911-146">Propiedades y esquema de propiedades del adaptador FTP</span><span class="sxs-lookup"><span data-stu-id="9a911-146">FTP Adapter Property Schema and Properties</span></span>](../core/ftp-adapter-property-schema-and-properties.md)