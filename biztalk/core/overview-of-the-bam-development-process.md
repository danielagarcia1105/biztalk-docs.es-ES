---
title: "Información general sobre el proceso de desarrollo de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adfe1e552c0f129df67ec5ea790f8e685b214fe6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-bam-development-process"></a><span data-ttu-id="4605d-102">Información general sobre el proceso de desarrollo con BAM</span><span class="sxs-lookup"><span data-stu-id="4605d-102">Overview of the BAM Development Process</span></span>
<span data-ttu-id="4605d-103">En este tema se describen el proceso de desarrollo, así como las bases de datos y tablas que almacenan los datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-103">This topic describes the development process and the database and tables that store BAM data.</span></span>  
  
## <a name="prerequisites-for-developing-with-bam"></a><span data-ttu-id="4605d-104">Requisitos previos para desarrollar con BAM</span><span class="sxs-lookup"><span data-stu-id="4605d-104">Prerequisites for Developing with BAM</span></span>  
 <span data-ttu-id="4605d-105">Tenga en cuenta los siguientes requisitos previos antes de desarrollar con BAM:</span><span class="sxs-lookup"><span data-stu-id="4605d-105">Note the following prerequisites before you begin developing with BAM:</span></span>  
  
-   <span data-ttu-id="4605d-106">Para instrumentar una aplicación, es preciso tener una actividad implementada.</span><span class="sxs-lookup"><span data-stu-id="4605d-106">To instrument an application you must have an activity deployed.</span></span>  
  
-   <span data-ttu-id="4605d-107">Debe tener derechos DBO en las bases de datos de SQL Server y ser miembro del contexto de seguridad de la función de escritor de eventos de BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-107">You must have DBO rights to the SQL Server databases and be a member of the BAM Event Writer Role security context.</span></span>  
  
-   <span data-ttu-id="4605d-108">Debe usar Microsoft .NET 4 para desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4605d-108">You must use Microsoft .NET 4 to develop your application.</span></span> <span data-ttu-id="4605d-109">Puede usar cualquier lenguaje .NET, aunque recomendamos que use C#.</span><span class="sxs-lookup"><span data-stu-id="4605d-109">You can use any .NET language, although we recommend that you use C#.</span></span>  
  
-   <span data-ttu-id="4605d-110">Debe tener la biblioteca Microsoft.BizTalk.BAM.EventObservation.dll instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4605d-110">You must have the Microsoft.BizTalk.BAM.EventObservation.dll installed on your computer.</span></span> <span data-ttu-id="4605d-111">Puede obtener el archivo DLL de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="4605d-111">You can obtain the DLL in two ways:</span></span>  
  
    -   <span data-ttu-id="4605d-112">Utilice el administrador de configuración de BizTalk Server para instalar las herramientas de BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-112">Use the BizTalk Server Configuration Manager to install the BAM tools.</span></span> <span data-ttu-id="4605d-113">Recomendamos utilizar el administrador de configuración porque coloca las entradas apropiadas en el Registro, lo que facilita las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4605d-113">We recommend that you use the Configuration Manager because it places appropriate entries in the registry that facilitate upgrades.</span></span> <span data-ttu-id="4605d-114">Para obtener más información sobre la configuración de BAM, consulte [configurar herramientas de BAM mediante el Administrador de configuración](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561).</span><span class="sxs-lookup"><span data-stu-id="4605d-114">For more information about configuring BAM, see [Configuring BAM Tools Using the Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561).</span></span>  
  
    -   <span data-ttu-id="4605d-115">Copie el archivo DLL desde un equipo donde ya estén instaladas.</span><span class="sxs-lookup"><span data-stu-id="4605d-115">Copy the DLL from a computer on which they have already been installed.</span></span> <span data-ttu-id="4605d-116">El archivo DLL reside en Microsoft BizTalk Server \<versión > carpeta \Tracking.</span><span class="sxs-lookup"><span data-stu-id="4605d-116">The DLL resides in the Microsoft BizTalk Server \<version>\Tracking folder.</span></span>  
  
