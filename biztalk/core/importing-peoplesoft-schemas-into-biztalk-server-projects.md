---
title: Importar esquemas de PeopleSoft en Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6af82459f8b51f3dfa73a52593db18d25365c2a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="import-peoplesoft-schemas-into-biztalk-server-projects"></a><span data-ttu-id="cef5c-102">Importar esquemas de PeopleSoft en proyectos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cef5c-102">Import PeopleSoft Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="cef5c-103">Cuando haya creado el sistema PeopleSoft Enterprise, puede examinar el servidor e importar esquemas en un proyecto BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cef5c-103">When you have created the PeopleSoft Enterprise system, you can browse the server and import schemas into a BizTalk Server project.</span></span>  
  
## <a name="browse-a-peoplesoft-server-system"></a><span data-ttu-id="cef5c-104">Examinar un sistema de servidor de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="cef5c-104">Browse a PeopleSoft Server System</span></span>  
  
1.  <span data-ttu-id="cef5c-105">Haga clic con el botón secundario en un proyecto de BizTalk Server y seleccione una de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="cef5c-105">Right-click a BizTalk Server project, and select one of the following options.</span></span>  
  
    -   <span data-ttu-id="cef5c-106">Si ya tiene un esquema generado para el objeto, seleccione **agregar**, haga clic en **Agregar esquema** y, a continuación, seleccione el esquema existente para agregar a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="cef5c-106">If you already have a schema generated for your object, select **Add**, click **Add Schema,** and then select the existing schema to add to your orchestration,.</span></span>  
  
    -   <span data-ttu-id="cef5c-107">Si no tiene un esquema generado para el objeto, seleccione **agregar**, a continuación, haga clic en **agregar elementos generados**y, a continuación, seleccione el adaptador.</span><span class="sxs-lookup"><span data-stu-id="cef5c-107">If you do not have a schema generated for your object, select **Add**, then click **Add Generated Items**, and then select the adapter.</span></span> <span data-ttu-id="cef5c-108">Este es el mismo nombre que escribió en el **AdapterProperties** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cef5c-108">This is the same name entered in the **AdapterProperties** dialog box.</span></span> <span data-ttu-id="cef5c-109">Para obtener más información, consulte "Cuadro de diálogo Propiedades de adaptador" en la Ayuda principal de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cef5c-109">For more information, see "Adapter Properties Dialog Box" in the main BizTalk help.</span></span>  
  
2.  <span data-ttu-id="cef5c-110">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="cef5c-110">Click Next.</span></span>  
  
     <span data-ttu-id="cef5c-111">El sistema PeopleSoft Enterprise aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="cef5c-111">The PeopleSoft Enterprise system appears in the browser.</span></span>  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a><span data-ttu-id="cef5c-112">Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="cef5c-112">Component Interfaces</span></span>  
 <span data-ttu-id="cef5c-113">En el **Interfaces de componentes** carpeta (CI), puede ver todas las interfaces de componentes disponibles en el sistema.</span><span class="sxs-lookup"><span data-stu-id="cef5c-113">In the **Component Interfaces** (CI) folder, you can view all the available component interfaces in the system.</span></span> <span data-ttu-id="cef5c-114">Una interfaz de componente declara el conjunto de métodos y propiedades que admite.</span><span class="sxs-lookup"><span data-stu-id="cef5c-114">A component interface declares the set of methods and properties that it supports.</span></span> <span data-ttu-id="cef5c-115">Una interfaz de componente no implementa el comportamiento o las propiedades.</span><span class="sxs-lookup"><span data-stu-id="cef5c-115">A component interface does not implement behavior or properties.</span></span> <span data-ttu-id="cef5c-116">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise expone métodos estándar, como CreateEx, DeleteOnly, Find, Get y UpdateEx.</span><span class="sxs-lookup"><span data-stu-id="cef5c-116">Microsoft BizTalk Adapter for PeopleSoft Enterprise exposes standard methods, for example, CreateEx, DeleteOnly, Find, Get, and UpdateEx.</span></span> <span data-ttu-id="cef5c-117">Para obtener una descripción de estos métodos, consulte [métodos de interfaz de componente de apéndice A:](../core/appendix-a-component-interface-methods.md).</span><span class="sxs-lookup"><span data-stu-id="cef5c-117">For a description of these methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
## <a name="generate-schemas"></a><span data-ttu-id="cef5c-118">Generar esquemas</span><span class="sxs-lookup"><span data-stu-id="cef5c-118">Generate Schemas</span></span>  
  
<span data-ttu-id="cef5c-119">Seleccione el elemento para el que desea importar esquemas: un **mensaje**, **consulta**, o **interfaz de componente**.</span><span class="sxs-lookup"><span data-stu-id="cef5c-119">Select the item for which you want to import schemas: a **Message**, **Query**, or **Component Interface**.</span></span>  <span data-ttu-id="cef5c-120">BizTalk Server genera los esquemas para el elemento seleccionado y los importa en un proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cef5c-120">BizTalk Server generates the schemas for the selected item and imports them into a BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cef5c-121">Si cambia las definiciones de objeto de servidor, debe volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="cef5c-121">If the server object definitions change, you must regenerate the schema to update the data it contains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef5c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cef5c-122">See Also</span></span>  
 [<span data-ttu-id="cef5c-123">Creación de controladores de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="cef5c-123">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)