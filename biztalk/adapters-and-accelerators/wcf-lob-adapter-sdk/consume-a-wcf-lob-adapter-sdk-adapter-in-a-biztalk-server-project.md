---
title: Utilizar un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f81d23b56c2631879f366e6fe502840408a0d7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a><span data-ttu-id="ee824-102">Utilizar un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ee824-102">Consume a WCF LOB Adapter SDK adapter in a BizTalk Server project</span></span>
<span data-ttu-id="ee824-103">Este tema describe cómo consumir un adaptador que se generan con el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee824-103">This topic describes how to consume an adapter built using the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee824-104">Para poder usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], debe instalar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] herramientas en el mismo equipo que hospeda [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee824-104">In order to use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you must install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tools on the same computer hosting [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 
## <a name="use-the-consume-adapter-service-add-in"></a><span data-ttu-id="ee824-105">Use el Consume Adapter Service complemento</span><span class="sxs-lookup"><span data-stu-id="ee824-105">Use the Consume Adapter Service Add-in</span></span>  
 
  
1.  <span data-ttu-id="ee824-106">Abra la aplicación de .NET en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee824-106">Open your .NET application in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee824-107">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **proyecto** panel, haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, elija **agregar**&#124;**agregar elementos generados** &#124;  **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="ee824-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in the **Project** pane, right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project, and then choose **Add**&#124;**Add Generated Items** &#124; **Consume Adapter Service**.</span></span>  
  
3.  <span data-ttu-id="ee824-108">En el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] pantalla, seleccione un enlace del adaptador.</span><span class="sxs-lookup"><span data-stu-id="ee824-108">In the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] screen, select an adapter binding.</span></span>  
  
4.  <span data-ttu-id="ee824-109">Haga clic en **configurar** para configurar el URI de conexión para el enlace del adaptador seleccionado y para proporcionar las credenciales, propiedades URI y propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="ee824-109">Click **Configure** to configure the connection URI for the selected adapter binding and to provide any credentials, URI properties, and binding properties.</span></span> <span data-ttu-id="ee824-110">Los requisitos reales variarán según el enlace del adaptador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ee824-110">Actual requirements will vary based on the selected adapter binding.</span></span>  
  
5.  <span data-ttu-id="ee824-111">Haga clic en **Aceptar** cuando se ha configurado el URI.</span><span class="sxs-lookup"><span data-stu-id="ee824-111">Click **OK** when you have configured the URI.</span></span>  
  
6.  <span data-ttu-id="ee824-112">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ee824-112">Click **Connect**.</span></span> <span data-ttu-id="ee824-113">Si el URI de conexión es válida y se aceptan las credenciales del cliente (si existe), el **categoría** panel se debe rellenar con las categorías y las operaciones proporcionadas por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ee824-113">If the connection URI is valid and client credentials (if any) are accepted, the **Category** pane should be populated with the categories and operations provided by the adapter.</span></span>  
  
7.  <span data-ttu-id="ee824-114">Si el adaptador admite la búsqueda, se activará el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ee824-114">If the adapter support search, the search field will be active.</span></span> <span data-ttu-id="ee824-115">En caso contrario, puede filtrar por tipo de contrato y explorar los tipos y las operaciones haciendo clic en los nodos en el **categoría** panel.</span><span class="sxs-lookup"><span data-stu-id="ee824-115">Otherwise, you can filter by contract type and explore types and operations by clicking nodes in the **Category** pane.</span></span>  
  
