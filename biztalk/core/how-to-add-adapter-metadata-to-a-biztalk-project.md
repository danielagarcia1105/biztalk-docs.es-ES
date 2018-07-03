---
title: Cómo agregar metadatos de adaptador a un proyecto de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c95cfac206dad58e0093945d2495c7e725c849c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968813"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="13f99-102">Cómo agregar metadatos de adaptador a un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="13f99-102">How to Add Adapter Metadata to a BizTalk Project</span></span>
<span data-ttu-id="13f99-103">El Asistente para agregar metadatos de adaptador le permite agregar metadatos de adaptador a un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="13f99-103">The Add Adapter Metadata Wizard enables you to add adapter metadata to a BizTalk project.</span></span> <span data-ttu-id="13f99-104">Esos datos incluyen esquemas, tipos de mensajes y tipos de puertos necesarios para comunicarse con un adaptador desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="13f99-104">This data includes schemas, message types, and port types needed to communicate with an adapter from an orchestration.</span></span> <span data-ttu-id="13f99-105">Use este asistente con los adaptadores de aplicación, como FTP, para insertar los esquemas correspondientes a dichos adaptadores en el sistema.</span><span class="sxs-lookup"><span data-stu-id="13f99-105">Use the Add Adapter Metadata Wizard with application adapters, such as FTP, to pull schemas corresponding to these application adapters into the system.</span></span> <span data-ttu-id="13f99-106">Tenga en cuenta que los adaptadores de transporte, como HTTP, no suelen usar esquemas.</span><span class="sxs-lookup"><span data-stu-id="13f99-106">Note that transport adapters such as HTTP do not typically use schemas.</span></span>  
  
 <span data-ttu-id="13f99-107">El siguiente procedimiento le guiará por los pasos genéricos necesarios para agregar metadatos para un adaptador.</span><span class="sxs-lookup"><span data-stu-id="13f99-107">The following procedure walks you through the generic steps to add metadata for an adapter.</span></span>  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="13f99-108">Para agregar metadatos de adaptador a un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="13f99-108">To add adapter metadata to a BizTalk project</span></span>  
  
1. <span data-ttu-id="13f99-109">En su [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el Explorador de soluciones, haga clic en el proyecto, haga clic en **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="13f99-109">In your [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="13f99-110">En el **agregar elementos generados - \<**  <em>nombre del proyecto</em> **\>** cuadro de diálogo el **plantillas** sección, Seleccione **agregar adaptador**y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="13f99-110">In the **Add Generated Items - \<**<em>Project name</em>**\>** dialog box, in the **Templates** section, select **Add Adapter**, and then click **Open**.</span></span>  
  
3. <span data-ttu-id="13f99-111">En el Asistente para agregar metadatos de adaptador, en el **Seleccionar adaptador** página, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13f99-111">In the Add Adapter Metadata Wizard, on the **Select Adapter** page, do the following.</span></span>  
  
   |<span data-ttu-id="13f99-112">Use</span><span class="sxs-lookup"><span data-stu-id="13f99-112">Use this</span></span>|<span data-ttu-id="13f99-113">Para</span><span class="sxs-lookup"><span data-stu-id="13f99-113">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="13f99-114">Cuadro Lista de adaptadores</span><span class="sxs-lookup"><span data-stu-id="13f99-114">Adapter list box</span></span>|<span data-ttu-id="13f99-115">Seleccione el adaptador registrado que desee agregar al proyecto.</span><span class="sxs-lookup"><span data-stu-id="13f99-115">Select the registered adapter to add to the project.</span></span>|  
   |<span data-ttu-id="13f99-116">SQL Server</span><span class="sxs-lookup"><span data-stu-id="13f99-116">SQL Server</span></span>|<span data-ttu-id="13f99-117">Escriba el nombre del servidor de base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="13f99-117">Enter the BizTalk database server name.</span></span>|  
   |<span data-ttu-id="13f99-118">Base de datos</span><span class="sxs-lookup"><span data-stu-id="13f99-118">Database</span></span>|<span data-ttu-id="13f99-119">Muestra la lista de bases de datos de administración de BizTalk para el servidor elegido.</span><span class="sxs-lookup"><span data-stu-id="13f99-119">Displays the list of BizTalk Management databases for the chosen server.</span></span>|  
   |<span data-ttu-id="13f99-120">Puerto</span><span class="sxs-lookup"><span data-stu-id="13f99-120">Port</span></span>|<span data-ttu-id="13f99-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="13f99-121">Optional.</span></span> <span data-ttu-id="13f99-122">Muestra la lista de ubicaciones de recepción y puertos de envío de SQL que se han creado previamente y almacenado en la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="13f99-122">Displays the list of ports created and stored in the BizTalk Management database.</span></span> <span data-ttu-id="13f99-123">Solo se muestran los puertos configurados para funcionar con el adaptador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="13f99-123">Only ports configured to work with the selected adapter are shown.</span></span>|  
  
    <span data-ttu-id="13f99-124">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="13f99-124">Click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="13f99-125">Al intentar agregar esquemas generados que contienen caracteres que el **System.XML.XMLConvert** clase no es compatible con los resultados en un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="13f99-125">Attempting to add generated schemas that contain characters that the **System.XML.XMLConvert** class does not support results in a compilation error.</span></span>  
  
4. <span data-ttu-id="13f99-126">Si está usando un adaptador estático, en el **seleccionar servicios para importar** , seleccione un conjunto de servicios disponibles desde la vista de árbol y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="13f99-126">If you are using a static adapter, on the **Select Services to Import** page, select a set of available services from the tree view, and then click **Finish**.</span></span>  
  
    <span data-ttu-id="13f99-127">– O bien –</span><span class="sxs-lookup"><span data-stu-id="13f99-127">–Or–</span></span>  
  
    <span data-ttu-id="13f99-128">Si está usando un adaptador dinámico, siga los pasos de la interfaz de usuario personalizada para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="13f99-128">If you are using a dynamic adapter, follow the steps in the custom user interface to complete the wizard.</span></span>  
  
   <span data-ttu-id="13f99-129">Una vez finalizado el asistente, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] muestra la lista de archivos .odx y .xsd en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="13f99-129">After you complete the wizard, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] lists the .odx and .xsd files in Solution Explorer.</span></span>