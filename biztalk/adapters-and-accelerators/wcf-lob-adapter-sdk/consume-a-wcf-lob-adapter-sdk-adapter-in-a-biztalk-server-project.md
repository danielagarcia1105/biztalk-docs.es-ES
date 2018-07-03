---
title: Consumir un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b75a3fb19f10188c91120ec816e59996e18c644
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998269"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a><span data-ttu-id="76dfa-102">Consumir un adaptador de SDK de adaptador LOB de WCF en un proyecto de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="76dfa-102">Consume a WCF LOB Adapter SDK adapter in a BizTalk Server project</span></span>
<span data-ttu-id="76dfa-103">Este tema describe cómo consumir un adaptador creado mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] desde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76dfa-103">This topic describes how to consume an adapter built using the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  

> [!NOTE]
>  <span data-ttu-id="76dfa-104">Para poder usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], debe instalar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] herramientas en el mismo equipo que hospeda [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76dfa-104">In order to use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you must install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tools on the same computer hosting [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  


## <a name="use-the-consume-adapter-service-add-in"></a><span data-ttu-id="76dfa-105">Use el consumir el adaptador de complemento de servicio</span><span class="sxs-lookup"><span data-stu-id="76dfa-105">Use the Consume Adapter Service Add-in</span></span>  


1. <span data-ttu-id="76dfa-106">Abra la aplicación de .NET en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76dfa-106">Open your .NET application in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

2. <span data-ttu-id="76dfa-107">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **proyecto** panel, haga clic en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] del proyecto y, a continuación, elija **agregar**&#124;**agregar elementos generados** &#124;  **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="76dfa-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in the **Project** pane, right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project, and then choose **Add**&#124;**Add Generated Items** &#124; **Consume Adapter Service**.</span></span>  

3. <span data-ttu-id="76dfa-108">En el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] de pantalla, seleccione un enlace del adaptador.</span><span class="sxs-lookup"><span data-stu-id="76dfa-108">In the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] screen, select an adapter binding.</span></span>  

4. <span data-ttu-id="76dfa-109">Haga clic en **configurar** para configurar el URI de conexión para el enlace del adaptador seleccionado y para proporcionar las credenciales, propiedades de URI y propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="76dfa-109">Click **Configure** to configure the connection URI for the selected adapter binding and to provide any credentials, URI properties, and binding properties.</span></span> <span data-ttu-id="76dfa-110">Los requisitos reales variarán según el enlace del adaptador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="76dfa-110">Actual requirements will vary based on the selected adapter binding.</span></span>  

5. <span data-ttu-id="76dfa-111">Haga clic en **Aceptar** cuando se ha configurado el URI.</span><span class="sxs-lookup"><span data-stu-id="76dfa-111">Click **OK** when you have configured the URI.</span></span>  

6. <span data-ttu-id="76dfa-112">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="76dfa-112">Click **Connect**.</span></span> <span data-ttu-id="76dfa-113">Si el URI de conexión es válida y se aceptan las credenciales del cliente (si existe), el **categoría** panel debe rellenarse con las categorías y las operaciones proporcionadas por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="76dfa-113">If the connection URI is valid and client credentials (if any) are accepted, the **Category** pane should be populated with the categories and operations provided by the adapter.</span></span>  

7. <span data-ttu-id="76dfa-114">Si el adaptador admite la búsqueda, se activará el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76dfa-114">If the adapter support search, the search field will be active.</span></span> <span data-ttu-id="76dfa-115">En caso contrario, puede filtrar por tipo de contrato y explorar los tipos y las operaciones, haga clic en los nodos en el **categoría** panel.</span><span class="sxs-lookup"><span data-stu-id="76dfa-115">Otherwise, you can filter by contract type and explore types and operations by clicking nodes in the **Category** pane.</span></span>  

