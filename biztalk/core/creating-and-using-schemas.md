---
title: "Creación y uso de esquemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas
- creating schemas
- schemas, generating
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f10275c5ed0b887907c7b26b7d1ce8ad5003b099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-using-schemas"></a><span data-ttu-id="9b5f1-102">Creación y uso de esquemas</span><span class="sxs-lookup"><span data-stu-id="9b5f1-102">Creating and Using Schemas</span></span>
<span data-ttu-id="9b5f1-103">El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) usa esquemas que se crean con un editor XML o con el Editor de BizTalk Server en Visual Studio (solo si usa el adaptador en una orquestación).</span><span class="sxs-lookup"><span data-stu-id="9b5f1-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) uses schemas that you create using an XML editor or the BizTalk Server Editor in Visual Studio (only when you use the adapter in an orchestration).</span></span> <span data-ttu-id="9b5f1-104">El esquema describe el tipo de información que espera.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-104">The schema describes the type of information that you expect.</span></span> <span data-ttu-id="9b5f1-105">Este tema contiene información para un controlador tanto de envío como de recepción.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-105">This topic contains information for both a send and a receive handler.</span></span>  
  
 <span data-ttu-id="9b5f1-106">Los esquemas que cree para su uso con el Adaptador de BizTalk para TIBCO Enterprise Message Service deben tener un espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-106">The schemas you create for use with BizTalk Adapter for TIBCO Enterprise Message Service must have a target namespace.</span></span> <span data-ttu-id="9b5f1-107">BizTalk Server requiere el espacio de nombres de destino debido a que es la clave que asocia una instancia de mensaje dada con una orquestación dada.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-107">BizTalk Server requires the target namespace because it is the key that associates a given message instance with a given orchestration.</span></span> <span data-ttu-id="9b5f1-108">Es decir, una orquestación se suscribe a cualquier mensaje que tenga un espacio de nombres de destino específico y se proporciona un mensaje XML entrante que tenga dicho espacio de nombres de destino a cada orquestación suscrita al mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-108">In other words, an orchestration subscribes to any message that has a specific target namespace, and an incoming XML message that has that target namespace is given to every orchestration that subscribed to the message.</span></span> <span data-ttu-id="9b5f1-109">Si un esquema de documento XML no tiene un espacio de nombres de destino, BizTalk Server usa el nombre del elemento raíz como clave.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-109">If an XML document schema does not have a target namespace, BizTalk Server uses the name of the root element as a key.</span></span>  
  
## <a name="generating-a-schema"></a><span data-ttu-id="9b5f1-110">Generar un esquema</span><span class="sxs-lookup"><span data-stu-id="9b5f1-110">Generating a Schema</span></span>  
 <span data-ttu-id="9b5f1-111">En los siguientes procedimientos se muestra cómo generar un esquema y cómo establecer el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-111">The following procedures show how to generate a schema and how to set the target namespace.</span></span>  
  
#### <a name="to-generate-a-schema-using-biztalk-editor"></a><span data-ttu-id="9b5f1-112">Para generar un esquema mediante el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9b5f1-112">To generate a schema using BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="9b5f1-113">En el Editor de BizTalk, abra el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-113">In the BizTalk Editor, open your project.</span></span>  
  
2.  <span data-ttu-id="9b5f1-114">En el Explorador de soluciones en la superior derecha, seleccione **agregar**y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-114">Under Solution Explorer in the upper-right, select **Add**, and then select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="9b5f1-115">En el **plantillas** panel, seleccione **generar esquemas**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-115">In the **Templates** pane, select **Generate Schemas**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="9b5f1-116">En el **generar esquemas** cuadro de diálogo, en la **tipo de documento** lista, seleccione **XML bien formado**.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-116">In the **Generate Schemas** dialog box, in the **Document type** list, select **Well-Formed XML**.</span></span>  
  
5.  <span data-ttu-id="9b5f1-117">Haga clic en **examinar** para buscar el archivo de entrada para el que desea generar un esquema y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-117">Click **Browse** to locate the input file for which you want to generate a schema, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9b5f1-118">A continuación, debe establecer el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-118">Next, you must set the target namespace.</span></span>  
  
#### <a name="to-set-the-target-namespace"></a><span data-ttu-id="9b5f1-119">Para establecer el espacio de nombres de destino</span><span class="sxs-lookup"><span data-stu-id="9b5f1-119">To set the target namespace</span></span>  
  
1.  <span data-ttu-id="9b5f1-120">En el Editor de BizTalk, abra el archivo de esquema, haga clic en  **\<esquema >**y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-120">In BizTalk Editor, open your schema file, right-click **\<schema>**, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9b5f1-121">En el **propiedades** panel, busque el **Namespace** campo y escriba un nombre, por ejemplo, `testNameSpace`.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-121">In the **Properties** pane, locate the **Namespace** field and type a name, for example, `testNameSpace`.</span></span>  
  
 <span data-ttu-id="9b5f1-122">A continuación, puede continuar con la orquestación mediante mensajes.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-122">You can then continue with your orchestration using messages.</span></span> <span data-ttu-id="9b5f1-123">Cuando se selecciona un mensaje, BizTalk Server encuentra una orquestación que usa un esquema con un espacio de nombres de destino establecido y se sigue el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="9b5f1-123">When a message is picked up, BizTalk Server finds an orchestration that uses a schema with a set target namespace, and the orchestration process is followed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5f1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b5f1-124">See Also</span></span>  
 [<span data-ttu-id="9b5f1-125">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="9b5f1-125">Developing Applications</span></span>](../core/developing-applications5.md)