---
title: ¿Qué es un perfil de seguimiento? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, about tracking profiles
- tracking profiles, Tracking Profile Editor
- Tracking Profile Editor, tracking profiles
- tracking profiles
ms.assetid: b579bdc4-7c69-4fa0-bbc1-f98170c13d4f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9dbcdd4ff93749de5059b80fecfa140e41df422
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977880"
---
# <a name="what-is-a-tracking-profile"></a><span data-ttu-id="3d803-103">¿Qué es un perfil de seguimiento?</span><span class="sxs-lookup"><span data-stu-id="3d803-103">What Is a Tracking Profile?</span></span>
<span data-ttu-id="3d803-104">Un perfil es un conjunto de características que definen un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="3d803-104">A profile is a set of characteristics that define a business process.</span></span> <span data-ttu-id="3d803-105">Un perfil de seguimiento contiene la asignación de estas características de una actividad a orquestaciones y puertos.</span><span class="sxs-lookup"><span data-stu-id="3d803-105">A tracking profile contains the mapping of these characteristics from an activity to orchestrations and ports.</span></span> <span data-ttu-id="3d803-106">Un perfil de seguimiento es un archivo con extensión .btt de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="3d803-106">A tracking profile is a file with a .btt file name extension.</span></span>  
  
## <a name="using-tracking-profiles-in-the-tpe"></a><span data-ttu-id="3d803-107">Utilizar perfiles de seguimiento en el TPE</span><span class="sxs-lookup"><span data-stu-id="3d803-107">Using tracking profiles in the TPE</span></span>  
 <span data-ttu-id="3d803-108">Los usuarios del TPE crean una asignación, o perfil de seguimiento, entre elementos de una actividad de BAM y los orígenes de solución de BizTalk Server para aquellos elementos.</span><span class="sxs-lookup"><span data-stu-id="3d803-108">Users of the TPE create a map, or tracking profile, between items in a BAM activity and the BizTalk Server solution sources for those items.</span></span> <span data-ttu-id="3d803-109">Las actividades de BAM constan de los hitos y de los datos contextuales que forman la “lista de visibilidad”, y definen en la empresa una unidad de trabajo por la que se guía el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d803-109">BAM activities consist of the milestones and contextual data that make up the "visibility wish-list" and define a unit of work in the business that the tracking profile follows.</span></span> <span data-ttu-id="3d803-110">Para obtener más información acerca de las actividades, consulte [implementar actividades de BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md).</span><span class="sxs-lookup"><span data-stu-id="3d803-110">For more information about activities, see [Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md).</span></span>  
  
 <span data-ttu-id="3d803-111">Cuando se crea un perfil de seguimiento utilizando el TPE, se utilizan los objetos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d803-111">When you create a tracking profile using the TPE, you are working with the following objects:</span></span>  
  
- <span data-ttu-id="3d803-112">Actividades de BAM</span><span class="sxs-lookup"><span data-stu-id="3d803-112">BAM activities</span></span>  
  
- <span data-ttu-id="3d803-113">Orquestaciones de BizTalk en ensamblados implementados</span><span class="sxs-lookup"><span data-stu-id="3d803-113">BizTalk orchestrations in deployed assemblies</span></span>  
  
- <span data-ttu-id="3d803-114">Puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="3d803-114">Receive and send ports</span></span>  
  
- <span data-ttu-id="3d803-115">Esquemas de mensaje en ensamblados implementados</span><span class="sxs-lookup"><span data-stu-id="3d803-115">Message schemas in deployed assemblies</span></span>  
  
- <span data-ttu-id="3d803-116">Propiedades de contexto</span><span class="sxs-lookup"><span data-stu-id="3d803-116">Context properties</span></span>  
  
- <span data-ttu-id="3d803-117">Base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="3d803-117">BAM Primary Import database</span></span>  
  
- <span data-ttu-id="3d803-118">Base de datos de administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3d803-118">BizTalk Management database</span></span>  
  
