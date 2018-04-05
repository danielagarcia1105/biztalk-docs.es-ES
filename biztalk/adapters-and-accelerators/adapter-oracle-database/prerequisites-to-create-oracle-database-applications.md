---
title: Requisitos previos para crear aplicaciones de base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong-name key file, creating a
ms.assetid: 7a6b2e50-8153-468c-a25e-c15612792773
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba73b79cbbb7914f53c066b474deb23ffcaa9c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-to-create-oracle-database-applications"></a><span data-ttu-id="8a160-102">Requisitos previos para crear aplicaciones de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="8a160-102">Prerequisites to create Oracle Database applications</span></span>
<span data-ttu-id="8a160-103">¿Qué debe hacer antes de desarrollar aplicaciones de BizTalk con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a160-103">What you must do before developing BizTalk applications using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="8a160-104">También se mencionan algunas herramientas de BizTalk Server que se utilizan para desarrollar aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8a160-104">The section also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  
  
## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="8a160-105">Crear un archivo de claves con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="8a160-105">Create a strong-named key file</span></span>

<span data-ttu-id="8a160-106">Debe crear un archivo de clave de nombre seguro para generar proyectos en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a160-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="8a160-107">Un nombre seguro consta de la identidad del proyecto, su nombre de texto simple, el número de versión y la información de referencia cultural (si se proporciona); Además de una clave pública y una firma digital.</span><span class="sxs-lookup"><span data-stu-id="8a160-107">A strong name consists of the project's identity — its simple text name, version number, and culture information (if provided); plus a public key and a digital signature.</span></span> <span data-ttu-id="8a160-108">El archivo de clave de nombre seguro contiene la clave pública y la clave privada.</span><span class="sxs-lookup"><span data-stu-id="8a160-108">The strong-name key file contains the public key and the private key.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8a160-109">Crear un archivo de clave de nombre seguro es una tarea única.</span><span class="sxs-lookup"><span data-stu-id="8a160-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="8a160-110">Puede usar la misma clave para todas las aplicaciones de BizTalk que desarrolla.</span><span class="sxs-lookup"><span data-stu-id="8a160-110">You can use the same key for all the BizTalk applications you develop.</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="8a160-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8a160-111">Prerequisites</span></span>  
 <span data-ttu-id="8a160-112">Debe tener Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] instalado en el equipo donde desea crear una clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="8a160-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  
  
### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="8a160-113">Crear un archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="8a160-113">Create a strong-name key file</span></span>  
  
1.  <span data-ttu-id="8a160-114">Abra el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8a160-114">Open the developer command prompt for Visual Studio.</span></span>  
  
2.  <span data-ttu-id="8a160-115">En el símbolo del sistema, navegue a la ubicación donde desea crear el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="8a160-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="8a160-116">Por ejemplo, escriba `cd C:\Sample`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8a160-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="8a160-117">En el símbolo del sistema, escriba `sn -k <key file name>.snk`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8a160-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a160-118">Debería recibir un mensaje en el símbolo del sistema que indica que el par de claves se escribió en el archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="8a160-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  
  
4.  <span data-ttu-id="8a160-119">En el símbolo del sistema, escriba `exit`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8a160-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  
  
## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="8a160-120">Obtenga información acerca de las herramientas de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8a160-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="8a160-121">Los temas sobre cómo usar el [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] en [bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) se escriben con la suposición de que tiene conocimientos prácticos de un número de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas.</span><span class="sxs-lookup"><span data-stu-id="8a160-121">The topics on how to use the [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] in [Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="8a160-122">Use las siguientes herramientas para desarrollar aplicaciones de BizTalk con el [!INCLUDE[adapteroracle_md](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8a160-122">You use the following tools to develop BizTalk applications using the [!INCLUDE[adapteroracle_md](../../includes/adapteroracle-md.md)]:</span></span>  
  
-   <span data-ttu-id="8a160-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a160-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="8a160-124">Explorador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8a160-124">BizTalk Explorer</span></span>  
  
-   <span data-ttu-id="8a160-125">Eesigner de orquestación</span><span class="sxs-lookup"><span data-stu-id="8a160-125">Orchestration eesigner</span></span>  
  
-   <span data-ttu-id="8a160-126">Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8a160-126">Pipeline designer</span></span>  
  
-   <span data-ttu-id="8a160-127">Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8a160-127">BizTalk mapper</span></span>  
  
-   <span data-ttu-id="8a160-128">Consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8a160-128">BizTalk Server Administration console</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="8a160-129">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8a160-129">Prerequisites</span></span>  
 <span data-ttu-id="8a160-130">Debe instalar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] antes de que puede tener acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas.</span><span class="sxs-lookup"><span data-stu-id="8a160-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  
  
### <a name="biztalk-server-tools"></a><span data-ttu-id="8a160-131">Herramientas de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8a160-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="8a160-132">En la tabla siguiente incluye los temas de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación que explica cómo usar cada una de las herramientas enumeradas.</span><span class="sxs-lookup"><span data-stu-id="8a160-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  
  
|<span data-ttu-id="8a160-133">Herramienta</span><span class="sxs-lookup"><span data-stu-id="8a160-133">Tool</span></span>|<span data-ttu-id="8a160-134">Temas de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación principal</span><span class="sxs-lookup"><span data-stu-id="8a160-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|<span data-ttu-id="8a160-135">-   [Con Visual Studio](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="8a160-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="8a160-136">-   [Trabajar con proyectos de BizTalk](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="8a160-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="8a160-137">-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="8a160-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="8a160-138">Obtener información acerca de soluciones de Visual Studio, proyectos y elementos en [soluciones y proyectos en Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span><span class="sxs-lookup"><span data-stu-id="8a160-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span>|  
|<span data-ttu-id="8a160-139">Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="8a160-139">Orchestration Designer</span></span>|[<span data-ttu-id="8a160-140">Crear orquestaciones mediante el Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="8a160-140">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|<span data-ttu-id="8a160-141">Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8a160-141">Pipeline Designer</span></span>| [<span data-ttu-id="8a160-142">Crear canalizaciones mediante el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="8a160-142">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)|  
|<span data-ttu-id="8a160-143">Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8a160-143">BizTalk Mapper</span></span>| [<span data-ttu-id="8a160-144">Creación de mapas mediante el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8a160-144">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)|  
|<span data-ttu-id="8a160-145">Consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8a160-145">BizTalk Server Administration console</span></span>|[<span data-ttu-id="8a160-146">Utilizar la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8a160-146">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)|  
  
## <a name="next"></a><span data-ttu-id="8a160-147">Siguiente</span><span class="sxs-lookup"><span data-stu-id="8a160-147">Next</span></span>
[<span data-ttu-id="8a160-148">Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="8a160-148">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)