---
title: Cómo crear una asignación sin asignaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81be2591c1d8f20f5b8dd01cf01c03e8daed9c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248796"
---
# <a name="how-to-create-a-map-without-maps"></a><span data-ttu-id="9fb33-102">Cómo crear una asignación sin asignaciones</span><span class="sxs-lookup"><span data-stu-id="9fb33-102">How to Create a Map without Maps</span></span>
<span data-ttu-id="9fb33-103">Si dispone de código XSLT que ha estado utilizando para convertir mensajes de instancia, puede utilizar este código directamente en vez de crear una asignación.</span><span class="sxs-lookup"><span data-stu-id="9fb33-103">If you have XSLT code you have been using to convert instance messages, you can use that code directly instead of creating a map.</span></span>  
  
 <span data-ttu-id="9fb33-104">Utilizar el código XSLT implica crear una asignación vacía y establecer su **ruta de XSLT personalizada** propiedad de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9fb33-104">Using your XSLT code involves creating an empty map and setting its **Custom XSLT Path** grid property.</span></span> <span data-ttu-id="9fb33-105">Si el código XSLT utiliza ensamblados .NET externos, debe crear un archivo XML de extensión personalizada.</span><span class="sxs-lookup"><span data-stu-id="9fb33-105">If your XSLT code uses external .NET assemblies, you also need to create a custom extension XML file.</span></span> <span data-ttu-id="9fb33-106">Para obtener información sobre la estructura de un archivo XML de extensión personalizada, consulte el **XML de extensión personalizada (propiedad de cuadrícula)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="9fb33-106">For information about the structure of a custom extension XML file, see the **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a><span data-ttu-id="9fb33-107">Usar código XSLT personalizado en lugar de un mapa</span><span class="sxs-lookup"><span data-stu-id="9fb33-107">Use custom XSLT code in place of a map</span></span>  
  
1.  <span data-ttu-id="9fb33-108">Cree una asignación de BizTalk vacía en el proyecto y establezca los esquemas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="9fb33-108">Create an empty BizTalk map in your project and set the source and destination schemas.</span></span>  
  
     <span data-ttu-id="9fb33-109">Para obtener información sobre cómo crear la asignación y establecer los esquemas, vea [crear asignaciones](../core/creating-maps.md).</span><span class="sxs-lookup"><span data-stu-id="9fb33-109">For information about creating the map and setting the schemas, see [Creating Maps](../core/creating-maps.md).</span></span>  
  
2.  <span data-ttu-id="9fb33-110">En la vista Cuadrícula, haga clic en la cuadrícula del Asignador.</span><span class="sxs-lookup"><span data-stu-id="9fb33-110">In the Grid view, click the mapper grid.</span></span>  
  
     <span data-ttu-id="9fb33-111">Se muestra en la ventana Propiedades del **cuadrícula** propiedades.</span><span class="sxs-lookup"><span data-stu-id="9fb33-111">The Properties window shows the **Grid** properties.</span></span>  
  
3.  <span data-ttu-id="9fb33-112">En la ventana Propiedades, seleccione **ruta de XSLT personalizada** y haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="9fb33-112">In the Properties window, select **Custom XSLT Path** and click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="9fb33-113">En el **abiertos** cuadro de diálogo, desplácese hasta el archivo y haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9fb33-113">In the **Open** dialog box, navigate to the file and click **Open**.</span></span>  
  
     <span data-ttu-id="9fb33-114">El **ruta de XSLT personalizada** se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9fb33-114">The **Custom XSLT Path** property is set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fb33-115">El Asignador de BizTalk solo admite XSLT 1.0.</span><span class="sxs-lookup"><span data-stu-id="9fb33-115">BizTalk Mapper supports XSLT 1.0 only.</span></span> <span data-ttu-id="9fb33-116">No se admite el uso de XSLT 2.0 en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9fb33-116">Using XSLT 2.0 in BizTalk Mapper is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb33-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fb33-117">See Also</span></span>  
 <span data-ttu-id="9fb33-118">[Acerca de las asignaciones](../core/about-maps.md) </span><span class="sxs-lookup"><span data-stu-id="9fb33-118">[About Maps](../core/about-maps.md) </span></span>  
 <span data-ttu-id="9fb33-119">[Secuencias de comandos utilizando XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="9fb33-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 [<span data-ttu-id="9fb33-120">XSLT personalizado</span><span class="sxs-lookup"><span data-stu-id="9fb33-120">Custom XSLT</span></span>](../core/custom-xslt.md)   