- <span data-ttu-id="3d803-119">Base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3d803-119">BizTalk Tracking database</span></span>  
  
  <span data-ttu-id="3d803-120">Para definir la extracción de datos desde una orquestación, coloque los elementos de esquemas de mensaje, formas de orquestación y propiedades de contexto en las carpetas de hitos económicos (evento) y de elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="3d803-120">You define the data extraction from an orchestration by dropping items from message schemas, orchestration shapes, and context properties into business milestone (event) and data item folders.</span></span>  
  
  <span data-ttu-id="3d803-121">Por ejemplo, considere una actividad de BAM que incluya un hito llamado Pedido recibido y que tenga un puerto de mensajería por el que fluyen los pedidos para iniciar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3d803-121">For example, consider a BAM activity that includes a milestone called PO Received and has a Messaging port through which purchase orders flow to initiate processing.</span></span> <span data-ttu-id="3d803-122">Los programadores pueden asociar el hito `PO Received` a una propiedad de mensajería de BizTalk denominada `PortEndTime` para el puerto en su solución.</span><span class="sxs-lookup"><span data-stu-id="3d803-122">Developers can associate the `PO Received` milestone with a BizTalk Messaging property called `PortEndTime` for the port in their solution.</span></span> <span data-ttu-id="3d803-123">Semánticamente, indica que el Pedido se recibe satisfactoriamente cuando el puerto de recepción concluye su acción y rellena la propiedad `PortEndTime`.</span><span class="sxs-lookup"><span data-stu-id="3d803-123">Semantically, this indicates that the PO is successfully received once the receive port concludes its action and populates the `PortEndTime` property.</span></span> <span data-ttu-id="3d803-124">El programador realiza ésta y otras asignaciones para completar el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d803-124">The developer makes this and any other mappings to complete the tracking profile.</span></span> <span data-ttu-id="3d803-125">Se asignarán todos los elementos de la actividad siempre que tengan un origen de BizTalk Server. Por el contrario, si el origen de los datos o eventos es un proceso externo al tiempo de ejecución de BizTalk Server, los elementos se dejarán sin asignar, para ser completados directamente por llamadas de API.</span><span class="sxs-lookup"><span data-stu-id="3d803-125">All items in the activity are mapped if they have a BizTalk Server source, or are left unmapped to be populated by API calls directly if the source of the data or event is from a process outside of BizTalk Server’s run-time environment.</span></span>  
  
  <span data-ttu-id="3d803-126">Aunque cada panel o vista del TPE dispone de una función exclusiva, todas las vistas y carpetas tienen características de exploración similares para ayudarle a buscar y controlar la información.</span><span class="sxs-lookup"><span data-stu-id="3d803-126">Although each pane or view in the TPE has a unique function, all the views and folders have similar navigational features to help you find and manipulate information.</span></span>  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a><span data-ttu-id="3d803-127">¿Quién utiliza los perfiles de seguimiento y el TPE?</span><span class="sxs-lookup"><span data-stu-id="3d803-127">Who uses tracking profiles and the TPE?</span></span>  
 <span data-ttu-id="3d803-128">Los usuarios implicados en el desarrollo de integración empresarial utilizan los perfiles de seguimiento y el TPE para asignar orígenes de eventos de BizTalk Server a actividades de destino de BAM.</span><span class="sxs-lookup"><span data-stu-id="3d803-128">Users involved with enterprise integration development use tracking profiles and the TPE to map BizTalk Server event sources to BAM target activities.</span></span> <span data-ttu-id="3d803-129">El archivo .btt resultante se entrega a la implementación de TI para su implantación.</span><span class="sxs-lookup"><span data-stu-id="3d803-129">The resulting .btt file is handed off to IT Implementation for deployment.</span></span>  
  
 <span data-ttu-id="3d803-130">Por lo general, los usuarios de implementación de TI aplicarán los perfiles de seguimiento utilizando herramientas de línea de comandos (BTTDeploy).</span><span class="sxs-lookup"><span data-stu-id="3d803-130">IT Implementation users will typically apply tracking profiles using command-line tools (BTTDeploy).</span></span> <span data-ttu-id="3d803-131">El usuario de TI también puede utilizar el TPE directamente para aplicar el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d803-131">The IT user can also use the TPE directly to apply the tracking profile.</span></span>  
  
 <span data-ttu-id="3d803-132">Los usuarios de operaciones de TI pueden ser responsables de las actualizaciones periódicas de los perfiles de seguimiento de forma programada (incluidas las operaciones de bases de datos como copia de seguridad y restauración), especialmente como resultado de cambios en los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="3d803-132">Users in IT Operations may be responsible for periodic updates to tracking profiles on a scheduled basis (including any database operations required, such as backup and restore), especially as a result of changes in business requirements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d803-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d803-133">See Also</span></span>  
 [<span data-ttu-id="3d803-134">Editor de perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3d803-134">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)