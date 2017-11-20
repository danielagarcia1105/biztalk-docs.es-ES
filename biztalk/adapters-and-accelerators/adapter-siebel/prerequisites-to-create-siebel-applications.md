---
title: Requisitos previos para crear aplicaciones Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c08f853-7f72-4e08-aa63-debdab68c972
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eeea15b7a05eb50b498c4c177c987f5c5c736a85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-to-create-siebel-applications"></a><span data-ttu-id="8cae6-102">Requisitos previos para crear aplicaciones de Siebel</span><span class="sxs-lookup"><span data-stu-id="8cae6-102">Prerequisites to create Siebel applications</span></span>
<span data-ttu-id="8cae6-103">¿Qué debe hacer antes de desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cae6-103">What you must do before developing BizTalk applications using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="8cae6-104">El tema también enumeran algunas herramientas de BizTalk Server que se utilizan para desarrollar aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8cae6-104">The topic also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  
  
## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="8cae6-105">Crear un archivo de claves con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="8cae6-105">Create a strong-named key file</span></span>

<span data-ttu-id="8cae6-106">Debe crear un archivo de clave de nombre seguro para generar proyectos en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cae6-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="8cae6-107">Un nombre seguro consta de la identidad del proyecto, su nombre de texto simple, el número de versión y la información de referencia cultural (si se proporciona); Además de una clave pública y una firma digital.</span><span class="sxs-lookup"><span data-stu-id="8cae6-107">A strong name consists of the project's identity — its simple text name, version number, and culture information (if provided); plus a public key and a digital signature.</span></span> <span data-ttu-id="8cae6-108">El archivo de clave de nombre seguro contiene la clave pública y la clave privada.</span><span class="sxs-lookup"><span data-stu-id="8cae6-108">The strong-name key file contains the public key and the private key.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8cae6-109">Crear un archivo de clave de nombre seguro es una tarea única.</span><span class="sxs-lookup"><span data-stu-id="8cae6-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="8cae6-110">Puede usar la misma clave para todas las aplicaciones de BizTalk que desarrolla.</span><span class="sxs-lookup"><span data-stu-id="8cae6-110">You can use the same key for all the BizTalk applications you develop.</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="8cae6-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8cae6-111">Prerequisites</span></span>  
 <span data-ttu-id="8cae6-112">Debe tener Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] instalado en el equipo donde desea crear una clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="8cae6-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  
  
### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="8cae6-113">Crear un archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="8cae6-113">Create a strong-name key file</span></span>  
  
1.  <span data-ttu-id="8cae6-114">Abra el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8cae6-114">Open the developer command prompt for Visual Studio.</span></span>  
  
2.  <span data-ttu-id="8cae6-115">En el símbolo del sistema, navegue a la ubicación donde desea crear el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="8cae6-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="8cae6-116">Por ejemplo, escriba `cd C:\Sample`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8cae6-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="8cae6-117">En el símbolo del sistema, escriba `sn -k <key file name>.snk`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8cae6-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8cae6-118">Debería recibir un mensaje en el símbolo del sistema que indica que el par de claves se escribió en el archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="8cae6-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  
  
4.  <span data-ttu-id="8cae6-119">En el símbolo del sistema, escriba `exit`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8cae6-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  
  
## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="8cae6-120">Obtenga información acerca de las herramientas de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8cae6-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="8cae6-121">Los temas sobre cómo usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en [bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md) se escriben con la suposición de que tiene conocimientos prácticos de un número de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas.</span><span class="sxs-lookup"><span data-stu-id="8cae6-121">The topics on how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in [Building blocks to create BizTalk applications with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="8cae6-122">Use las siguientes herramientas para desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8cae6-122">You use the following tools to develop BizTalk applications using the [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span></span>  
  
-   <span data-ttu-id="8cae6-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cae6-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="8cae6-124">Explorador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8cae6-124">BizTalk Explorer</span></span>  
  
-   <span data-ttu-id="8cae6-125">Eesigner de orquestación</span><span class="sxs-lookup"><span data-stu-id="8cae6-125">Orchestration eesigner</span></span>  
  
-   <span data-ttu-id="8cae6-126">Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8cae6-126">Pipeline designer</span></span>  
  
-   <span data-ttu-id="8cae6-127">Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8cae6-127">BizTalk mapper</span></span>  
  
-   <span data-ttu-id="8cae6-128">Consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8cae6-128">BizTalk Server Administration console</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="8cae6-129">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8cae6-129">Prerequisites</span></span>  
 <span data-ttu-id="8cae6-130">Debe instalar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] antes de que puede tener acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas.</span><span class="sxs-lookup"><span data-stu-id="8cae6-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  
  
### <a name="biztalk-server-tools"></a><span data-ttu-id="8cae6-131">Herramientas de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8cae6-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="8cae6-132">En la tabla siguiente incluye los temas de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación que explica cómo usar cada una de las herramientas enumeradas.</span><span class="sxs-lookup"><span data-stu-id="8cae6-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  
  
|<span data-ttu-id="8cae6-133">Herramienta</span><span class="sxs-lookup"><span data-stu-id="8cae6-133">Tool</span></span>|<span data-ttu-id="8cae6-134">Temas de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación principal</span><span class="sxs-lookup"><span data-stu-id="8cae6-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|<span data-ttu-id="8cae6-135">-   [Con Visual Studio](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="8cae6-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="8cae6-136">-   [Trabajar con proyectos de BizTalk](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="8cae6-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="8cae6-137">-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="8cae6-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="8cae6-138">Obtener información acerca de soluciones de Visual Studio, proyectos y elementos en [soluciones y proyectos en Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span><span class="sxs-lookup"><span data-stu-id="8cae6-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span>|  
|<span data-ttu-id="8cae6-139">Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="8cae6-139">Orchestration Designer</span></span>|[<span data-ttu-id="8cae6-140">Crear orquestaciones mediante el Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="8cae6-140">Creating Orchestrations Using Orchestration Designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|<span data-ttu-id="8cae6-141">Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8cae6-141">Pipeline Designer</span></span>| [<span data-ttu-id="8cae6-142">Crear canalizaciones mediante el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8cae6-142">Creating Pipelines Using Pipeline Designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)|  
|<span data-ttu-id="8cae6-143">Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8cae6-143">BizTalk Mapper</span></span>| [<span data-ttu-id="8cae6-144">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8cae6-144">Creating Maps Using BizTalk Mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)|  
|<span data-ttu-id="8cae6-145">Consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8cae6-145">BizTalk Server Administration console</span></span>|[<span data-ttu-id="8cae6-146">Uso de la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8cae6-146">Using the BizTalk Server Administration Console</span></span>](../../core/using-the-biztalk-server-administration-console.md)|  
  
## <a name="next"></a><span data-ttu-id="8cae6-147">Siguiente</span><span class="sxs-lookup"><span data-stu-id="8cae6-147">Next</span></span>
[<span data-ttu-id="8cae6-148">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="8cae6-148">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)