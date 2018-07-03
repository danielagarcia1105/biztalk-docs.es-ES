---
title: Cómo crear esquemas para mensajes XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22b241d002884f24be0a2972db24b8a398ee1d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984453"
---
# <a name="how-to-create-schemas-for-xml-messages"></a><span data-ttu-id="14e6f-102">Cómo crear esquemas para mensajes XML</span><span class="sxs-lookup"><span data-stu-id="14e6f-102">How to Create Schemas for XML Messages</span></span>
<span data-ttu-id="14e6f-103">Hay varios métodos para crear esquemas de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="14e6f-103">There are several methods for creating BizTalk message schemas.</span></span> <span data-ttu-id="14e6f-104">Este tema proporciona instrucciones paso a paso para algunos de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="14e6f-104">This topic provides step-by-step instructions for some of those methods.</span></span>  
  
### <a name="to-create-a-new-schema"></a><span data-ttu-id="14e6f-105">Para crear un nuevo esquema</span><span class="sxs-lookup"><span data-stu-id="14e6f-105">To create a new schema</span></span>  
  
1. <span data-ttu-id="14e6f-106">En **el Explorador de soluciones**, seleccione el proyecto de BizTalk al que desea agregar un esquema.</span><span class="sxs-lookup"><span data-stu-id="14e6f-106">In **Solution Explorer**, select the BizTalk project to which you want to add a schema.</span></span>  
  
2. <span data-ttu-id="14e6f-107">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="14e6f-107">On the **Project** menu, click **Add New Item**.</span></span>  
  
3. <span data-ttu-id="14e6f-108">En el **Agregar nuevo elemento - \< *BizTalk ProjectName* \>**  cuadro de diálogo el **plantillas** sección, haga clic en **esquema**.</span><span class="sxs-lookup"><span data-stu-id="14e6f-108">In the **Add New Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Schema**.</span></span>  
  
4. <span data-ttu-id="14e6f-109">En el **nombre** , escriba un nombre para el esquema y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="14e6f-109">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
5. <span data-ttu-id="14e6f-110">Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="14e6f-110">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
6. <span data-ttu-id="14e6f-111">En la vista de árbol de esquema, seleccione el **esquema** nodo y, a continuación, en la ventana Propiedades, seleccione la **Target Namespace** propiedad y escriba un nombre para el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="14e6f-111">In the schema tree view, select the **Schema** node, and then in the Properties window, select the **Target Namespace** property and type a name for the target namespace.</span></span> <span data-ttu-id="14e6f-112">Es importante que establezca esta propiedad en esta fase inicial de creación de esquemas; Evite usar el valor predeterminado **Target Namespace** valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="14e6f-112">It is important that you set this property in this initial phase of schema creation; avoid using the default **Target Namespace** property value.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14e6f-113">Algunos de los nombres que se eligen para los archivos del proyecto, como los archivos de esquema, pueden producir más adelante errores de compilación debido a conflictos con palabras reservadas del lenguaje C# y con nombres de tipos y espacios de nombres de .NET Framework (como System).</span><span class="sxs-lookup"><span data-stu-id="14e6f-113">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as System).</span></span> <span data-ttu-id="14e6f-114">Entre los ejemplos de esquemas se incluyen schema.xsd, XmlContent y RootNodes.</span><span class="sxs-lookup"><span data-stu-id="14e6f-114">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="14e6f-115">Esto es porque el **nombre de tipo** valores predeterminados de la propiedad a la base parte (que no sean de extensión) de la **Filename** propiedad.</span><span class="sxs-lookup"><span data-stu-id="14e6f-115">This is because the **Type Name** property defaults to the base (non-extension) portion of the  **Filename** property.</span></span> <span data-ttu-id="14e6f-116">Puede solucionar este tipo de error de compilación cambiando explícitamente el valor de la **nombre de tipo** propiedad a algo que no entra en conflicto.</span><span class="sxs-lookup"><span data-stu-id="14e6f-116">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="14e6f-117">Puede que deba agregar, eliminar y modificar los registros y campos del esquema junto con las propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="14e6f-117">You may need to add, delete, and modify the records and fields in your schema along with their associated properties.</span></span> <span data-ttu-id="14e6f-118">Para obtener más información sobre esto, vea [administrar los nodos de esquema](../core/managing-the-nodes-within-a-schema.md).</span><span class="sxs-lookup"><span data-stu-id="14e6f-118">To learn more about this, see [Managing the Nodes Within a Schema](../core/managing-the-nodes-within-a-schema.md).</span></span>  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a><span data-ttu-id="14e6f-119">Para generar un esquema a partir de un origen no XSD</span><span class="sxs-lookup"><span data-stu-id="14e6f-119">To generate a schema from a non-XSD source</span></span>  
  
1.  <span data-ttu-id="14e6f-120">En **el Explorador de soluciones**, haga clic en un proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="14e6f-120">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="14e6f-121">En el **agregar elementos generados - \< *BizTalk ProjectName* \>**  cuadro de diálogo el **plantillas** sección, haga clic en **generar Esquemas**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="14e6f-121">In the **Add Generated Items - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="14e6f-122">En el **generar esquemas** cuadro de diálogo el **tipo de documento** lista desplegable, seleccione **esquema XDR**, **esquema DTD**, o **XML correcto**.</span><span class="sxs-lookup"><span data-stu-id="14e6f-122">In the **Generate Schemas** dialog box, in the **Document type** drop-down list, select **XDR Schema**, **DTD Schema**, or **Well-Formed XML**.</span></span>  
  
     <span data-ttu-id="14e6f-123">Si ve alguno **DTD (no cargado)** o **XML bien formado (no cargado)** en la lista desplegable, seleccione el tipo de documento apropiado de todos modos, y se le guiará a través del proceso de instalación de la Falta el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="14e6f-123">If you see either **DTD (Not Loaded)** or **Well-Formed XML (Not Loaded)** in the drop-down list, select the appropriate document type anyway, and you will be guided through the process of installing the missing DLL.</span></span> <span data-ttu-id="14e6f-124">A continuación, repita estos pasos.</span><span class="sxs-lookup"><span data-stu-id="14e6f-124">Then repeat these steps.</span></span>  
  
4.  <span data-ttu-id="14e6f-125">En el **generar esquemas** cuadro de diálogo, haga clic en **examinar**, busque el archivo que desea importar y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="14e6f-125">In the **Generate Schemas** dialog box, click **Browse**, locate the file you want to import, and then click **Open**.</span></span> <span data-ttu-id="14e6f-126">El archivo encontrado debe coincidir con el tipo de documento seleccionado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="14e6f-126">The file you locate must match the document type you selected in the previous step.</span></span>  
  
     <span data-ttu-id="14e6f-127">Se genera un nuevo esquema a partir del archivo especificado con el mismo nombre que el archivo con la extensión .xsd y se abre en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="14e6f-127">A new schema is generated from the specified file, using the same name as that file with the .xsd extension, and opened in BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e6f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="14e6f-128">See Also</span></span>  
 [<span data-ttu-id="14e6f-129">Administración de esquemas en proyectos</span><span class="sxs-lookup"><span data-stu-id="14e6f-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)