8.  <span data-ttu-id="ee824-116">Haga clic en **Aceptar** para generar los artefactos de proxy.</span><span class="sxs-lookup"><span data-stu-id="ee824-116">Click **OK** to generate the proxy artifacts.</span></span> <span data-ttu-id="ee824-117">El número de artefactos varía según el tipo de contrato:</span><span class="sxs-lookup"><span data-stu-id="ee824-117">The number of artifacts varies based on the contract type:</span></span>  
  
    |<span data-ttu-id="ee824-118">Tipo de contrato</span><span class="sxs-lookup"><span data-stu-id="ee824-118">Contract Type</span></span>|<span data-ttu-id="ee824-119">Artefacto</span><span class="sxs-lookup"><span data-stu-id="ee824-119">Artifact</span></span>|<span data-ttu-id="ee824-120">Description</span><span class="sxs-lookup"><span data-stu-id="ee824-120">Description</span></span>||  
    |-------------------|--------------|-----------------|-|  
    |<span data-ttu-id="ee824-121">Salida</span><span class="sxs-lookup"><span data-stu-id="ee824-121">Outbound</span></span>|<span data-ttu-id="ee824-122">Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="ee824-122">XML Schemas</span></span>|<span data-ttu-id="ee824-123">Contiene los esquemas para los tipos seleccionados y las operaciones.</span><span class="sxs-lookup"><span data-stu-id="ee824-123">Contains the schemas for the selected types and operations.</span></span>||  
    |<span data-ttu-id="ee824-124">Salida</span><span class="sxs-lookup"><span data-stu-id="ee824-124">Outbound</span></span>||<span data-ttu-id="ee824-125">XML de información de enlace de puerto de envío WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="ee824-125">WCF-Custom send port binding information XML</span></span>|<span data-ttu-id="ee824-126">Contiene el XML de configuración para el puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="ee824-126">Contains configuration XML for the WCF-Custom send port.</span></span>|  
    |<span data-ttu-id="ee824-127">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee824-127">Inbound</span></span>|<span data-ttu-id="ee824-128">Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="ee824-128">XML Schemas</span></span>|<span data-ttu-id="ee824-129">Contiene los esquemas para los tipos seleccionados y las operaciones.</span><span class="sxs-lookup"><span data-stu-id="ee824-129">Contains the schemas for the selected types and operations.</span></span>||  
    |<span data-ttu-id="ee824-130">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee824-130">Inbound</span></span>||<span data-ttu-id="ee824-131">XML de información de enlace de puerto de recepción de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="ee824-131">WCF-Custom receive port binding information XML</span></span>|<span data-ttu-id="ee824-132">Contiene el XML de configuración de puerto de recepción de WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="ee824-132">Contains configuration XML for the WCF-Custom receive port.</span></span>|  
  
9. <span data-ttu-id="ee824-133">Ahora puede usar los archivos de esquema XML en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee824-133">You can now use the XML Schema files in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="deploy-the-biztalk-server-project"></a><span data-ttu-id="ee824-134">Implementar el proyecto de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ee824-134">Deploy the BizTalk Server project</span></span>  
  
1.  <span data-ttu-id="ee824-135">Abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="ee824-135">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ee824-136">Importe los archivos XML de enlace de puerto para crear los puertos físicos.</span><span class="sxs-lookup"><span data-stu-id="ee824-136">Import the port binding XML file(s) to create the physical ports.</span></span> <span data-ttu-id="ee824-137">Haga clic en la aplicación en el **aplicaciones** grupo, seleccione **importar enlaces**y, a continuación, vaya a y seleccione la información de enlace de puerto adecuado archivos XML.</span><span class="sxs-lookup"><span data-stu-id="ee824-137">Right-click your application under the **Applications** group, select **Import Bindings**, and then navigate to and select the appropriate port binding information XML file(s).</span></span>  
  
3.  <span data-ttu-id="ee824-138">Asigne los puertos lógicos definidos en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orquestaciones a los puertos físicos recién creados.</span><span class="sxs-lookup"><span data-stu-id="ee824-138">Map the logical ports defined in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestrations to the newly created physical ports.</span></span>  
  
4.  <span data-ttu-id="ee824-139">Haga clic en **orquestaciones** en la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **dar de alta**.</span><span class="sxs-lookup"><span data-stu-id="ee824-139">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
5.  <span data-ttu-id="ee824-140">Haga clic en **orquestaciones** en la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ee824-140">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Start**.</span></span>  
  
6.  <span data-ttu-id="ee824-141">Haga clic en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ee824-141">Right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, and then click **Start**.</span></span>  
  
## <a name="generate-multiple-schemas"></a><span data-ttu-id="ee824-142">Generar varios esquemas</span><span class="sxs-lookup"><span data-stu-id="ee824-142">Generate Multiple Schemas</span></span>  
 <span data-ttu-id="ee824-143">Si utiliza el Asistente para consumir un servicio de adaptador para generar varios esquemas, uno o más elementos pueden estar duplicados en los esquemas que se produjo un error de compilación para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="ee824-143">If you use the Consume Adapter Service Wizard to generate multiple schemas, one or more elements may be duplicated in the schemas resulting in compilation failure for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="ee824-144">Para evitarlo, seleccione la **genere el tipo de esquema único** casilla de verificación para asegurarse de que los tipos de esquema se generan con espacios de nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="ee824-144">You can avoid this by selecting the **Generate Unique Schema Type** check box to ensure that schema types are generated with unique namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee824-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee824-145">See Also</span></span>  
 [<span data-ttu-id="ee824-146">Utilizar un adaptador creado mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="ee824-146">Consume an adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)