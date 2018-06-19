---
title: 'Tutorial 2: Migrar un proyecto de BizTalk RFC de SAP | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80b5d53904b96267b1877310aa3480ce34a1bedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218100"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a><span data-ttu-id="734f9-102">Tutorial 2: Migrar un proyecto de BizTalk RFC de SAP</span><span class="sxs-lookup"><span data-stu-id="734f9-102">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>
<span data-ttu-id="734f9-103">La versión anterior del adaptador SAP que se incluye con Microsoft BizTalk Server difiere basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en muchos aspectos, como:</span><span class="sxs-lookup"><span data-stu-id="734f9-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="734f9-104">La experiencia en tiempo de diseño de creación de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="734f9-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="734f9-105">La experiencia de recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="734f9-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="734f9-106">Nombre de archivo de esquema y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="734f9-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="734f9-107">Asignaciones de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="734f9-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="734f9-108">Las operaciones que pueden realizarse usando el adaptador.</span><span class="sxs-lookup"><span data-stu-id="734f9-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="734f9-109">Configuración del puerto físico en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="734f9-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="734f9-110">Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante la versión anterior del adaptador SAP](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span><span class="sxs-lookup"><span data-stu-id="734f9-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
 <span data-ttu-id="734f9-111">Sin embargo, puede realizar cambios en el proyecto de BizTalk creado con la versión anterior del adaptador y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="734f9-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="734f9-112">Este tutorial proporciona instrucciones sobre los cambios que se debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.</span><span class="sxs-lookup"><span data-stu-id="734f9-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="734f9-113">En este tutorial, por brevedad, la versión anterior del adaptador SAP se conocerán como adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="734f9-114">De forma similar, un proyecto de BizTalk que usa el adaptador SAP vPrev se conocerán como proyecto de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="734f9-115">Ejemplo usado para el Tutorial</span><span class="sxs-lookup"><span data-stu-id="734f9-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="734f9-116">Este tutorial se basa en un ejemplo (SAP_RFC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que invoca una solicitud de cambio en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="734f9-116">This tutorial is based upon a sample (SAP_RFC_Migration) that demonstrates how to migrate a vPrev BizTalk project that invokes an RFC in an SAP system.</span></span> <span data-ttu-id="734f9-117">El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="734f9-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="734f9-118">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="734f9-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="734f9-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="734f9-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="734f9-120">Debe tener un proyecto de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="734f9-121">Este tutorial consiste en un proyecto de BizTalk que invoca la RFC SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="734f9-121">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span>  
  
-   <span data-ttu-id="734f9-122">Debe tener un mensaje de solicitud para llevar a cabo para invocar la solicitud de cambio de SD_RFC_CUSTOMER_GET con un adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-122">You must have a request message to perform to invoke the SD_RFC_CUSTOMER_GET RFC using the vPrev SAP adapter.</span></span> <span data-ttu-id="734f9-123">El mensaje de solicitud debe ajustarse al esquema de la solicitud de cambio que se genera mediante el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-123">The request message must conform to the schema of the RFC generated using the vPrev SAP adapter.</span></span> <span data-ttu-id="734f9-124">El ejemplo que se proporciona para este tutorial contiene el siguiente mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="734f9-124">The sample provided for this tutorial contains this request message.</span></span>  
  
