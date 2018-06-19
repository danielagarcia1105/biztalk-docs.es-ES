---
title: 'Tutorial 3: Migrar una SAP enviar IDOC proyecto de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52f8bc638d1adefe952ce055542706d11e0ca61f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217044"
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a><span data-ttu-id="4a43f-102">Tutorial 3: Migrar un proyecto de BizTalk SAP IDOC de envío</span><span class="sxs-lookup"><span data-stu-id="4a43f-102">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>
<span data-ttu-id="4a43f-103">La versión anterior del adaptador SAP que se incluye con Microsoft BizTalk Server difiere basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en muchos aspectos, como:</span><span class="sxs-lookup"><span data-stu-id="4a43f-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="4a43f-104">La experiencia en tiempo de diseño de creación de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4a43f-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="4a43f-105">La experiencia de recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4a43f-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="4a43f-106">Nombre de archivo de esquema y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4a43f-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="4a43f-107">Asignaciones de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="4a43f-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="4a43f-108">Las operaciones que pueden realizarse usando el adaptador.</span><span class="sxs-lookup"><span data-stu-id="4a43f-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="4a43f-109">Configuración del puerto físico en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4a43f-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="4a43f-110">Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante la versión anterior del adaptador SAP](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span><span class="sxs-lookup"><span data-stu-id="4a43f-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
 <span data-ttu-id="4a43f-111">Sin embargo, puede realizar cambios en el proyecto de BizTalk creado con la versión anterior del adaptador y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a43f-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="4a43f-112">Este tutorial proporciona instrucciones sobre los cambios que se debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.</span><span class="sxs-lookup"><span data-stu-id="4a43f-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a43f-113">En este tutorial, por brevedad, la versión anterior del adaptador SAP se conocerán como adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="4a43f-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="4a43f-114">De forma similar, un proyecto de BizTalk que usa el adaptador SAP vPrev se conocerán como proyecto de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="4a43f-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="4a43f-115">Ejemplo usado para el Tutorial</span><span class="sxs-lookup"><span data-stu-id="4a43f-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="4a43f-116">Este tutorial se basa en un ejemplo (SendIDOC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que envía un IDOC a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a43f-116">This tutorial is based upon a sample (SendIDOC_Migration) that demonstrates how to migrate a vPrev BizTalk project that sends an IDOC to an SAP system.</span></span> <span data-ttu-id="4a43f-117">El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a43f-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="4a43f-118">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4a43f-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a43f-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4a43f-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="4a43f-120">Debe tener un proyecto de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="4a43f-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="4a43f-121">Este tutorial consiste en un proyecto de BizTalk que envía un IDOC BOMDOC a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a43f-121">This tutorial involves a BizTalk project that sends a BOMDOC IDOC to an SAP system.</span></span>  
  
-   <span data-ttu-id="4a43f-122">Debe tener un archivo sin formato BOMDOC IDOC para enviar al sistema SAP mediante el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="4a43f-122">You must have a flat-file BOMDOC IDOC to send to the SAP system using the vPrev SAP adapter.</span></span> <span data-ttu-id="4a43f-123">El ejemplo que se proporciona para este tutorial contiene este IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="4a43f-123">The sample provided for this tutorial contains this flat-file IDOC.</span></span>  
  
