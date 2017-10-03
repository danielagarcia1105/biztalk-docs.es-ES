---
title: Limitaciones y los requisitos de servicio de mensajes TIBCO Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption
- messages, compression
- EMS limitations
- message compression
- API, adding to GAC
- global assembly cache, adding API
- GAC, adding TIBCO EMS API
- system requirements
- TIBCO.EMS.dll
- EMS requirements
- messages, encryption
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81e49f4a74cce4414fd9d0b069a382d9facb03d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a><span data-ttu-id="3f1c1-102">Requisitos y limitaciones de TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="3f1c1-102">TIBCO Enterprise Message Service Requirements and Limitations</span></span>
## <a name="system-requirements"></a><span data-ttu-id="3f1c1-103">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="3f1c1-103">System Requirements</span></span>  
 <span data-ttu-id="3f1c1-104">El adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service es compatible con TIBCO Enterprise Message Service (EMS) versión 4.2.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service supports TIBCO Enterprise Message Service (EMS) version 4.2.</span></span> <span data-ttu-id="3f1c1-105">Con TIBCO EMS versión 4.2 se incluye un SDK de cliente (que usa la API TIBCO EMS C#).</span><span class="sxs-lookup"><span data-stu-id="3f1c1-105">Included with TIBCO EMS version 4.2 is a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="3f1c1-106">El adaptador de BizTalk para TIBCO EMS usa esta API para comunicarse con TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-106">BizTalk Adapter for TIBCO EMS uses this API to communicate with TIBCO EMS.</span></span>  
  
## <a name="adding-the-api-to-the-gac"></a><span data-ttu-id="3f1c1-107">Adición de la API a la memoria GAC</span><span class="sxs-lookup"><span data-stu-id="3f1c1-107">Adding the API to the GAC</span></span>  
 <span data-ttu-id="3f1c1-108">El adaptador de BizTalk para TIBCO EMS requiere que la API de TIBCO EMS C#, TIBCO.EMS.dll, se agregue a la memoria caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="3f1c1-108">BizTalk Adapter for TIBCO EMS requires the TIBCO EMS C# API, TIBCO.EMS.dll, to be added to the global assembly cache (GAC).</span></span> <span data-ttu-id="3f1c1-109">El adaptador desencadena una excepción y registra un mensaje adecuado si este ensamblado no está instalado.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-109">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
#### <a name="to-add-the-tibco-ems-c-api-to-the-gac"></a><span data-ttu-id="3f1c1-110">Para agregar la API TIBCO EMS C# a la memoria GAC</span><span class="sxs-lookup"><span data-stu-id="3f1c1-110">To add the TIBCO EMS C# API to the GAC</span></span>  
  
1.  <span data-ttu-id="3f1c1-111">Copie la API de TIBCO EMS C# en el equipo que tenga [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-111">Copy the TIBCO EMS C#API to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span>  
  
2.  <span data-ttu-id="3f1c1-112">Cambie los directorios a la ubicación del archivo de la API de C#, TIBCO.EMS.DLL.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-112">Change directories to the location of the C# API file, TIBCO.EMS.DLL.</span></span>  
  
     <span data-ttu-id="3f1c1-113">En la instalación predeterminada, la ruta de acceso a esta DLL es c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-113">In the default installation, the path to this DLL is c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.</span></span>  
  
3.  <span data-ttu-id="3f1c1-114">En un símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="3f1c1-114">In a command prompt, type:</span></span>  
  
     `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
     <span data-ttu-id="3f1c1-115">El archivo TIBCO.EMS.dll ahora muestra la memoria GAC.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-115">The TIBCO.EMS.dll now shows the GAC.</span></span>  
  
     <span data-ttu-id="3f1c1-116">Para ver la lista GAC, en el Panel de Control, abra **herramientas administrativas**, abra **Microsoft .NET Framework X.XConfiguration**y, a continuación, haga clic en **caché de ensamblados**.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-116">To view the GAC list, in Control Panel, open **Administrative Tools**, open **Microsoft .NET Framework X.XConfiguration**, and then click **Assembly Cache**.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="3f1c1-117">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="3f1c1-117">Limitations</span></span>  
 <span data-ttu-id="3f1c1-118">El adaptador de BizTalk para TIBCO Enterprise Message Service usa TIBCO.EMS.dll para comunicarse con TIBCO Enterprise Message Service.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-118">BizTalk Adapter for TIBCO Enterprise Message Service uses TIBCO.EMS.dll to communicate with TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="3f1c1-119">Cuando se usa la API TIBCO EMS C#, se deben tener en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="3f1c1-119">You should consider the following limitations when you use the TIBCO EMS C# API:</span></span>  
  
-   <span data-ttu-id="3f1c1-120">La compresión de mensajes, que permite al cliente de TIBCO EMS enviar a EMS mensajes de forma comprimida, no se encuentra disponible con la API de C#.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-120">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available with the C# API.</span></span>  
  
-   <span data-ttu-id="3f1c1-121">El cifrado de mensajes entre el adaptador y el servidor no se encuentra disponible con la API de C#.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-121">Encryption of messages between the adapter and the server is not available with the C# API.</span></span> <span data-ttu-id="3f1c1-122">La API de C# no permite el cifrado de SSL mediante las bibliotecas OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-122">The C# API does not allow for SSL encryption using the OpenSSL libraries.</span></span>  
  
-   <span data-ttu-id="3f1c1-123">La API de C# no es compatible con la API de administración para EMS.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-123">The C# API does not support the Administration API for EMS.</span></span>  
  
-   <span data-ttu-id="3f1c1-124">No se pueden enviar ni recibir mensajes de más de 50 MB mediante el adaptador de BizTalk TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-124">Messages greater than 50MB in size cannot be sent or received using the BizTalk TIBCO EMS adapter.</span></span> <span data-ttu-id="3f1c1-125">Por encima de este tamaño, el entorno experimenta excepciones System.OutOfMemoryException.</span><span class="sxs-lookup"><span data-stu-id="3f1c1-125">Beyond this size, the environment experiences System.OutOfMemoryException exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1c1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f1c1-126">See Also</span></span>  
 [<span data-ttu-id="3f1c1-127">Planeamiento y arquitectura</span><span class="sxs-lookup"><span data-stu-id="3f1c1-127">Planning and Architecture</span></span>](../core/planning-and-architecture16.md)