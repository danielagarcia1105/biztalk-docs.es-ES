---
title: 'Tutorial 4: Migración de una SAP recibir IDOC proyecto de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e943c3663767d2b684b0f4657f639d752705b86f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011261"
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a><span data-ttu-id="2aa9b-102">Tutorial 4: Migración de una SAP recibir IDOC proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2aa9b-102">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>
<span data-ttu-id="2aa9b-103">La versión anterior del adaptador SAP que se incluye con Microsoft BizTalk Server difiere basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en muchos aspectos, como:</span><span class="sxs-lookup"><span data-stu-id="2aa9b-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="2aa9b-104">La experiencia en tiempo de diseño de la creación de un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="2aa9b-105">La experiencia de recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="2aa9b-106">Nombre de archivo de esquema y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="2aa9b-107">Asignaciones de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="2aa9b-108">Las operaciones que pueden realizarse mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="2aa9b-109">Configuración de puerto físico en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
  <span data-ttu-id="2aa9b-110">Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante la versión anterior del adaptador SAP](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span><span class="sxs-lookup"><span data-stu-id="2aa9b-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
  <span data-ttu-id="2aa9b-111">Sin embargo, puede realizar cambios en el proyecto de BizTalk creado con la versión anterior del adaptador y que funcione con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aa9b-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="2aa9b-112">Este tutorial proporciona instrucciones sobre los cambios que debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2aa9b-113">En este tutorial, por brevedad, la versión anterior del adaptador de SAP se hará referencia a como adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="2aa9b-114">De forma similar, se hará referencia a un proyecto de BizTalk que usa el adaptador SAP vPrev como proyecto de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="2aa9b-115">Ejemplo usado para el Tutorial</span><span class="sxs-lookup"><span data-stu-id="2aa9b-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="2aa9b-116">En este tutorial se basa en un ejemplo (ReceiveIDOC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que recibe un IDOC de archivo sin formato de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-116">This tutorial is based upon a sample (ReceiveIDOC_Migration) that demonstrates how to migrate a vPrev BizTalk project that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="2aa9b-117">El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aa9b-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="2aa9b-118">Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2aa9b-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2aa9b-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2aa9b-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="2aa9b-120">Debe tener un proyecto de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="2aa9b-121">Este tutorial trata de un proyecto de BizTalk que recibe un IDOC ORDERS03 desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-121">This tutorial involves a BizTalk project that receives an ORDERS03 IDOC from an SAP system.</span></span>  
  
-   [<span data-ttu-id="2aa9b-122">Crear el archivo de clave de nombre seguro y obtener información sobre las herramientas</span><span class="sxs-lookup"><span data-stu-id="2aa9b-122">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="2aa9b-123">Descripción de un proyecto de BizTalk creado con la versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="2aa9b-123">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="2aa9b-124">Los componentes claves de un proyecto de BizTalk vPrev para recibir un IDOC son:</span><span class="sxs-lookup"><span data-stu-id="2aa9b-124">The key constituents of a vPrev BizTalk project to receive an IDOC are:</span></span>  
  
-   <span data-ttu-id="2aa9b-125">**Orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-125">**BizTalk orchestration**.</span></span> <span data-ttu-id="2aa9b-126">Se trata de una sencilla orquestación que consta de una SAP puerto de recepción que recibe un IDOC de archivo sin formato de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-126">This is a simple orchestration that consists of an SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="2aa9b-127">El proyecto de BizTalk contiene un desensamblador de archivo sin formato para convertir el IDOC de archivo sin formato a XML, por lo que se puede usar en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-127">The BizTalk project contains a flat-file disassembler to convert the flat-file IDOC to an XML, so that it can be used in an orchestration.</span></span> <span data-ttu-id="2aa9b-128">Antes de que el IDOC XML se copia en una ubicación de archivo a través de un puerto de archivos, se convierte en un IDOC de archivo sin formato mediante un ensamblador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-128">Before the XML IDOC is copied to a file location through a file port, it is converted back into a flat-file IDOC using a flat-file assembler.</span></span>  
  
-   <span data-ttu-id="2aa9b-129">**Esquema para el IDOC que desee enviar al sistema SAP**.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-129">**Schema for the IDOC you want to send to the SAP system**.</span></span> <span data-ttu-id="2aa9b-130">Este tutorial trata de un proyecto de BizTalk que recibe los IDOC ORDERS03 desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-130">This tutorial involves a BizTalk project that receives ORDERS03 IDOC from the SAP system.</span></span> <span data-ttu-id="2aa9b-131">El esquema generado para el IDOC es ORDERS03.xsd.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-131">The schema generated for the IDOC is ORDERS03.xsd.</span></span> <span data-ttu-id="2aa9b-132">Este esquema se genera mediante el adaptador de SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-132">This schema is generated using the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="2aa9b-133">Cómo migrar un proyecto de BizTalk creado con la versión anterior del adaptador</span><span class="sxs-lookup"><span data-stu-id="2aa9b-133">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="2aa9b-134">El objetivo de este tutorial de migración es para que pueda recibir un IDOC de archivo sin formato de un sistema SAP mediante un puerto de envío WCF-Custom en lugar del puerto de envío para el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-134">The goal of this migration tutorial is to enable you to receive a flat-file IDOC from an SAP system using a WCF-Custom send port instead of the send port for the vPrev SAP adapter.</span></span> <span data-ttu-id="2aa9b-135">Antes de comprender qué configuración es necesaria para el puerto de envío WCF-Custom, debe comprender primero qué puertos físicos son necesarios para la orquestación de IDOC de envío vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-135">Before understanding what settings are required for the WCF-Custom send port, you must first understand what physical ports are required for the vPrev send IDOC orchestration.</span></span>  
  
- <span data-ttu-id="2aa9b-136">Un vPrev SAP puerto de recepción que recibe un IDOC de archivo sin formato de un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-136">A vPrev SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="2aa9b-137">El puerto también lo convierte en un IDOC XML con un desensamblador de archivo sin formato, que está disponible como parte de la aplicación de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-137">The port also converts this to an XML IDOC using a flat-file disassembler, which is available as part of the vPrev BizTalk application.</span></span> <span data-ttu-id="2aa9b-138">El IDOC XML se ajusta al esquema (ORDERS03.xsd) que se han generado mediante el adaptador SAP vPrev.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-138">The XML IDOC conforms to the schema (ORDERS03.xsd) that you generated using the vPrev SAP adapter.</span></span>  
  
- <span data-ttu-id="2aa9b-139">Un puerto de envío de archivo que se copia el IDOC en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-139">A file send port which copies the IDOC to folder.</span></span> <span data-ttu-id="2aa9b-140">Este puerto también usa la canalización de ensamblador de archivo sin formato, disponible en la aplicación de BizTalk para convertir el IDOC XML en un IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-140">This port also uses the flat-file assembler pipeline, available in the BizTalk application, to convert the XML IDOC to a flat-file IDOC.</span></span>  
  
  <span data-ttu-id="2aa9b-141">Para migrar el proyecto de BizTalk vPrev existente, no es necesario cambiar el puerto de envío de archivo que se copia el IDOC de archivo sin formato en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-141">To migrate your existing vPrev BizTalk project, you do not need to change the file send port that copies the flat-file IDOC to a folder.</span></span> <span data-ttu-id="2aa9b-142">Deberá configurar un nuevo puerto con la configuración correcta de recepción WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="2aa9b-142">You only need to configure a new WCF-Custom receive port with the right configuration settings.</span></span> <span data-ttu-id="2aa9b-143">Este tutorial muestra cómo se configura el WCF-Custom puerto de recepción para recibir los IDOC desde un sistema SAP mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aa9b-143">This tutorial demonstrates how to configure the WCF-Custom receive port to receive IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2aa9b-144">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2aa9b-144">In This Section</span></span>  
  
-   [<span data-ttu-id="2aa9b-145">Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para recibir un IDOC</span><span class="sxs-lookup"><span data-stu-id="2aa9b-145">Step 1: Build and Deploy the vPrev BizTalk Project for Receiving an IDOC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [<span data-ttu-id="2aa9b-146">Paso 2: Configurar un puerto de recepción unidireccional personalizado de WCF</span><span class="sxs-lookup"><span data-stu-id="2aa9b-146">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [<span data-ttu-id="2aa9b-147">Paso 3: Probar la aplicación migrada</span><span class="sxs-lookup"><span data-stu-id="2aa9b-147">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a><span data-ttu-id="2aa9b-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aa9b-148">See Also</span></span>  
 [<span data-ttu-id="2aa9b-149">Tutoriales del adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="2aa9b-149">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)