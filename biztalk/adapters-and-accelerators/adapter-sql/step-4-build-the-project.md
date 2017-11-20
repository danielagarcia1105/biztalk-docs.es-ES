---
title: 'Paso 4: Generar el proyecto | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d88b1407-ecdd-4dbf-90da-02dc4781568c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f1d6fa03b4a686537ef04f0121c1ae168e525ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-build-the-project"></a><span data-ttu-id="b7a65-102">Paso 4: Generar el proyecto</span><span class="sxs-lookup"><span data-stu-id="b7a65-102">Step 4: Build the Project</span></span>
<span data-ttu-id="b7a65-103">![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="b7a65-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="b7a65-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="b7a65-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="b7a65-105">**Objetivo:** en este paso, compilará el proyecto de orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b7a65-105">**Objective:** In this step, you compile the BizTalk orchestration project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b7a65-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b7a65-106">Prerequisites</span></span>  
 <span data-ttu-id="b7a65-107">Debe haber completado [paso 3: enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span><span class="sxs-lookup"><span data-stu-id="b7a65-107">You must have completed [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  
  
### <a name="to-build-the-biztalk-orchestration-project"></a><span data-ttu-id="b7a65-108">Para compilar el proyecto de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b7a65-108">To build the BizTalk orchestration project</span></span>  
  
1.  <span data-ttu-id="b7a65-109">En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b7a65-109">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b7a65-110">En el cuadro de diálogo páginas de propiedades, en el panel del árbol, expanda **propiedades comunes**, haga clic en **ensamblado**y, a continuación, en la lista de propiedades, haga clic en el **archivo de clave de ensamblado** puntos suspensivos **[...]** .</span><span class="sxs-lookup"><span data-stu-id="b7a65-110">In the property pages dialog box, in the tree pane, expand **Common Properties**, click **Assembly**, and then in the properties list, click the **Assembly Key File** ellipsis **[…]**.</span></span>  
  
3.  <span data-ttu-id="b7a65-111">Especifique una ruta de acceso al archivo de clave de ensamblado que creó como se describe en [los requisitos previos para crear aplicaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="b7a65-111">Specify a path to the assembly key file you created as described in [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md), and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="b7a65-112">En el cuadro de diálogo páginas de propiedades, en el panel del árbol, expanda **propiedades de configuración**, haga clic en **implementación**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7a65-112">In the property pages dialog box, in the tree pane, expand **Configuration Properties**, click **Deployment**, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="b7a65-113">Para el **nombre de la aplicación** propiedad, escriba `SampleApplication`.</span><span class="sxs-lookup"><span data-stu-id="b7a65-113">For the **Application Name** property, type `SampleApplication`.</span></span>  
  
    2.  <span data-ttu-id="b7a65-114">Para el **volver a implementar** propiedad, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="b7a65-114">For the **Redeploy** property, select **True**.</span></span>  
  
     <span data-ttu-id="b7a65-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7a65-115">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b7a65-116">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="b7a65-116">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="b7a65-117">En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="b7a65-117">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
     <span data-ttu-id="b7a65-118">El panel de salida en la parte inferior de la pantalla se lea: **compilar: 3 se ha realizado correctamente o actualizados, 0 incorrectos, 0 omitidos.**</span><span class="sxs-lookup"><span data-stu-id="b7a65-118">The Output pane at the bottom of the screen should read: **Build: 3 succeeded or up-to-date, 0 failed, 0 skipped.**</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b7a65-119">Síntesis</span><span class="sxs-lookup"><span data-stu-id="b7a65-119">What did I just do?</span></span>  
 <span data-ttu-id="b7a65-120">En este paso, ha compilado la solución que contiene el proyecto de BizTalk y dos proyectos de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="b7a65-120">In this step, you compiled the solution containing the BizTalk project and two class library projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b7a65-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b7a65-121">Next Steps</span></span>  
 <span data-ttu-id="b7a65-122">Implementar la solución, como se describe en [lección 5: implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md).</span><span class="sxs-lookup"><span data-stu-id="b7a65-122">You deploy the solution, as described in [Lesson 5: Deploy the Solution](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a65-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7a65-123">See Also</span></span>  
 <span data-ttu-id="b7a65-124">[Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span><span class="sxs-lookup"><span data-stu-id="b7a65-124">[Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span></span>  
 [<span data-ttu-id="b7a65-125">Lección 4: Realizar una operación de inserción en la tabla de orden de compra</span><span class="sxs-lookup"><span data-stu-id="b7a65-125">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)