8. <span data-ttu-id="76dfa-116">Haga clic en **Aceptar** para generar los artefactos de proxy.</span><span class="sxs-lookup"><span data-stu-id="76dfa-116">Click **OK** to generate the proxy artifacts.</span></span> <span data-ttu-id="76dfa-117">El número de artefactos varía según el tipo de contrato:</span><span class="sxs-lookup"><span data-stu-id="76dfa-117">The number of artifacts varies based on the contract type:</span></span>  


   | <span data-ttu-id="76dfa-118">Tipo de contrato</span><span class="sxs-lookup"><span data-stu-id="76dfa-118">Contract Type</span></span> |  <span data-ttu-id="76dfa-119">Artefacto</span><span class="sxs-lookup"><span data-stu-id="76dfa-119">Artifact</span></span>   |                         <span data-ttu-id="76dfa-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="76dfa-120">Description</span></span>                         |                                                             |
   |---------------|-------------|-------------------------------------------------------------|-------------------------------------------------------------|
   |   <span data-ttu-id="76dfa-121">Saliente</span><span class="sxs-lookup"><span data-stu-id="76dfa-121">Outbound</span></span>    | <span data-ttu-id="76dfa-122">Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="76dfa-122">XML Schemas</span></span> | <span data-ttu-id="76dfa-123">Contiene los esquemas para las operaciones y los tipos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="76dfa-123">Contains the schemas for the selected types and operations.</span></span> |                                                             |
   |   <span data-ttu-id="76dfa-124">Saliente</span><span class="sxs-lookup"><span data-stu-id="76dfa-124">Outbound</span></span>    |             |        <span data-ttu-id="76dfa-125">XML de información de enlace de puerto de envío WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="76dfa-125">WCF-Custom send port binding information XML</span></span>         |  <span data-ttu-id="76dfa-126">Contiene el XML de configuración para el puerto de envío WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="76dfa-126">Contains configuration XML for the WCF-Custom send port.</span></span>   |
   |    <span data-ttu-id="76dfa-127">Entrada</span><span class="sxs-lookup"><span data-stu-id="76dfa-127">Inbound</span></span>    | <span data-ttu-id="76dfa-128">Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="76dfa-128">XML Schemas</span></span> | <span data-ttu-id="76dfa-129">Contiene los esquemas para las operaciones y los tipos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="76dfa-129">Contains the schemas for the selected types and operations.</span></span> |                                                             |
   |    <span data-ttu-id="76dfa-130">Entrada</span><span class="sxs-lookup"><span data-stu-id="76dfa-130">Inbound</span></span>    |             |       <span data-ttu-id="76dfa-131">XML de información de enlace de puerto de recepción WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="76dfa-131">WCF-Custom receive port binding information XML</span></span>       | <span data-ttu-id="76dfa-132">Contiene el XML de configuración de puerto de recepción personalizada de WCF.</span><span class="sxs-lookup"><span data-stu-id="76dfa-132">Contains configuration XML for the WCF-Custom receive port.</span></span> |


9. <span data-ttu-id="76dfa-133">Ahora puede usar los archivos de esquema XML en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="76dfa-133">You can now use the XML Schema files in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  

## <a name="deploy-the-biztalk-server-project"></a><span data-ttu-id="76dfa-134">Implementar el proyecto de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="76dfa-134">Deploy the BizTalk Server project</span></span>  

1. <span data-ttu-id="76dfa-135">Abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="76dfa-135">Open **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="76dfa-136">Importe los archivos XML de enlace de puerto para crear los puertos físicos.</span><span class="sxs-lookup"><span data-stu-id="76dfa-136">Import the port binding XML file(s) to create the physical ports.</span></span> <span data-ttu-id="76dfa-137">Haga clic en la aplicación en el **aplicaciones** grupo, seleccione **importar enlaces**y, a continuación, vaya a y seleccione la información de enlace de puerto adecuado archivos XML.</span><span class="sxs-lookup"><span data-stu-id="76dfa-137">Right-click your application under the **Applications** group, select **Import Bindings**, and then navigate to and select the appropriate port binding information XML file(s).</span></span>  

3. <span data-ttu-id="76dfa-138">Asigne los puertos lógicos definidos en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orquestaciones para los puertos físicos recién creados.</span><span class="sxs-lookup"><span data-stu-id="76dfa-138">Map the logical ports defined in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestrations to the newly created physical ports.</span></span>  

4. <span data-ttu-id="76dfa-139">Haga clic en **orquestaciones** debajo de la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **Enlist**.</span><span class="sxs-lookup"><span data-stu-id="76dfa-139">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  

5. <span data-ttu-id="76dfa-140">Haga clic en **orquestaciones** debajo de la aplicación, haga clic en la orquestación para dar de alta y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="76dfa-140">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Start**.</span></span>  

6. <span data-ttu-id="76dfa-141">Haga clic en su [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="76dfa-141">Right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, and then click **Start**.</span></span>  

## <a name="generate-multiple-schemas"></a><span data-ttu-id="76dfa-142">Generar varios esquemas</span><span class="sxs-lookup"><span data-stu-id="76dfa-142">Generate Multiple Schemas</span></span>  
 <span data-ttu-id="76dfa-143">Si usa el Asistente para consumir un servicio adaptador para generar varios esquemas, uno o varios elementos pueden estar duplicados en los esquemas de un error de compilación para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="76dfa-143">If you use the Consume Adapter Service Wizard to generate multiple schemas, one or more elements may be duplicated in the schemas resulting in compilation failure for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="76dfa-144">Puede evitar esto seleccionando la **genere el tipo de esquema únicos** casilla de verificación para asegurarse de que se generan tipos de esquemas con espacios de nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="76dfa-144">You can avoid this by selecting the **Generate Unique Schema Type** check box to ensure that schema types are generated with unique namespaces.</span></span>  

## <a name="see-also"></a><span data-ttu-id="76dfa-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="76dfa-145">See Also</span></span>  
 [<span data-ttu-id="76dfa-146">Consumir un adaptador creado mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="76dfa-146">Consume an adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)