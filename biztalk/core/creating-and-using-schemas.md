---
title: Crear y utilizar esquemas en TIBCO | Documentos de Microsoft
description: Utilice el Editor de BizTalk para crear un esquema para el adaptador de BizTalk para TIBCO Enterprise Message Service y establecer el espacio de nombres de destino en el esquema de BizTalk Server
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 707067ed0c48abb62d567098cd472b59bad302b0
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="create-and-use-tibco-schemas"></a><span data-ttu-id="7bfe8-103">Crear y utilizar esquemas TIBCO</span><span class="sxs-lookup"><span data-stu-id="7bfe8-103">Create and use TIBCO schemas</span></span>

## <a name="overview"></a><span data-ttu-id="7bfe8-104">Información general</span><span class="sxs-lookup"><span data-stu-id="7bfe8-104">Overview</span></span>
<span data-ttu-id="7bfe8-105">El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) usa esquemas que se crean con un editor XML o con el Editor de BizTalk Server en Visual Studio (solo si usa el adaptador en una orquestación).</span><span class="sxs-lookup"><span data-stu-id="7bfe8-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) uses schemas that you create using an XML editor or the BizTalk Server Editor in Visual Studio (only when you use the adapter in an orchestration).</span></span> <span data-ttu-id="7bfe8-106">El esquema describe el tipo de información que espera.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-106">The schema describes the type of information that you expect.</span></span> <span data-ttu-id="7bfe8-107">Este tema contiene información para un controlador tanto de envío como de recepción.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-107">This topic contains information for both a send and a receive handler.</span></span>  
  
<span data-ttu-id="7bfe8-108">Los esquemas que cree para su uso con el Adaptador de BizTalk para TIBCO Enterprise Message Service deben tener un espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-108">The schemas you create for use with BizTalk Adapter for TIBCO Enterprise Message Service must have a target namespace.</span></span> <span data-ttu-id="7bfe8-109">BizTalk Server requiere el espacio de nombres de destino debido a que es la clave que asocia una instancia de mensaje dada con una orquestación dada.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-109">BizTalk Server requires the target namespace because it is the key that associates a given message instance with a given orchestration.</span></span> <span data-ttu-id="7bfe8-110">Es decir, una orquestación se suscribe a cualquier mensaje que tenga un espacio de nombres de destino específico y se proporciona un mensaje XML entrante que tenga dicho espacio de nombres de destino a cada orquestación suscrita al mensaje.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-110">In other words, an orchestration subscribes to any message that has a specific target namespace, and an incoming XML message that has that target namespace is given to every orchestration that subscribed to the message.</span></span> <span data-ttu-id="7bfe8-111">Si un esquema de documento XML no tiene un espacio de nombres de destino, BizTalk Server usa el nombre del elemento raíz como clave.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-111">If an XML document schema does not have a target namespace, BizTalk Server uses the name of the root element as a key.</span></span>  

<span data-ttu-id="7bfe8-112">Los pasos siguientes muestran cómo generar un esquema y cómo establecer el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-112">The following steps show how to generate a schema, and how to set the target namespace.</span></span>  
  
## <a name="generate-a-schema"></a><span data-ttu-id="7bfe8-113">Generar un esquema</span><span class="sxs-lookup"><span data-stu-id="7bfe8-113">Generate a Schema</span></span>    
 
1.  <span data-ttu-id="7bfe8-114">En el Editor de BizTalk, abra el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-114">In the BizTalk Editor, open your project.</span></span>  
  
2.  <span data-ttu-id="7bfe8-115">En el Explorador de soluciones en la superior derecha, seleccione **agregar**y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-115">Under Solution Explorer in the upper-right, select **Add**, and then select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="7bfe8-116">En el **plantillas** panel, seleccione **generar esquemas**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-116">In the **Templates** pane, select **Generate Schemas**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="7bfe8-117">En el **generar esquemas** cuadro de diálogo, en la **tipo de documento** lista, seleccione **XML bien formado**.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-117">In the **Generate Schemas** dialog box, in the **Document type** list, select **Well-Formed XML**.</span></span>  
  
5.  <span data-ttu-id="7bfe8-118">Haga clic en **examinar** para buscar el archivo de entrada para el que desea generar un esquema y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-118">Click **Browse** to locate the input file for which you want to generate a schema, and then click **OK**.</span></span>  
  
<span data-ttu-id="7bfe8-119">A continuación, establezca el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-119">Next, set the target namespace.</span></span>  
  
## <a name="set-the-target-namespace"></a><span data-ttu-id="7bfe8-120">Establecer el espacio de nombres de destino</span><span class="sxs-lookup"><span data-stu-id="7bfe8-120">Set the target namespace</span></span>  
  
1.  <span data-ttu-id="7bfe8-121">En el Editor de BizTalk, abra el archivo de esquema, haga clic en  **\<esquema >**y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-121">In BizTalk Editor, open your schema file, right-click **\<schema>**, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="7bfe8-122">En el **propiedades** panel, busque el **Namespace** campo y escriba un nombre, por ejemplo, `testNameSpace`.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-122">In the **Properties** pane, locate the **Namespace** field and type a name, for example, `testNameSpace`.</span></span>  
  
 <span data-ttu-id="7bfe8-123">A continuación, puede continuar con la orquestación mediante mensajes.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-123">You can then continue with your orchestration using messages.</span></span> <span data-ttu-id="7bfe8-124">Cuando se selecciona un mensaje, BizTalk Server encuentra una orquestación que usa un esquema con un espacio de nombres de destino establecido y se sigue el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="7bfe8-124">When a message is picked up, BizTalk Server finds an orchestration that uses a schema with a set target namespace, and the orchestration process is followed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bfe8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bfe8-125">See Also</span></span>  
 [<span data-ttu-id="7bfe8-126">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7bfe8-126">Developing Applications</span></span>](../core/developing-applications5.md)