## <a name="bam-development-process"></a><span data-ttu-id="4605d-117">Proceso de desarrollo con BAM</span><span class="sxs-lookup"><span data-stu-id="4605d-117">BAM Development Process</span></span>  
 <span data-ttu-id="4605d-118">En la ilustración siguiente se describe el flujo de desarrollo con BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-118">The following figure describes the BAM development flow.</span></span>  
  
 <span data-ttu-id="4605d-119">![Flujo de trabajo de desarrollo de BAM](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span><span class="sxs-lookup"><span data-stu-id="4605d-119">![BAM development work flow](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span></span>  
  
 <span data-ttu-id="4605d-120">En el procedimiento siguiente se enumeran los pasos básicos para desarrollar una solución con BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-120">The following procedure lists the basic steps for developing a solution with BAM.</span></span>  
  
#### <a name="to-develop-a-bam-enabled-solution"></a><span data-ttu-id="4605d-121">Para desarrollar una solución habilitada para BAM</span><span class="sxs-lookup"><span data-stu-id="4605d-121">To develop a BAM-enabled solution</span></span>  
  
1.  <span data-ttu-id="4605d-122">Cree un modelo de observación con el complemento BAM para Excel.</span><span class="sxs-lookup"><span data-stu-id="4605d-122">Create an observation model with the BAM Add-in for Excel.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4605d-123">Ejemplos de los pasos de este procedimiento pueden encontrarse en la API de BAM (ejemplo de BizTalk Server) en [http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968).</span><span class="sxs-lookup"><span data-stu-id="4605d-123">Examples of the steps noted in this procedure can be found in the BAM API (BizTalk Server sample) at [http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968).</span></span>  
  
2.  <span data-ttu-id="4605d-124">Utilice la utilidad de administración de BAM para implementar la actividad en la base de datos de importación principal (BDIP).</span><span class="sxs-lookup"><span data-stu-id="4605d-124">Use the BAM Management utility to deploy the activity to the PID.</span></span>  
  
3.  <span data-ttu-id="4605d-125">Instrumente la aplicación agregando su propio código de EventStream de BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-125">Instrument the application by adding your BAM EventStream code.</span></span>  
  
4.  <span data-ttu-id="4605d-126">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4605d-126">Run the application.</span></span> <span data-ttu-id="4605d-127">Al hacerlo, el código hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4605d-127">When you do this, the code will:</span></span>  
  
    -   <span data-ttu-id="4605d-128">Agregar un registro de marcador de posición a la tabla BAM_\<*nombre de la actividad*> _especifique tabla.</span><span class="sxs-lookup"><span data-stu-id="4605d-128">Add a placeholder record to the BAM_\<*activity name*>_Active table.</span></span>  
  
    -   <span data-ttu-id="4605d-129">Actualizar los elementos de datos del registro.</span><span class="sxs-lookup"><span data-stu-id="4605d-129">Update the data items in the record.</span></span>  
  
    -   <span data-ttu-id="4605d-130">Finalizar la actividad y mover el registro a la tabla BAM_\<*actividad nam*e > tabla _completed.</span><span class="sxs-lookup"><span data-stu-id="4605d-130">End the activity and move the record to the BAM_\<*activity nam*e>_completed table.</span></span>  
  
## <a name="where-bam-data-is-stored"></a><span data-ttu-id="4605d-131">¿Dónde se guardan los datos de BAM?</span><span class="sxs-lookup"><span data-stu-id="4605d-131">Where BAM Data Is Stored</span></span>  
 <span data-ttu-id="4605d-132">BAM proporciona el espacio de nombres EventObservation que contiene las clases EventStream usadas para controlar los eventos de BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-132">BAM provides the EventObservation namespace that contains the EventStream classes that are used to handle BAM events.</span></span>  
  
 <span data-ttu-id="4605d-133">Los datos de seguimiento de BAM se almacenan en la base de datos de importación principal (BDIP) de BAM.</span><span class="sxs-lookup"><span data-stu-id="4605d-133">BAM tracking data is stored in the BAM Primary Import database (PID).</span></span> <span data-ttu-id="4605d-134">Al implementar un modelo de observación mediante la utilidad de administración de BAM, se crean las siguientes cinco tablas en la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="4605d-134">When you deploy an observation model using the BAM Management utility, the following five tables are created in the PID.</span></span>  
  
|<span data-ttu-id="4605d-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="4605d-135">Name</span></span>|<span data-ttu-id="4605d-136">Description</span><span class="sxs-lookup"><span data-stu-id="4605d-136">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="4605d-137">Tabla activa</span><span class="sxs-lookup"><span data-stu-id="4605d-137">Active table</span></span>|<span data-ttu-id="4605d-138">Denominado bam_\<*nombre de la actividad*> _especifique, esta tabla contiene las actividades de este tipo que aún no se han completado.</span><span class="sxs-lookup"><span data-stu-id="4605d-138">Named bam_\<*activity name*>_Active, this table holds the activities of this type that have not yet completed.</span></span>|  
|<span data-ttu-id="4605d-139">Tabla de relaciones activas</span><span class="sxs-lookup"><span data-stu-id="4605d-139">Active relationships table</span></span>|<span data-ttu-id="4605d-140">Denominado bam_\<*nombre de la actividad*> _ActiveRelationships, esta tabla contiene las actividades relacionadas con la actividad que aún no se han completado.</span><span class="sxs-lookup"><span data-stu-id="4605d-140">Named bam_\<*activity name*>_ActiveRelationships, this table contains the related activities for the activity that have not yet completed.</span></span>|  
|<span data-ttu-id="4605d-141">Tabla de continuaciones</span><span class="sxs-lookup"><span data-stu-id="4605d-141">Continuations table</span></span>|<span data-ttu-id="4605d-142">Denominado bam_\<*nombre de la actividad*> _continuations, esta tabla se muestran las actividades de continuaciones para la actividad.</span><span class="sxs-lookup"><span data-stu-id="4605d-142">Named bam_\<*activity name*>_continuations, this table lists the continuations activities for the activity.</span></span>|  
|<span data-ttu-id="4605d-143">Tabla de actividades completadas</span><span class="sxs-lookup"><span data-stu-id="4605d-143">Completed table</span></span>|<span data-ttu-id="4605d-144">Denominado bam_\<*nombre de la actividad*> _completed.</span><span class="sxs-lookup"><span data-stu-id="4605d-144">Named bam_\<*activity name*>_completed.</span></span>|  
|<span data-ttu-id="4605d-145">Tabla de relaciones completadas</span><span class="sxs-lookup"><span data-stu-id="4605d-145">Completed Relationships table</span></span>|<span data-ttu-id="4605d-146">Denominado bam_\<*nombre de la actividad*> _CompletedRelationships, esta tabla contiene las actividades relacionadas completadas para la actividad.</span><span class="sxs-lookup"><span data-stu-id="4605d-146">Named bam_\<*activity name*>_CompletedRelationships, this table contains the completed related activities for the activity.</span></span>|  
  
 <span data-ttu-id="4605d-147">En una actividad de BAM se capturan cuatro tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="4605d-147">You capture four types of data in a BAM activity:</span></span>  
  
-   <span data-ttu-id="4605d-148">String</span><span class="sxs-lookup"><span data-stu-id="4605d-148">String</span></span>  
  
-   <span data-ttu-id="4605d-149">Date/Time (normalmente denominados hitos)</span><span class="sxs-lookup"><span data-stu-id="4605d-149">Data/Time (commonly referred to as milestones)</span></span>  
  
-   <span data-ttu-id="4605d-150">Integer</span><span class="sxs-lookup"><span data-stu-id="4605d-150">Integer</span></span>  
  
-   <span data-ttu-id="4605d-151">Float</span><span class="sxs-lookup"><span data-stu-id="4605d-151">Float</span></span>