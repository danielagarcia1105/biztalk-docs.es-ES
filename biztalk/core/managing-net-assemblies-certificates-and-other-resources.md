---
title: Administrar ensamblados. NET, certificados y otros recursos | Documentos de Microsoft
description: "Vínculos para agregar archivos de enlace, certificados, ensamblados, directorios virtuales, archivos y más información en el servidor BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb74762bdf08e6e9e2a79650a26dedb0915ea8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a><span data-ttu-id="b515d-103">Administrar ensamblados. NET, certificados y otros recursos</span><span class="sxs-lookup"><span data-stu-id="b515d-103">Manage .NET Assemblies, Certificates, and Other Resources</span></span>

## <a name="overview"></a><span data-ttu-id="b515d-104">Información general</span><span class="sxs-lookup"><span data-stu-id="b515d-104">Overview</span></span>
<span data-ttu-id="b515d-105">Esta sección proporciona instrucciones sobre cómo usar la consola de administración de BizTalk Server y la herramienta de línea de comandos BTSTask para administrar los siguientes tipos de artefactos de recursos para una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b515d-105">This section provides instructions on using the BizTalk Server Administration console and the BTSTask command-line tool to manage the following types of resource artifacts for a BizTalk application.</span></span> <span data-ttu-id="b515d-106">Estos artefactos de recursos no se pueden implementar automáticamente en una aplicación de BizTalk desde Visual Studio; por tanto, se deben agregar de forma manual a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b515d-106">These resource artifacts cannot be automatically deployed into a BizTalk application from Visual Studio, so you must add them manually to the application.</span></span> <span data-ttu-id="b515d-107">Sin embargo, una vez agregados a una aplicación, se pueden importar, exportar e instalar como una unidad junto con la aplicación y sus demás artefactos.</span><span class="sxs-lookup"><span data-stu-id="b515d-107">Once added to an application, however, you can import, export, and install them as a unit with the application and its other artifacts.</span></span>  
  
-   <span data-ttu-id="b515d-108">**Los archivos.**</span><span class="sxs-lookup"><span data-stu-id="b515d-108">**Files.**</span></span> <span data-ttu-id="b515d-109">puede incluir archivos ad hoc, como archivos Léame.</span><span class="sxs-lookup"><span data-stu-id="b515d-109">You can include ad hoc files, such as a Readme file.</span></span> <span data-ttu-id="b515d-110">Al instalar la aplicación, los archivos se copian en la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="b515d-110">When you install the application, files are copied to the installation folder.</span></span>  
  
-   <span data-ttu-id="b515d-111">**Certificados.**</span><span class="sxs-lookup"><span data-stu-id="b515d-111">**Certificates.**</span></span> <span data-ttu-id="b515d-112">puede agregar un archivo de certificados a una aplicación, de modo que pueda transportar el certificado de un grupo de BizTalk a otro, empaquetado con una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b515d-112">You can add a certificate file to an application so that you can transport the certificate from one BizTalk group to another, packaged with an application.</span></span> <span data-ttu-id="b515d-113">Puede asignar certificados a los puertos de envío y las ubicaciones de recepción para comprobar las identidades y establecer vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="b515d-113">You assign certificates to send ports and receive locations to verify identities and to establish secure links.</span></span>  
  
-   <span data-ttu-id="b515d-114">**Componentes COM y COM +.**</span><span class="sxs-lookup"><span data-stu-id="b515d-114">**COM and COM+ components.**</span></span> <span data-ttu-id="b515d-115">puede incluir componentes COM y COM+ administrados para proporcionar funcionalidad adicional en una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b515d-115">You can include managed COM and managed COM+ components to provide additional functionality in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="b515d-116">**Ensamblados. NET.**</span><span class="sxs-lookup"><span data-stu-id="b515d-116">**.NET assemblies.**</span></span> <span data-ttu-id="b515d-117">puede incluir ensamblados .NET que no sean específicamente ensamblados de BizTalk en una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b515d-117">You can include .NET assemblies that are not specifically BizTalk assemblies in a BizTalk application.</span></span> <span data-ttu-id="b515d-118">Los ensamblados de BizTalk son ensamblados .NET que contienen orquestaciones, canalizaciones, esquemas o asignaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b515d-118">(BizTalk assemblies are .NET assemblies that contain BizTalk orchestrations, pipelines, schemas, or maps.)</span></span>  
  
-   <span data-ttu-id="b515d-119">**Archivos de definición de BAM.**</span><span class="sxs-lookup"><span data-stu-id="b515d-119">**BAM definition files.**</span></span> <span data-ttu-id="b515d-120">para facilitar la implementación de BAM, puede crear una aplicación de BizTalk y agregarle definiciones de BAM.</span><span class="sxs-lookup"><span data-stu-id="b515d-120">To make BAM deployment easier, you can create a BizTalk application and add BAM definitions to it.</span></span> <span data-ttu-id="b515d-121">Posteriormente, puede usar las características de implementación de aplicaciones de BizTalk para implementar las definiciones de BAM en distintos entornos.</span><span class="sxs-lookup"><span data-stu-id="b515d-121">You can then use the BizTalk application deployment features to deploy the BAM definitions into different environments.</span></span>  
  
-   <span data-ttu-id="b515d-122">**Archivos de enlace.**</span><span class="sxs-lookup"><span data-stu-id="b515d-122">**Binding files.**</span></span> <span data-ttu-id="b515d-123">puede agregar archivos de enlace a una aplicación para que el proceso de mover una aplicación de un entorno de desarrollo a otro sea más rápido y sencillo.</span><span class="sxs-lookup"><span data-stu-id="b515d-123">You can add binding files to an application to make moving an application from one deployment environment to another quicker and easier.</span></span>  
  
-   <span data-ttu-id="b515d-124">**Directorios virtuales.**</span><span class="sxs-lookup"><span data-stu-id="b515d-124">**Virtual directories.**</span></span> <span data-ttu-id="b515d-125">puede agregar directorios virtuales a las aplicaciones de modo que se implementen junto con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b515d-125">You can add virtual directories to your application so that they will be deployed with the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b515d-126">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="b515d-126">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="b515d-127">Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="b515d-127">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b515d-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b515d-128">Next steps</span></span>
  
-   [<span data-ttu-id="b515d-129">Agregar un archivo a una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-129">Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="b515d-130">Agregar un certificado a una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-130">Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="b515d-131">Agregar un componente COM a una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-131">Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="b515d-132">Agregar un ensamblado de .NET a una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-132">Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="b515d-133">Agregar un artefacto de BAM a una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-133">Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="b515d-134">Agregar un archivo de enlace a una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-134">Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [<span data-ttu-id="b515d-135">Agregar un directorio Virtual para una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-135">Add a Virtual Directory to an Application</span></span>](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [<span data-ttu-id="b515d-136">Modificar las opciones de implementación de un ensamblado. NET, un componente COM, un archivo o un artefacto de BAM</span><span class="sxs-lookup"><span data-stu-id="b515d-136">Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [<span data-ttu-id="b515d-137">Quitar un ensamblado. NET, certificado ni ningún otro artefacto de recurso de una aplicación</span><span class="sxs-lookup"><span data-stu-id="b515d-137">Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)