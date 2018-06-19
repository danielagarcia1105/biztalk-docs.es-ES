---
title: Requisitos previos para crear aplicaciones de SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51ae9569-4081-4142-9ee2-8ae0069e9d90
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7cddc252868bf47ace0d73e81ddb1c7721bf8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216404"
---
# <a name="prerequisites-to-create-sap-applications"></a><span data-ttu-id="926a3-102">Requisitos previos para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="926a3-102">Prerequisites to create SAP applications</span></span>
<span data-ttu-id="926a3-103">Esta sección proporciona información acerca de las tareas que se deben realizar antes de desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="926a3-103">This section provides information about tasks that you must perform before developing BizTalk applications using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="926a3-104">También se mencionan algunas herramientas de BizTalk Server que se utilizan para desarrollar aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="926a3-104">The section also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  
  
## <a name="create-a-strong-name-key-file"></a><span data-ttu-id="926a3-105">Crear un archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="926a3-105">Create a strong-name key file</span></span>

<span data-ttu-id="926a3-106">Debe crear un archivo de clave de nombre seguro para generar proyectos en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="926a3-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="926a3-107">Un nombre seguro consta de la identidad del proyecto, su nombre de texto simple, el número de versión y la información de referencia cultural (si se proporciona), más una clave pública y una firma digital.</span><span class="sxs-lookup"><span data-stu-id="926a3-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="926a3-108">El archivo de clave de nombre seguro contiene la clave pública y la clave privada.</span><span class="sxs-lookup"><span data-stu-id="926a3-108">The strong-name key file contains the public key and the private key.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="926a3-109">Crear un archivo de clave de nombre seguro es una tarea única.</span><span class="sxs-lookup"><span data-stu-id="926a3-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="926a3-110">Puede usar la misma clave para todas las aplicaciones de BizTalk que desarrolla.</span><span class="sxs-lookup"><span data-stu-id="926a3-110">You can use the same key for all the BizTalk applications you develop.</span></span>  
  
1.  <span data-ttu-id="926a3-111">Abra el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="926a3-111">Open the developer command prompt for Visual Studio.</span></span>  
  
2.  <span data-ttu-id="926a3-112">En el símbolo del sistema vaya a la ubicación donde desea crear el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="926a3-112">At the command prompt navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="926a3-113">Por ejemplo, escriba **cd C:\Sample**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="926a3-113">For example, type **cd C:\Sample**,and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="926a3-114">En el símbolo del sistema, escriba `sn -k <key file name\>.snk`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="926a3-114">At the command prompt, type `sn -k <key file name\>.snk`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="926a3-115">Debería recibir un mensaje en el símbolo del sistema que indica que el par de claves se escribió en el archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="926a3-115">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  
  
4.  <span data-ttu-id="926a3-116">En el símbolo del sistema, escriba **salir**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="926a3-116">At the command prompt, type **exit**, and then press ENTER.</span></span>  

## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="926a3-117">Obtenga información acerca de las herramientas de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="926a3-117">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="926a3-118">Los temas sobre cómo usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en [aplicaciones de BizTalk desarrollar](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md) se supone que tiene conocimientos prácticos de una serie de herramientas de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="926a3-118">The topics on how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in [Develop BizTalk applications](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md) assume that you have working knowledge of a number of BizTalk Server tools.</span></span> <span data-ttu-id="926a3-119">Usará las siguientes herramientas para desarrollar aplicaciones de BizTalk con [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="926a3-119">You will use the following tools to develop BizTalk applications using [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span></span>  
  
-   <span data-ttu-id="926a3-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="926a3-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="926a3-121">Eesigner de orquestación</span><span class="sxs-lookup"><span data-stu-id="926a3-121">Orchestration eesigner</span></span>  
  
-   <span data-ttu-id="926a3-122">Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="926a3-122">Pipeline designer</span></span>  
  
-   <span data-ttu-id="926a3-123">Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="926a3-123">BizTalk mapper</span></span>  
  
-   <span data-ttu-id="926a3-124">Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="926a3-124">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console</span></span>  

  
### <a name="prerequisites"></a><span data-ttu-id="926a3-125">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="926a3-125">Prerequisites</span></span>  
 <span data-ttu-id="926a3-126">Debe instalar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para poder tener acceso a las herramientas de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="926a3-126">You must install [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  
  
### <a name="biztalk-server-tools"></a><span data-ttu-id="926a3-127">Herramientas de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="926a3-127">BizTalk Server Tools</span></span>  
 <span data-ttu-id="926a3-128">En la tabla siguiente incluye los temas de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación que explica cómo usar cada una de las herramientas enumeradas.</span><span class="sxs-lookup"><span data-stu-id="926a3-128">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  

|<span data-ttu-id="926a3-129">Herramienta</span><span class="sxs-lookup"><span data-stu-id="926a3-129">Tool</span></span>|<span data-ttu-id="926a3-130">Temas de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación principal</span><span class="sxs-lookup"><span data-stu-id="926a3-130">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|<span data-ttu-id="926a3-131">-   [Con Visual Studio](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="926a3-131">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="926a3-132">-   [Trabajar con proyectos de BizTalk](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="926a3-132">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="926a3-133">-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="926a3-133">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="926a3-134">Obtener información acerca de soluciones de Visual Studio, proyectos y elementos en [soluciones y proyectos en Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span><span class="sxs-lookup"><span data-stu-id="926a3-134">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span>|  
|<span data-ttu-id="926a3-135">Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="926a3-135">Orchestration Designer</span></span>|[<span data-ttu-id="926a3-136">Crear orquestaciones mediante el Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="926a3-136">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|<span data-ttu-id="926a3-137">Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="926a3-137">Pipeline Designer</span></span>| [<span data-ttu-id="926a3-138">Crear canalizaciones mediante el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="926a3-138">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)|  
|<span data-ttu-id="926a3-139">Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="926a3-139">BizTalk Mapper</span></span>| [<span data-ttu-id="926a3-140">Creación de mapas mediante el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="926a3-140">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)|  
|<span data-ttu-id="926a3-141">Consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="926a3-141">BizTalk Server Administration console</span></span>|[<span data-ttu-id="926a3-142">Utilizar la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="926a3-142">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)|  

## <a name="next"></a><span data-ttu-id="926a3-143">Siguiente</span><span class="sxs-lookup"><span data-stu-id="926a3-143">Next</span></span>
[<span data-ttu-id="926a3-144">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="926a3-144">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)