-   [<span data-ttu-id="734f9-125">Crear archivo de clave de nombre seguro y obtenga información acerca de las herramientas</span><span class="sxs-lookup"><span data-stu-id="734f9-125">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="734f9-126">Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="734f9-126">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="734f9-127">Los componentes claves de un proyecto de BizTalk vPrev para invocar una solicitud de cambio son:</span><span class="sxs-lookup"><span data-stu-id="734f9-127">The key constituents of a vPrev BizTalk project to invoke an RFC are:</span></span>  
  
-   <span data-ttu-id="734f9-128">**Orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="734f9-128">**BizTalk orchestration**.</span></span> <span data-ttu-id="734f9-129">Se trata de una orquestación sencilla que toma los mensajes de solicitud desde una ubicación de archivo, envía el mensaje de solicitud al sistema SAP mediante SAP envío y recepción puerto, recibe la respuesta y lo guarda en otra ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="734f9-129">This is a simple orchestration that picks request messages from a file location, sends the request message to the SAP system using an SAP send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="734f9-130">**Esquema para la solicitud de cambio que desea invocar en el sistema SAP**.</span><span class="sxs-lookup"><span data-stu-id="734f9-130">**Schema for the RFC you want to invoke in the SAP system**.</span></span> <span data-ttu-id="734f9-131">Este tutorial consiste en un proyecto de BizTalk que invoca la RFC SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="734f9-131">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="734f9-132">El esquema generado para la solicitud de cambio es SD_RFC_CUSTOMER_GET__x32003.xsd.</span><span class="sxs-lookup"><span data-stu-id="734f9-132">The schema generated for the RFC is SD_RFC_CUSTOMER_GET__x32003.xsd.</span></span> <span data-ttu-id="734f9-133">Este esquema se genera con un adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-133">This schema is generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="734f9-134">**Mensaje de solicitud**.</span><span class="sxs-lookup"><span data-stu-id="734f9-134">**Request message**.</span></span> <span data-ttu-id="734f9-135">El mensaje de solicitud para invocar la solicitud de cambio de SD_RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="734f9-135">The request message to invoke the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="734f9-136">El esquema del mensaje de solicitud se ajusta al esquema de la solicitud de cambio de SD_RFC_CUSTOMER_GET como obtenidas por el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-136">The schema of the request message conforms to the schema of the SD_RFC_CUSTOMER_GET RFC as surfaced by the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="734f9-137">Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="734f9-137">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="734f9-138">El objetivo de este tutorial de migración es que le permite enviar un mensaje de solicitud, que se ajusta al esquema generado por el adaptador SAP vPrev, utilizando un puerto personalizado de WCF que sólo puede procesar mensajes sean conformes a las basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="734f9-138">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev SAP adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="734f9-139">Por lo tanto, en resumen, el ejercicio de migración implica configurar el puerto personalizado de WCF para procesar los mensajes que no cumplen basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]del esquema.</span><span class="sxs-lookup"><span data-stu-id="734f9-139">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="734f9-140">Sin embargo, para poder configurar correctamente el puerto de WCF-Custom, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="734f9-140">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="734f9-141">Generar metadatos para la solicitud de cambio de SD_RFC_CUSTOMER_GET mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="734f9-141">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="734f9-142">Asignar el mensaje de solicitud para invocar la solicitud de cambio con un adaptador SAP vPrev a un mensaje de solicitud para invocar la solicitud de cambio con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="734f9-142">Map the request message for invoking the RFC using the vPrev SAP adapter to a request message for invoking the RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="734f9-143">Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] al mensaje de respuesta para el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="734f9-143">Map the response message received using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the response message for the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="734f9-144">Crear un SAP de WCF-Custom envío y recepción de puerto en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="734f9-144">Create a WCF-Custom SAP send-receive port in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="734f9-145">Configurar el puerto de WCF-Custom para utilizar las asignaciones de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="734f9-145">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="734f9-146">En esta sección</span><span class="sxs-lookup"><span data-stu-id="734f9-146">In This Section</span></span>  
  
-   [<span data-ttu-id="734f9-147">Paso 1: Modificar el proyecto de BizTalk vPrev para llamar a una solicitud de cambio</span><span class="sxs-lookup"><span data-stu-id="734f9-147">Step 1: Modify the vPrev BizTalk Project for Invoking an RFC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [<span data-ttu-id="734f9-148">Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="734f9-148">Step 2: Configure the Orchestration in BizTalk Server Administration Console</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [<span data-ttu-id="734f9-149">Paso 3: Probar la aplicación migrada</span><span class="sxs-lookup"><span data-stu-id="734f9-149">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a><span data-ttu-id="734f9-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="734f9-150">See Also</span></span>  
 [<span data-ttu-id="734f9-151">Tutoriales del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="734f9-151">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)