-   [<span data-ttu-id="4a43f-124">Crear archivo de clave de nombre seguro y obtenga información acerca de las herramientas</span><span class="sxs-lookup"><span data-stu-id="4a43f-124">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="4a43f-125">Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="4a43f-125">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="4a43f-126">Los componentes claves de un proyecto de BizTalk vPrev para enviar un IDOC son:</span><span class="sxs-lookup"><span data-stu-id="4a43f-126">The key constituents of a vPrev BizTalk project to send an IDOC are:</span></span>  
  
-   <span data-ttu-id="4a43f-127">**Orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="4a43f-127">**BizTalk orchestration**.</span></span> <span data-ttu-id="4a43f-128">Se trata de una orquestación sencilla que toma un IDOC de archivo sin formato desde una ubicación de archivo y envía el IDOC al sistema SAP mediante SAP puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4a43f-128">This is a simple orchestration that picks a flat-file IDOC from a file location and sends the IDOC to the SAP system using an SAP send port.</span></span> <span data-ttu-id="4a43f-129">El proyecto de BizTalk contiene un desensamblador de archivos sin formato para convertir el IDOC de archivo sin formato en un XML, por lo que se puede utilizar en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="4a43f-129">The BizTalk project contains a flat-file disassembler to convert the flat-file IDOC to an XML, so that it can be used in an orchestration.</span></span> <span data-ttu-id="4a43f-130">Antes de que el puerto de envío de SAP de vPrev consume el IDOC XML, se convierte en un IDOC de archivo sin formato mediante un ensamblador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="4a43f-130">Before the XML IDOC is consumed by the vPrev SAP send port, it is converted back into a flat-file IDOC using a flat-file assembler.</span></span>  
  
-   <span data-ttu-id="4a43f-131">**Esquema para el IDOC que desee enviar al sistema SAP**.</span><span class="sxs-lookup"><span data-stu-id="4a43f-131">**Schema for the IDOC you want to send to the SAP system**.</span></span> <span data-ttu-id="4a43f-132">Para este tutorial, tiene un proyecto de BizTalk que envía BOMDOC01 IDOC al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a43f-132">For this tutorial, you take a BizTalk project that sends BOMDOC01 IDOC to the SAP system.</span></span> <span data-ttu-id="4a43f-133">El esquema generado para el IDOC es BOMDOC01.xsd.</span><span class="sxs-lookup"><span data-stu-id="4a43f-133">The schema generated for the IDOC is BOMDOC01.xsd.</span></span> <span data-ttu-id="4a43f-134">Este esquema se genera con un adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="4a43f-134">This schema is generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="4a43f-135">**El IDOC de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="4a43f-135">**The flat-file IDOC**.</span></span> <span data-ttu-id="4a43f-136">Se trata de la que se envía al sistema SAP IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="4a43f-136">This is the flat-file IDOC that is sent to the SAP system.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="4a43f-137">Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="4a43f-137">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="4a43f-138">El objetivo de este tutorial de migración es que le permite enviar un IDOC de archivo sin formato a un sistema SAP mediante un puerto de envío WCF-Custom en lugar del puerto de envío para el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="4a43f-138">The goal of this migration tutorial is to enable you to send a flat-file IDOC to an SAP system using a WCF-Custom send port instead of the send port for the vPrev SAP adapter.</span></span> <span data-ttu-id="4a43f-139">Antes de comprender qué configuración es necesaria para el puerto de envío WCF-Custom, primero debe entender qué puertos físicos son necesarios para la orquestación de IDOC vPrev envío:</span><span class="sxs-lookup"><span data-stu-id="4a43f-139">Before understanding what settings are required for the WCF-Custom send port, you must first understand what physical ports are required for the vPrev send IDOC orchestration:</span></span>  
  
-   <span data-ttu-id="4a43f-140">Un archivo de puerto de recepción que recoge el IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="4a43f-140">A file receive port that picks the flat-file IDOC.</span></span> <span data-ttu-id="4a43f-141">Este puerto utiliza la canalización de desensamblador de archivos sin formato, disponible en la aplicación de BizTalk, para convertir el archivo sin formato en un XML que se ajusta al esquema (BOMDOC01.xsd) generado con el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="4a43f-141">This port uses the flat-file disassembler pipeline, available in the BizTalk application, to convert the flat-file into an XML that conforms to the schema (BOMDOC01.xsd) generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="4a43f-142">Un SAP vPrev puerto de envío que envía el IDOC de archivo sin formato al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="4a43f-142">A vPrev SAP send port that sends the flat-file IDOC to the SAP system.</span></span> <span data-ttu-id="4a43f-143">Antes de enviar el archivo sin formato, el puerto utiliza el ensamblador de archivo sin formato para convertir el XML IDOC en un IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="4a43f-143">Before sending the flat-file, the port uses the flat-file assembler to convert the XML IDOC into a flat-file IDOC.</span></span>  
  
 <span data-ttu-id="4a43f-144">Para migrar el proyecto de BizTalk vPrev existente, no es necesario cambiar el archivo de puerto de recepción que recoge el IDOC de archivo sin formato y convierte el IDOC de archivo sin formato a XML mediante un desensamblador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="4a43f-144">To migrate your existing vPrev BizTalk project, you do not need to change the file receive port that picks the flat-file IDOC and converts the flat-file IDOC to XML using a flat-file disassembler.</span></span> <span data-ttu-id="4a43f-145">Solo debe configurar un puerto de envío WCF-Custom con la configuración de la configuración correcta.</span><span class="sxs-lookup"><span data-stu-id="4a43f-145">You only need to configure a new WCF-Custom send port with the right configuration settings.</span></span> <span data-ttu-id="4a43f-146">Este tutorial muestra cómo configurar el puerto de envío WCF-Custom para enviar los IDOC a un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a43f-146">This tutorial demonstrates how to configure the WCF-Custom send port to send IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a43f-147">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4a43f-147">In This Section</span></span>  
  
-   [<span data-ttu-id="4a43f-148">Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para enviar un IDOC</span><span class="sxs-lookup"><span data-stu-id="4a43f-148">Step 1: Build and Deploy the vPrev BizTalk Project for Sending an IDOC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [<span data-ttu-id="4a43f-149">Paso 2: Configurar un puerto de envío unidireccional de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="4a43f-149">Step 2: Configure a WCF-Custom One-way Send Port</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [<span data-ttu-id="4a43f-150">Paso 3: Probar la aplicación migrada</span><span class="sxs-lookup"><span data-stu-id="4a43f-150">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a43f-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a43f-151">See Also</span></span>  
 [<span data-ttu-id="4a43f-152">Tutoriales del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="4a43f-152">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)