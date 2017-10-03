---
title: Crear asignaciones usando el asignador de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, maps
- maps, creating
- orchestrations, maps
- translations [maps]
- maps, about maps
- transformations [maps]
- maps
ms.assetid: 265e61d8-8cff-44c9-a717-8e895cb4b9bf
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12da6732729052119bfcc7841424db6d0dcaff9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-maps-using-biztalk-mapper"></a><span data-ttu-id="d29ed-102">Crear asignaciones con el Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d29ed-102">Creating Maps Using BizTalk Mapper</span></span>
<span data-ttu-id="d29ed-103">El Asignador de BizTalk es una herramienta que se ejecuta en el entorno Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d29ed-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="d29ed-104">El Asignador de BizTalk se puede usar para crear y editar asignaciones, que se utilizan para traducir o transformar mensajes xml.</span><span class="sxs-lookup"><span data-stu-id="d29ed-104">BizTalk Mapper can be used to create and edit maps, which are used for translating or transforming xml messages.</span></span> <span data-ttu-id="d29ed-105">Las asignaciones se usan en orquestaciones, como sugiere la siguiente ilustración, y también se pueden usar para procesar los mensajes recibidos en un puerto de recepción y, a continuación, transformar los mensajes para su envío mediante puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="d29ed-105">Maps are used in orchestrations, as the following figure suggest, and can also be used for processing messages received at a receive port, and then transforming the message to be sent via send port(s).</span></span>  
  
 <span data-ttu-id="d29ed-106">![Diagrama de procesamiento empresarial con asignaciones. ] (../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")</span><span class="sxs-lookup"><span data-stu-id="d29ed-106">![Business processing diagram with maps.](../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")</span></span>  
<span data-ttu-id="d29ed-107">Asignaciones en procesamiento empresarial</span><span class="sxs-lookup"><span data-stu-id="d29ed-107">Maps in Business Processing</span></span>  
  
 <span data-ttu-id="d29ed-108">Las asignaciones le permiten traducir y transformar mensajes.</span><span class="sxs-lookup"><span data-stu-id="d29ed-108">Maps enable you to translate and to transform messages.</span></span> <span data-ttu-id="d29ed-109">La traducción es el proceso por el que se convierte un mensaje de un formato en otro formato, como convertir un archivo sin formato en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d29ed-109">Translation is the process of converting a message from one format to another format, such as converting a flat file into an XML file.</span></span> <span data-ttu-id="d29ed-110">La transformación es el proceso por el que se toma información de un mensaje y se inserta en otro.</span><span class="sxs-lookup"><span data-stu-id="d29ed-110">Transformation is the process of taking information from one message and inserting it in another message.</span></span> <span data-ttu-id="d29ed-111">Por ejemplo, puede tomar las direcciones de envío y de facturación de un pedido e insertarlas en un documento de factura.</span><span class="sxs-lookup"><span data-stu-id="d29ed-111">For example, you might take shipping and billing addresses from a purchase order and insert them in an invoice document.</span></span>  
  
 <span data-ttu-id="d29ed-112">El Asignador de BizTalk utiliza su propio sistema gráfico de iconos y vínculos para representar la traducción y transformación de mensajes de instancia de entrada a mensajes de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="d29ed-112">BizTalk Mapper uses its own graphical system of icons and links to represent the translation and transformation of input instance messages to output instance messages.</span></span> <span data-ttu-id="d29ed-113">El Asignador utiliza la misma representación gráfica de esquemas que el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d29ed-113">Mapper uses the same graphical representation of schemas as BizTalk Editor.</span></span> <span data-ttu-id="d29ed-114">El Asignador de BizTalk almacena las asignaciones como hojas de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT).</span><span class="sxs-lookup"><span data-stu-id="d29ed-114">BizTalk Mapper stores its maps as Extensible Stylesheet Language Transformations (XSLT) stylesheets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d29ed-115">El Asignador de BizTalk es compatible con XSLT 1.0.</span><span class="sxs-lookup"><span data-stu-id="d29ed-115">BizTalk Mapper supports XSLT 1.0.</span></span> <span data-ttu-id="d29ed-116">No se admite el uso de XSLT 2.0 en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d29ed-116">Using XSLT 2.0 in BizTalk Mapper is not supported.</span></span>  
  
 <span data-ttu-id="d29ed-117">Para obtener información sobre la creación de esquemas, vea [crear esquemas de uso del Editor BizTalk](../core/creating-schemas-using-biztalk-editor.md).</span><span class="sxs-lookup"><span data-stu-id="d29ed-117">For information about creating schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span> <span data-ttu-id="d29ed-118">Para obtener información sobre el uso de las asignaciones en orquestaciones, consulte [crear orquestaciones utilizando Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md).</span><span class="sxs-lookup"><span data-stu-id="d29ed-118">For information about using maps within orchestrations, see [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d29ed-119">El rendimiento de una asignación depende de la complejidad de la asignación: el número y el tipo de functoids, el tamaño de los esquemas de entrada y de salida, el tamaño del mensaje de entrada y el hardware.</span><span class="sxs-lookup"><span data-stu-id="d29ed-119">The performance of a map depends on the complexity of the map - the number and type of functoids, size of input and output schemas, the size of the input message, and your hardware.</span></span>  
  
 <span data-ttu-id="d29ed-120">Para obtener información sobre cómo usar métodos abreviados de teclado para el asignador de BizTalk, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="d29ed-120">For information about using the keyboard shortcuts for BizTalk Mapper, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d29ed-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d29ed-121">In This Section</span></span>  
  
-   [<span data-ttu-id="d29ed-122">Planear la creación de mapas</span><span class="sxs-lookup"><span data-stu-id="d29ed-122">Planning to Create Maps</span></span>](../core/planning-to-create-maps.md)  
  
-   [<span data-ttu-id="d29ed-123">Acerca de las asignaciones</span><span class="sxs-lookup"><span data-stu-id="d29ed-123">About Maps</span></span>](../core/about-maps.md)  
  
-   [<span data-ttu-id="d29ed-124">Con el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d29ed-124">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)  
  
-   [<span data-ttu-id="d29ed-125">Crear mapas</span><span class="sxs-lookup"><span data-stu-id="d29ed-125">Creating Maps</span></span>](../core/creating-maps.md)  
  
-   [<span data-ttu-id="d29ed-126">Compilar y probar las asignaciones</span><span class="sxs-lookup"><span data-stu-id="d29ed-126">Compiling and Testing Maps</span></span>](../core/compiling-and-testing-maps.md)  
  
-   [<span data-ttu-id="d29ed-127">Solucionar problemas de asignaciones</span><span class="sxs-lookup"><span data-stu-id="d29ed-127">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)