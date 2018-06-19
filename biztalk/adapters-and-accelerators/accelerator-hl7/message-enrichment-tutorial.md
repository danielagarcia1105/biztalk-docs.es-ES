---
title: Tutorial de enriquecimiento de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial
- message enrichment tutorial, about the tutorial
- messages, tutorial
- tutorials, message enrichment tutorial
ms.assetid: 4ffb047f-457a-4a80-b7ec-4b61ae16f35f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532fc0e8a9aeefbc35a892277c68be8d640b5588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205236"
---
# <a name="message-enrichment-tutorial"></a><span data-ttu-id="c671f-102">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="c671f-102">Message Enrichment Tutorial</span></span>
<span data-ttu-id="c671f-103">Este tutorial proporciona procedimientos paso a paso para usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para resolver un problema empresarial determinado: el problema de enriquecimiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c671f-103">This tutorial provides step-by-step procedures for using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to solve a particular business problem: the message enrichment problem.</span></span> <span data-ttu-id="c671f-104">El tutorial de enriquecimiento de mensajes describe una situación en la que se deben agregar a, o enriquecer, un mensaje que no es compatible con HL7 o está incompleta.</span><span class="sxs-lookup"><span data-stu-id="c671f-104">The message enrichment tutorial describes a situation in which you have to add to, or enrich, a message that is not HL7-compliant and/or is incomplete.</span></span> <span data-ttu-id="c671f-105">Esto puede ocurrir con una aplicación, como una aplicación de registro del paciente, o puede producirse cuando se rellena un mensaje con datos XML de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c671f-105">This can occur with an application, such as a patient registration application, or it can occur when you are populating a message with XML data from [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c671f-106">En este tutorial, capturar los mensajes con BTAHL7 y proporcionar los datos que faltan, por ejemplo, desde una base de datos de registros de pacientes.</span><span class="sxs-lookup"><span data-stu-id="c671f-106">In this tutorial, you capture the messages with BTAHL7, and provide any missing data, for example, from a patient records database.</span></span> <span data-ttu-id="c671f-107">A continuación, convertir el mensaje y enviarlo a un laboratorio, seguro o cualquier aplicación heredado línea de negocio (LOB) usa el adaptador MLLP (protocolo mínimos de nivel inferior).</span><span class="sxs-lookup"><span data-stu-id="c671f-107">You then convert the message and send it to a laboratory, insurance, or any legacy line-of-business (LOB) application using the MLLP (Minimal Lower Layer Protocol) adapter.</span></span>  
  
 <span data-ttu-id="c671f-108">En este tutorial, utilice una aplicación de cliente (WSClient.exe) del servicio Web para enviar un mensaje con formato XML, en este caso, un evento de desencadenador "timbre" registrar paciente, a través del adaptador SOAP para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] con BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="c671f-108">In this tutorial, you use a Web service client (WSClient.exe) application to send an XML-formatted message, in this case a "doorbell" Register Patient trigger event, through the SOAP adapter to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] with BTAHL7.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c671f-109">recibe el mensaje SOAP en el puerto de recepción y las rutas que publica el mensaje a una orquestación como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="c671f-109"> receives the message in a SOAP receive port, and routes the message to an orchestration published as a Web service.</span></span> <span data-ttu-id="c671f-110">El mensaje XML contiene un nombre del paciente y el número del seguro social.</span><span class="sxs-lookup"><span data-stu-id="c671f-110">The XML message contains a patient name and social security number.</span></span> <span data-ttu-id="c671f-111">Aumentar el mensaje y usar los esquemas, un mapa y una transformación para convertir el mensaje en formato de HL7.</span><span class="sxs-lookup"><span data-stu-id="c671f-111">You augment the message, and use schemas, a map, and a transform to convert the message into HL7 format.</span></span> <span data-ttu-id="c671f-112">A continuación, se envía a través de un adaptador MLLP para el laboratorio, seguro, o de las aplicaciones LOB.</span><span class="sxs-lookup"><span data-stu-id="c671f-112">You will then send it through an MLLP adapter to the laboratory, insurance, or LOB application.</span></span>  
  
 <span data-ttu-id="c671f-113">En la siguiente ilustración muestra el flujo de proceso del tutorial.</span><span class="sxs-lookup"><span data-stu-id="c671f-113">The following figure shows the process flow of the tutorial.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")  
  
