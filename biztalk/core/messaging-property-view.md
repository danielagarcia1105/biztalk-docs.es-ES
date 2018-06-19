---
title: Vista propiedad de mensajería | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- message schemas, properties
- Messaging Property view [Tracking Profile Editor]
- Tracking Profile Editor, Messaging Property view
- message schemas, XML messages
ms.assetid: 80d040e9-d58b-41d1-b26d-19aff4d3126b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1be1498cd3766863b9f5b2e3a37ae419d4bafc8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262900"
---
# <a name="messaging-property-view"></a><span data-ttu-id="e709a-102">Vista Propiedad de mensajería</span><span class="sxs-lookup"><span data-stu-id="e709a-102">Messaging Property View</span></span>
<span data-ttu-id="e709a-103">La vista Propiedad de mensajería muestra el esquema del mensaje XML asociado a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e709a-103">The Messaging Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="e709a-104">La vista está disponible desde el menú contextual para algunas de las formas de la vista Programación de orquestación.</span><span class="sxs-lookup"><span data-stu-id="e709a-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-messaging-properties"></a><span data-ttu-id="e709a-105">Trabajar con propiedades de mensajería</span><span class="sxs-lookup"><span data-stu-id="e709a-105">Working with messaging properties</span></span>  
 <span data-ttu-id="e709a-106">Seleccione la vista de la propiedad de mensajería, haga clic en el **Seleccionar origen de eventos** botón y haciendo clic en el **Seleccionar propiedad de mensaje** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="e709a-106">You select your Messaging Property view by clicking the **Select Event Source** button and clicking the **Select Message Property** menu item.</span></span> <span data-ttu-id="e709a-107">Se elige una propiedad de mensajes de la que se selecciona un esquema.</span><span class="sxs-lookup"><span data-stu-id="e709a-107">You then choose a message property from which to select a schema.</span></span> <span data-ttu-id="e709a-108">Una vez seleccionado el esquema, puede arrastrar los elementos de este esquema a las carpetas de elementos de datos de la actividad. De esta manera, se indica que desea extraer en esta acción esos datos específicos de las expresiones XPath específicas del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e709a-108">Once you select the schema, you can drag elements from this schema to the data item folders of the activity, thus indicating that you want to extract that particular data from specific XPath expressions inside the message at this action.</span></span>  
  
 <span data-ttu-id="e709a-109">Puede abrir las vistas de propiedad de mensajes desde la programación de orquestación haciendo clic con el botón secundario en una forma que contenga una carga de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e709a-109">You can open message property views from the Orchestration Schedule view by right-clicking a shape that contains a message payload.</span></span> <span data-ttu-id="e709a-110">De esta manera, se abrirá el menú contextual desde el que puede hacer clic en el elemento de menú Carga de mensaje para recuperar una lista de las cargas asociadas con la forma.</span><span class="sxs-lookup"><span data-stu-id="e709a-110">This will open a context menu from which you can click the Message Payload menu item to retrieve a list of payloads associated with the shape.</span></span>  
  
 <span data-ttu-id="e709a-111">La lista de propiedades de mensajes disponibles puede ser amplia.</span><span class="sxs-lookup"><span data-stu-id="e709a-111">The list of available message properties can be extensive.</span></span> <span data-ttu-id="e709a-112">Si conoce parte del nombre de la orquestación que está buscando, puede escribirla en el **en cadena** cuadro de texto y haga clic en el **búsqueda** botón.</span><span class="sxs-lookup"><span data-stu-id="e709a-112">If you know part of the name of the orchestration for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="e709a-113">De este modo, se seleccionarán solo las propiedades de mensajes que contienen la cadena parcial que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="e709a-113">This will select only those message properties that contain the partial string you have entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e709a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e709a-114">See Also</span></span>  
 <span data-ttu-id="e709a-115">[¿Qué es la vista del origen de eventos?](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="e709a-115">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="e709a-116">Editor de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e709a-116">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)