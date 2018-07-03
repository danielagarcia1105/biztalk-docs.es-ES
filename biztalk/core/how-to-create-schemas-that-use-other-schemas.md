---
title: Cómo crear esquemas que usan otros esquemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff0bcd9a-6c66-4c3b-bd41-64047a7c8392
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51fdc5e7601eebca7cc8193757cc909784ab828f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987813"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a><span data-ttu-id="786ed-102">Cómo crear esquemas que usan otros esquemas</span><span class="sxs-lookup"><span data-stu-id="786ed-102">How to Create Schemas That Use Other Schemas</span></span>
<span data-ttu-id="786ed-103">El lenguaje de definición de esquemas XML (XSD) proporciona tres mecanismos diferentes pero relacionados entre sí para utilizar un esquema dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="786ed-103">XML Schema definition (XSD) language provides three different but related mechanisms for using one schema within another schema.</span></span> <span data-ttu-id="786ed-104">Estos mecanismos son importar un esquema, incluir un esquema y redefinir un esquema.</span><span class="sxs-lookup"><span data-stu-id="786ed-104">These mechanisms are importing a schema, including a schema, and redefining a schema.</span></span> <span data-ttu-id="786ed-105">Para obtener un resumen breve de estos mecanismos y cómo se diferencian, consulte [esquemas que usan otros esquemas](../core/schemas-that-use-other-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="786ed-105">For a brief summary of these mechanisms and how they differ, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md).</span></span> <span data-ttu-id="786ed-106">Para obtener información detallada, consulte [recursos XSD en Internet](../core/xsd-resources-on-the-web.md) para obtener vínculos a las especificaciones y manual de XSD.</span><span class="sxs-lookup"><span data-stu-id="786ed-106">For detailed information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md) for links to the XSD primer and specifications.</span></span>  
  
 <span data-ttu-id="786ed-107">En este tema se describen los pasos necesarios para importar, incluir y redefinir otros esquemas en el esquema que esté desarrollando.</span><span class="sxs-lookup"><span data-stu-id="786ed-107">This topic describes the steps required to import, include, and redefine other schemas within the schema you are developing.</span></span>  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a><span data-ttu-id="786ed-108">Para importar, incluir o redefinir un esquema dentro de otro esquema</span><span class="sxs-lookup"><span data-stu-id="786ed-108">To import, include, or redefine one schema within another schema</span></span>  
  
1. <span data-ttu-id="786ed-109">En el Editor de BizTalk, abra el esquema en el que desea importar, incluir o redefinir otro esquema.</span><span class="sxs-lookup"><span data-stu-id="786ed-109">In BizTalk Editor, open the schema to which you want to import, include, or redefine another schema.</span></span> <span data-ttu-id="786ed-110">Para abrir un esquema, haga doble clic en él en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="786ed-110">You can open a schema by double-clicking it in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="786ed-111">Seleccione el **esquema** nodo en la parte superior de la vista de árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="786ed-111">Select the **Schema** node at the top of the schema tree view.</span></span>  
  
3. <span data-ttu-id="786ed-112">Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="786ed-112">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
4. <span data-ttu-id="786ed-113">En la ventana Propiedades, en el **avanzadas** categoría, en la parte del valor de la **importaciones** propiedad, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="786ed-113">In the Properties window, in the **Advanced** category, in the value portion of the **Imports** property, click the ellipsis (**...**) button.</span></span>  
  
5. <span data-ttu-id="786ed-114">En el **importaciones** cuadro de diálogo el **importar un esquema nuevo como** lista, seleccione **XSD Import**, **XSD Include**, o **XSD Redefinir**, según corresponda y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="786ed-114">In the **Imports** dialog box, in the **Import New Schema as** list, select **XSD Import**, **XSD Include**, or **XSD Redefine**, as appropriate, and then click **Add**.</span></span>  
  
6. <span data-ttu-id="786ed-115">En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquema** nodo en el árbol del proyecto, seleccione el esquema que desea importar, incluir, o volver a definir y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="786ed-115">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the project tree, select the schema that you want to import, include, or redefine, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="786ed-116">En el **importaciones** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="786ed-116">In the **Imports** dialog box, click **OK**.</span></span>  
  
    <span data-ttu-id="786ed-117">Las directivas XSD adecuadas para implementar la importación, inclusión o redefinición de la operación se agregan a la **esquema** elemento en la vista XSD, incluido un nuevo **importar**, **incluyen**, o **redefinir** elemento según corresponda.</span><span class="sxs-lookup"><span data-stu-id="786ed-117">The appropriate XSD directives to implement the import, include, or redefine operation are added to the **schema** element in the XSD view, including a new **import**, **include**, or **redefine** element, as appropriate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="786ed-118">Asegúrese de que entiende las distintas finalidades de estos tres mecanismos, por ejemplo, en qué difieren con respecto a los requisitos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="786ed-118">Make sure you understand the different purposes of these three mechanisms, such as how they differ with respect to namespace requirements.</span></span> <span data-ttu-id="786ed-119">Siempre puede eliminar un esquema importado, incluido o redefinido anteriormente y, posteriormente, utilizar uno de los otros dos mecanismos. No obstante, según el grado de exhaustividad con el que haya hecho referencia a dicho esquema, podría tener que modificarlo en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="786ed-119">You can always delete a previously imported, included, or redefined schema and then use one of the other two mechanisms, but depending on how extensively you have referenced that schema, you may need to rework your schema accordingly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="786ed-120">El mecanismo XSD para importar, incluir y redefinir un esquema dentro de otro esquema utiliza una referencia al esquema importado, incluido o redefinido.</span><span class="sxs-lookup"><span data-stu-id="786ed-120">The XSD mechanism for importing, including, and redefining one schema within another schema works by reference to the imported, included, or redefined schema.</span></span> <span data-ttu-id="786ed-121">Esto significa que, si hace algún cambio al esquema importado, incluido o redefinido, este cambio se verá reflejado en el esquema que contiene la referencia de importación, inclusión o redefinición.</span><span class="sxs-lookup"><span data-stu-id="786ed-121">This means that if you make a change to the imported, included, or redefined schema, that change will be reflected in the schema containing the import, include, or redefine reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786ed-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="786ed-122">See Also</span></span>  
 <span data-ttu-id="786ed-123">[Administrar esquemas en proyectos](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="786ed-123">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="786ed-124">Cómo crear referencias a otro nodo o tipo</span><span class="sxs-lookup"><span data-stu-id="786ed-124">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)