> [!NOTE]
>  <span data-ttu-id="c671f-114">Este tutorial requiere Windows Server Standard, Enterprise, Datacenter o Web Edition y una instalación de BTAHL7 personalizada que incluye la MLLP herramientas de prueba.</span><span class="sxs-lookup"><span data-stu-id="c671f-114">This tutorial requires Windows Server Standard, Enterprise, Datacenter, or Web Edition, and a custom BTAHL7 installation that includes the MLLP test tools.</span></span> <span data-ttu-id="c671f-115">Además, debe estar familiarizado con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] desarrollo en [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] y la información que se encuentra en [obtener información sobre el Acelerador para HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span><span class="sxs-lookup"><span data-stu-id="c671f-115">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and the information found in [learn about the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c671f-116">Puede evitar errores al anular la implementación de ensamblados, detener puertos de envío, y deshabilitar ubicaciones de recepción que utilizan en los tutoriales anteriores.</span><span class="sxs-lookup"><span data-stu-id="c671f-116">You can avoid errors by undeploying assemblies, stopping send ports, and disabling receive locations that you used in previous tutorials.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c671f-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c671f-117">In this section</span></span>  
  
-   [<span data-ttu-id="c671f-118">Paso 1: Configurar la identidad del grupo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c671f-118">Step 1: Configure Application Pool Identity</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [<span data-ttu-id="c671f-119">Paso 2: Crear un nuevo proyecto</span><span class="sxs-lookup"><span data-stu-id="c671f-119">Step 2: Create a New Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [<span data-ttu-id="c671f-120">Paso 3: Asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="c671f-120">Step 3: Assign a Strong Name to the Assembly</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [<span data-ttu-id="c671f-121">Paso 4: Crear los esquemas</span><span class="sxs-lookup"><span data-stu-id="c671f-121">Step 4: Create the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [<span data-ttu-id="c671f-122">Paso 5: Promocionar las propiedades de esquema</span><span class="sxs-lookup"><span data-stu-id="c671f-122">Step 5: Promote Schema Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [<span data-ttu-id="c671f-123">Paso 6: Validar los esquemas</span><span class="sxs-lookup"><span data-stu-id="c671f-123">Step 6: Validate the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [<span data-ttu-id="c671f-124">Paso 7: Firmar y compilar los proyectos</span><span class="sxs-lookup"><span data-stu-id="c671f-124">Step 7: Sign and Build the Projects</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [<span data-ttu-id="c671f-125">Paso 8: Crear un mapa con el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c671f-125">Step 8: Create a Map with BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [<span data-ttu-id="c671f-126">Paso 9: Validar y compilar el proyecto de mapa</span><span class="sxs-lookup"><span data-stu-id="c671f-126">Step 9: Validate and Build the Map Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [<span data-ttu-id="c671f-127">Paso 10: Crear una orquestación</span><span class="sxs-lookup"><span data-stu-id="c671f-127">Step 10: Create an Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [<span data-ttu-id="c671f-128">Paso 11: Crear Variables de orquestación</span><span class="sxs-lookup"><span data-stu-id="c671f-128">Step 11: Create Orchestration Variables</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [<span data-ttu-id="c671f-129">Paso 12: Configurar formas de orquestación</span><span class="sxs-lookup"><span data-stu-id="c671f-129">Step 12: Configure Orchestration Shapes</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [<span data-ttu-id="c671f-130">Paso 13: Crear y configurar puertos</span><span class="sxs-lookup"><span data-stu-id="c671f-130">Step 13: Create and Configure Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [<span data-ttu-id="c671f-131">Paso 14: Publicar la orquestación como servicio Web</span><span class="sxs-lookup"><span data-stu-id="c671f-131">Step 14: Publish the Orchestration as a Web Service</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="c671f-132">Paso 15: Configurar el envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="c671f-132">Step 15: Configure the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="c671f-133">Paso 16: Iniciar la orquestación</span><span class="sxs-lookup"><span data-stu-id="c671f-133">Step 16: Start the Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [<span data-ttu-id="c671f-134">Paso 17: Crear la aplicación WSClient</span><span class="sxs-lookup"><span data-stu-id="c671f-134">Step 17: Create the WSClient Application</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [<span data-ttu-id="c671f-135">Paso 18: Probar la nueva solución de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="c671f-135">Step 18: Test Your New Message Enrichment Solution</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)