---
title: Vista propiedad de contexto | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a0f3a1d507e1440f67cd5f9e4afa18bff0b52a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="context-property-view"></a><span data-ttu-id="86339-102">Vista Propiedad de contexto</span><span class="sxs-lookup"><span data-stu-id="86339-102">Context Property View</span></span>
<span data-ttu-id="86339-103">La vista Propiedad de contexto muestra el esquema del mensaje XML asociado a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="86339-103">The Context Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="86339-104">La vista está disponible desde el menú contextual para algunas de las formas de la vista Programación de orquestación.</span><span class="sxs-lookup"><span data-stu-id="86339-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-the-context-property-view"></a><span data-ttu-id="86339-105">Trabajar con la vista Propiedad de contexto</span><span class="sxs-lookup"><span data-stu-id="86339-105">Working with the Context Property view</span></span>  
 <span data-ttu-id="86339-106">Seleccione la vista de la propiedad de contexto haciendo clic en el **Seleccionar origen de eventos** botón y haciendo clic en el **Seleccionar propiedad de contexto** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="86339-106">You select your Context Property view by clicking the **Select Event Source** button and clicking the **Select Context Property** menu item.</span></span> <span data-ttu-id="86339-107">A continuación, seleccione una propiedad de contexto desde la lista de propiedades de contexto conocidas para cargar el esquema para esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="86339-107">You then choose a context property from the list of known context properties to load the schema for that property.</span></span> <span data-ttu-id="86339-108">Una vez seleccionada la propiedad, puede arrastrar los elementos del esquema asociado a las carpetas de elementos de datos de la actividad. De esta manera, se indica que desea extraer en esta acción esos datos de la expresión XPath específica del mensaje.</span><span class="sxs-lookup"><span data-stu-id="86339-108">Once you select the property, you can drag elements from the associated schema to the data item folders of the activity, thus indicating you want to extract that data from specific XPath expression inside the message at this action.</span></span>  
  
 <span data-ttu-id="86339-109">Puede abrir las vistas de propiedad de contexto desde la vista de programación de orquestación al hacer clic con el botón secundario en una forma que contenga una propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="86339-109">You can open context property views from the orchestration schedule view by right-clicking a shape that contains a context property.</span></span> <span data-ttu-id="86339-110">Se abrirá un menú contextual desde el que puede hacer clic en el **esquema de propiedades de contexto** elemento de menú para recuperar una lista de propiedades de contexto asociado a la forma.</span><span class="sxs-lookup"><span data-stu-id="86339-110">This will open a context menu from which you can click the **Context Property Schema** menu item to retrieve a list of context properties associated with the shape.</span></span>  
  
 <span data-ttu-id="86339-111">La lista de propiedades de contexto disponibles puede ser amplia.</span><span class="sxs-lookup"><span data-stu-id="86339-111">The list of available context properties can be extensive.</span></span> <span data-ttu-id="86339-112">Si conoce parte del nombre de la propiedad que está buscando, puede escribirla en el **en cadena** cuadro de texto y haga clic en el **búsqueda** botón.</span><span class="sxs-lookup"><span data-stu-id="86339-112">If you know part of the name of the property for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="86339-113">De este modo, se seleccionarán solo las propiedades que contengan la cadena parcial que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="86339-113">This will select only those properties that contain the partial string you have entered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86339-114">Cuando elige asignar desde la vista de propiedades de contexto, la lista de esquemas de propiedad es una lista completa de todos los esquemas de propiedad que se configuraron durante la instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="86339-114">When you choose to map from the Context Properties view, the list of potential property schemas is a complete list of every property schema configured in your BizTalk Server installation.</span></span>  <span data-ttu-id="86339-115">Debe tener en cuenta que los esquemas que se muestran no dependen de las características de BizTalk Server que se utilizan durante el proceso en ejecución con el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="86339-115">You must aware that the schemas presented are not sensitive to which features in BizTalk Server are used by the running process on which you are working.</span></span> <span data-ttu-id="86339-116">Por ejemplo, puede seleccionar un esquema para las propiedades SOAP de la lista de esquemas que se ofrecen cuando se realiza una asignación a partir de las propiedades de contexto, pero puede que el propio proceso en ejecución no utilice SOAP.</span><span class="sxs-lookup"><span data-stu-id="86339-116">For example, you can select a schema for SOAP properties from the list of schemas offered when mapping from Context Properties, but the running process itself may not use SOAP.</span></span> <span data-ttu-id="86339-117">Cualquier elemento de actividad de BAM que se haya asignado a partir de una propiedad sin usar, hace que los datos que captura BAM sean nulos o estén vacíos.</span><span class="sxs-lookup"><span data-stu-id="86339-117">Any BAM activity item mapped from an unused property results in null or empty data being captured by BAM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86339-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="86339-118">See Also</span></span>  
 <span data-ttu-id="86339-119">[¿Qué es la vista del origen de eventos?](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="86339-119">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="86339-120">Editor de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="86339-120">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)