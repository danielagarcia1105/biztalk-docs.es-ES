---
title: Usar IntelliSense para crear un archivo de configuración de Interceptor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d6df002c51bbcc51a3cb714e389a0f453a0693c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011357"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a><span data-ttu-id="c5673-102">Uso de IntelliSense para crear un archivo de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="c5673-102">Using IntelliSense to Create an Interceptor Configuration File</span></span>
<span data-ttu-id="c5673-103">Puede usar IntelliSense y la validación de esquemas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para que le ayuden a construir archivos de configuración de interceptor válidos en términos de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c5673-103">You can use IntelliSense and schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to help you construct interceptor configuration files that are schematically valid.</span></span> <span data-ttu-id="c5673-104">La utilidad de administración de BAM valida el archivo de configuración del interceptor con respecto al esquema de configuración del interceptor base y, si el archivo no es válido, no implementa el esquema.</span><span class="sxs-lookup"><span data-stu-id="c5673-104">The BAM management utility validates your interceptor configuration file against the base interceptor configuration schema and, if the file is not valid, does not deploy the schema.</span></span> <span data-ttu-id="c5673-105">Si el archivo pasa la validación con respecto al esquema de configuración del interceptor base, se valida en relación a los esquemas específicos de la tecnología, como el esquema de [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] o el de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)], durante el tiempo de ejecución. Si no se encuentran errores, no se producirá ninguna intercepción.</span><span class="sxs-lookup"><span data-stu-id="c5673-105">If the file passes validation against the base interceptor configuration schema, it is validated against technology-specific schemas like the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema or the [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema during run time and if errors are encountered, no interception will occur.</span></span> <span data-ttu-id="c5673-106">Puede prevenir estos errores usando la validación de esquemas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] al construir su archivo de configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="c5673-106">You can avoid these errors by using schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when constructing your interceptor configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5673-107">Los archivos XSD de configuración de interceptor DE BAM de ejemplo se instalan con archivos SDK.</span><span class="sxs-lookup"><span data-stu-id="c5673-107">The sample BAM interceptor configuration XSD files are installed with the SDK files.</span></span> <span data-ttu-id="c5673-108">Pueden encontrarse en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:</span><span class="sxs-lookup"><span data-stu-id="c5673-108">They can be found at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:</span></span>  
> 
> - <span data-ttu-id="c5673-109">CommonInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="c5673-109">CommonInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="c5673-110">WcfInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="c5673-110">WcfInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="c5673-111">WorkflowInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="c5673-111">WorkflowInterceptorConfiguration.xsd</span></span>  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a><span data-ttu-id="c5673-112">Para obtener una copia de los esquemas del interceptor</span><span class="sxs-lookup"><span data-stu-id="c5673-112">To obtain a copy of the interceptor schemas</span></span>  
  
1. <span data-ttu-id="c5673-113">Abra el Bloc de notas u otro procesador de texto.</span><span class="sxs-lookup"><span data-stu-id="c5673-113">Open Notepad or another text editor.</span></span>  
  
2. <span data-ttu-id="c5673-114">Navegue hasta la [esquema de configuración de Interceptor](../core/interceptor-configuration-schema.md) tema.</span><span class="sxs-lookup"><span data-stu-id="c5673-114">Navigate to the [Interceptor Configuration Schema](../core/interceptor-configuration-schema.md) topic.</span></span>  
  
3. <span data-ttu-id="c5673-115">Pegue el contenido en un nuevo documento en el editor de texto abierto y, a continuación, guarde el archivo como un archivo de texto con el nombre **CommonInterceptorConfiguration.xsd** (o uno de su propia elección) en el disco duro.</span><span class="sxs-lookup"><span data-stu-id="c5673-115">Paste the contents into a new document in the open text editor, and then save the file as a text file using the name **CommonInterceptorConfiguration.xsd** (or one of your own choosing) to your hard disk.</span></span>  
  
4. <span data-ttu-id="c5673-116">Repita estos pasos para la [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] esquema y [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] temas del esquema con los nombres de archivo **WorkflowInterceptorConfiguration.xsd** y **WcfInterceptorConfiguration.xsd** o nombres de su propia elección.</span><span class="sxs-lookup"><span data-stu-id="c5673-116">Repeat these steps for the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema and [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema topics using the file names **WorkflowInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** or names of your own choosing.</span></span>  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a><span data-ttu-id="c5673-117">Procedimiento para usar IntelliSense con su archivo de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="c5673-117">To use IntelliSense with your interceptor configuration file</span></span>  
  
1. <span data-ttu-id="c5673-118">Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5673-118">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="c5673-119">Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="c5673-119">Click **File**, click **New**, and then click **File**.</span></span>  
  
3. <span data-ttu-id="c5673-120">En el **nuevo archivo** cuadro de diálogo, seleccione **archivo XML** y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="c5673-120">In the **New File** dialog box, select **XML File** and then click **Open**.</span></span>  
  
4. <span data-ttu-id="c5673-121">Ver el panel de propiedades haciendo clic en el panel de edición y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c5673-121">View the Properties pane by right-clicking the edit pane, and then clicking **Properties**.</span></span>  
  
5. <span data-ttu-id="c5673-122">En el panel Propiedades, haga clic en **esquemas**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ).</span><span class="sxs-lookup"><span data-stu-id="c5673-122">In the Properties pane, click **Schemas**, and then click the ellipsis (**…**).</span></span>  
  
6. <span data-ttu-id="c5673-123">En el **esquemas XML** cuadro de diálogo, haga clic en **agregar** y, a continuación, navegue hasta la ubicación de los esquemas y seleccione **CommonInterceptorConfiguration.xsd** y  **WcfInterceptorConfiguration.xsd** si está trabajando con un [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] archivo de configuración de interceptor, o **WorkflowInterceptorConfiguration.xsd** si está trabajando con un [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] archivo de configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="c5673-123">In the **XML Schemas** dialog box, click **Add** and then navigate to the location of the schemas and select **CommonInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor configuration file, or **WorkflowInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor configuration file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c5673-124">Si ha guardado los archivos con nombres diferentes, seleccione esos archivos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c5673-124">If you saved the files using different names, select those files instead.</span></span>  
  
7. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="c5673-125"> validará su archivo de configuración de interceptor cuando éste se abra, y le proporcionará ayuda de IntelliSense cuando cree y vaya modificando el archivo.</span><span class="sxs-lookup"><span data-stu-id="c5673-125"> will now validate your interceptor configuration file when it is opened and supply IntelliSense help as you create and modify the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5673-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5673-126">See Also</span></span>  
 <span data-ttu-id="c5673-127">[Esquema de Windows Workflow Foundation](../core/windows-workflow-foundation-schema.md) </span><span class="sxs-lookup"><span data-stu-id="c5673-127">[Windows Workflow Foundation Schema](../core/windows-workflow-foundation-schema.md) </span></span>  
 [<span data-ttu-id="c5673-128">Esquema de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c5673-128">Windows Communication Foundation Schema</span></span>](../core/windows-communication-foundation-schema.md)