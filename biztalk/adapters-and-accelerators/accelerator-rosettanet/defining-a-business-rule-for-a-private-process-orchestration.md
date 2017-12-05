---
title: "Definir una regla de negocios para una orquestación de procesos privados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, policies
- vocabularies, saving
- private processes, orchestrations
- business rules, private processes
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- policies, deploying
- vocabularies, creating
- orchestrations, private-process orchestrations
- private processes, customizing
- policies, publishing
- business rules, Set elements
- creating, policies
- customizing private processes
- Set elements
- business rules, orchestrations
- publishing, vocabularies
- vocabularies, publishing
- creating, rules
- business rules, Get elements
- policies, saving
- publishing, policies
- Get elements
- orchestrations, business rules
- rules
- private processes, business rules
- policies, creating
ms.assetid: 5d2b0257-1b15-482b-a562-798b808e9a2d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dd0ebb22bcf6253604e4e8bf7fd858deb776b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a><span data-ttu-id="f783d-102">Definir una regla de negocios para una orquestación de procesos privado</span><span class="sxs-lookup"><span data-stu-id="f783d-102">Defining a Business Rule for a Private Process Orchestration</span></span>
<span data-ttu-id="f783d-103">Puede definir una regla de negocios para su uso en un proceso privado de confirmación.</span><span class="sxs-lookup"><span data-stu-id="f783d-103">You can define a business rule for use in an acknowledgement private process.</span></span> <span data-ttu-id="f783d-104">Esto permite modificar la regla de negocios dinámicamente sin detener la orquestación de procesos privado.</span><span class="sxs-lookup"><span data-stu-id="f783d-104">This lets you to modify the business rule dynamically without stopping the private-process orchestration.</span></span> <span data-ttu-id="f783d-105">Este proceso utiliza el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="f783d-105">This process uses the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Business Rule Engine.</span></span> <span data-ttu-id="f783d-106">Este proceso implica los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f783d-106">This process involves the following steps:</span></span>  
  
1.  <span data-ttu-id="f783d-107">Agregar un nuevo vocabulario.</span><span class="sxs-lookup"><span data-stu-id="f783d-107">Adding a new vocabulary.</span></span> <span data-ttu-id="f783d-108">Esto implica definir valor de constante de al menos un vocabulario.</span><span class="sxs-lookup"><span data-stu-id="f783d-108">This involves defining at least one vocabulary constant value.</span></span> <span data-ttu-id="f783d-109">Esto establece un umbral de regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="f783d-109">This sets a business-rule threshold.</span></span> <span data-ttu-id="f783d-110">También implica la definición de documento XML `Get` y `Set` elementos.</span><span class="sxs-lookup"><span data-stu-id="f783d-110">It also involves defining XML document `Get` and `Set` elements.</span></span> <span data-ttu-id="f783d-111">Esto establece cómo [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] usa el umbral.</span><span class="sxs-lookup"><span data-stu-id="f783d-111">This establishes how [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] uses the threshold.</span></span>  
  
2.  <span data-ttu-id="f783d-112">Agregar una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="f783d-112">Adding a new policy.</span></span> <span data-ttu-id="f783d-113">Esto implica la creación de una directiva, crear un conjunto de reglas y, a continuación, guardar, publicar e implementar la directiva.</span><span class="sxs-lookup"><span data-stu-id="f783d-113">This involves creating a policy, creating a set of rules, and then saving, publishing, and deploying the policy.</span></span>  
  
3.  <span data-ttu-id="f783d-114">Al llamar a la regla de negocios de la orquestación de procesos privado.</span><span class="sxs-lookup"><span data-stu-id="f783d-114">Calling the business rule from the private-process orchestration.</span></span> <span data-ttu-id="f783d-115">Esto implica agregar un **reglas de llamada** forma a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f783d-115">This involves adding a **Call Rules** shape to the orchestration.</span></span>  
  
 <span data-ttu-id="f783d-116">El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye un ejemplo de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] directiva empresarial, samplebtarnpolicy.xml, en \< *unidad*\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\PipAutomation\3A4.</span><span class="sxs-lookup"><span data-stu-id="f783d-116">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a sample [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] business policy, samplebtarnpolicy.xml, in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4.</span></span> <span data-ttu-id="f783d-117">Para obtener más información, consulte [directiva empresarial de BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f783d-117">For more information, see [Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).</span></span>  
  
 <span data-ttu-id="f783d-118">PIP3A4PrivateResponder.odx orquestación es una orquestación de procesos privados de ejemplo que muestra cómo implementar un proceso de interfaz de socio (PIP)-procesos privados Respondedor específico que incorpore una regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="f783d-118">PIP3A4PrivateResponder.odx orchestration is a sample private-process orchestration that demonstrates how to implement a Partner Interface Process (PIP)-specific responder private process incorporating a business rule.</span></span> <span data-ttu-id="f783d-119">Para obtener más información acerca de este ejemplo, vea [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span><span class="sxs-lookup"><span data-stu-id="f783d-119">For more information about this sample, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
 <span data-ttu-id="f783d-120">Para obtener más información acerca de vocabularios y directivas, vea el tema "Desarrollar con las reglas de negocios" en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f783d-120">For more information about vocabularies and policies, see the "Developing with Business Rules" topic in BizTalk Server.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="f783d-121">Para agregar un vocabulario nuevo</span><span class="sxs-lookup"><span data-stu-id="f783d-121">To add a new vocabulary</span></span>  
  
1.  <span data-ttu-id="f783d-122">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="f783d-122">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="f783d-123">Si el **Abrir almacén de reglas** abre el cuadro de diálogo, seleccione la **motor de reglas de BizTalk** base de datos que ha configurado en el servidor actual y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-123">If the **Open Rule Store** dialog box opens, select the **BizTalk Rule Engine** database that you set up on the current server, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="f783d-124">En [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Compositor de reglas de negocios, en el panel Explorador de hechos, haga clic en **vocabularios**y, a continuación, haga clic en **Agregar nuevo vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="f783d-124">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Business Rule Composer, in the Facts Explorer pane, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4.  <span data-ttu-id="f783d-125">En el panel de propiedades (parte inferior izquierda), establezca el **nombre** propiedad en el nombre del vocabulario adecuado y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f783d-125">In the Property pane (lower left), set the **Name** property to the name of the appropriate vocabulary, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="f783d-126">Expanda la carpeta de vocabulario que acaba de crear, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="f783d-126">Expand the vocabulary folder you just created, right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
6.  <span data-ttu-id="f783d-127">En la página **Asistente para definición de vocabulario** , seleccione **Valor, rango de valores o conjunto de valores constantes**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f783d-127">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="f783d-128">En el **valor constante, rango de valores o conjunto de valores** página, en la **nombre de definición de** , escriba el nombre del valor de constante de vocabulario adecuado, como **máximo permitido de cantidad** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f783d-128">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition Name** box, type the name of the appropriate vocabulary constant value, such as **Maximum Quantity Allowed**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="f783d-129">En el **definir un valor constante** página, en la **campo de valor** , escriba el umbral y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-129">On the **Define a Constant Value** page, in the **Value Field** box, type the threshold, and then click **Finish**.</span></span>  
  
### <a name="to-define-get-and-set-elements"></a><span data-ttu-id="f783d-130">Para definir Get y elementos del conjunto</span><span class="sxs-lookup"><span data-stu-id="f783d-130">To define Get and Set elements</span></span>  
  
1.  <span data-ttu-id="f783d-131">En el Compositor de reglas de negocios, en el panel Explorador de hechos, en la carpeta de vocabulario creada en el vínculo "para agregar un nuevo procedimiento de vocabulario", haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="f783d-131">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder created in the "To add a new vocabulary procedure", right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="f783d-132">En el **Asistente para definición de vocabulario** página, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f783d-132">On the **Vocabulary Definition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f783d-133">En el **atributo o elemento de documento XML** página, en el cuadro de texto Nombre de definición, escriba un nombre para un **obtener** elemento.</span><span class="sxs-lookup"><span data-stu-id="f783d-133">On the **XML Document Element or Attribute** page, in the Definition Name text box, type a name for a **Get** element.</span></span>  
  
4.  <span data-ttu-id="f783d-134">Haga clic en **examinar**, desplácese a la ubicación del esquema que desea usar, seleccione el archivo de esquema y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f783d-134">Click **Browse**, move to the location of the schema that you want to use, select the schema file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f783d-135">Si el **seleccionar el nodo raíz** se abre la página, seleccione el nodo raíz para examinar.</span><span class="sxs-lookup"><span data-stu-id="f783d-135">If the **Select Root Node** page opens, select the root node to browse.</span></span>  
  
6.  <span data-ttu-id="f783d-136">En el **Seleccionar enlace** página, desplazarse al campo para el que desea definir el umbral y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-136">On the **Select Binding** page, move to the field for which you want to define the threshold, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="f783d-137">En el **tipo de documento** , escriba el nombre del documento.</span><span class="sxs-lookup"><span data-stu-id="f783d-137">In the **Document Type** box, type the name of the document.</span></span>  
  
8.  <span data-ttu-id="f783d-138">En el **tipo de operación** sección, seleccione **realizar operación "Get"**.</span><span class="sxs-lookup"><span data-stu-id="f783d-138">In the **Operation Type** section, select **Perform “Get” operation**.</span></span>  
  
9. <span data-ttu-id="f783d-139">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-139">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="f783d-140">Repita estos pasos para definir una o varias `Set` operaciones, seleccionadas **realizar operación "Set"** para el **tipo de operación**.</span><span class="sxs-lookup"><span data-stu-id="f783d-140">Repeat these steps to define one or more `Set` operations, select **Perform “Set” operation** for the **Operation Type**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="f783d-141">Para guardar y publicar el vocabulario</span><span class="sxs-lookup"><span data-stu-id="f783d-141">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="f783d-142">En el Compositor de reglas de negocios, en el panel Explorador de hechos, en la carpeta de vocabulario que ha creado, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-142">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="f783d-143">En el panel Explorador de hechos, en la carpeta 3A4PurchaseOrderVocabulary, haga clic en **versión 1.0**y, a continuación, seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-143">In the Facts Explorer pane, under the 3A4PurchaseOrderVocabulary folder, right-click **Version 1.0**, and then select **Publish**.</span></span>  
  
### <a name="to-add-a-new-policy-and-rules"></a><span data-ttu-id="f783d-144">Para agregar una nueva directiva y reglas</span><span class="sxs-lookup"><span data-stu-id="f783d-144">To add a new policy and rules</span></span>  
  
1.  <span data-ttu-id="f783d-145">En el Compositor de reglas de negocios, en el panel Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="f783d-145">In Business Rule Composer, in the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
2.  <span data-ttu-id="f783d-146">Haga clic en **Policy1**.</span><span class="sxs-lookup"><span data-stu-id="f783d-146">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="f783d-147">En el panel Propiedades, establezca la **nombre** propiedad en el nombre de la directiva adecuada.</span><span class="sxs-lookup"><span data-stu-id="f783d-147">In the Property pane, set the **Name** property to the appropriate policy name.</span></span>  
  
4.  <span data-ttu-id="f783d-148">En el panel Explorador de directivas, bajo la carpeta para la nueva directiva, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="f783d-148">In the Policy Explorer pane, under the folder for the new policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span>  
  
5.  <span data-ttu-id="f783d-149">Haga clic en **Rule1**.</span><span class="sxs-lookup"><span data-stu-id="f783d-149">Click **Rule1**.</span></span>  
  
6.  <span data-ttu-id="f783d-150">En el panel Propiedades, establezca la **nombre** propiedad para el nombre de la regla desee y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f783d-150">In the Property pane, set the **Name** property to the rule name you want, and then press **Enter**.</span></span>  
  
7.  <span data-ttu-id="f783d-151">En el Compositor de reglas, en la **IF** panel, haga clic en **condiciones**y, a continuación, seleccione una condición lógica, si procede.</span><span class="sxs-lookup"><span data-stu-id="f783d-151">In the Rule Composer, under the **IF** pane, right-click **Conditions**, and then select a logical condition, if appropriate.</span></span>  
  
8.  <span data-ttu-id="f783d-152">En el panel Explorador de hechos, en **vocabularios**, expanda **predicados**, expanda **versión 1.0 - publicada**, seleccione el predicado que desee, arrástrelo hasta la superficie del compositor, y, a continuación, colóquela en **condiciones** o el operador lógico.</span><span class="sxs-lookup"><span data-stu-id="f783d-152">In the Facts Explorer pane, under **Vocabularies**, expand **Predicates**, expand **Version 1.0 - Published**, select the predicate you want, drag it to the composer surface, and then drop it on **Conditions** or the logical operator.</span></span>  
  
9. <span data-ttu-id="f783d-153">En el panel Explorador de hechos, en la carpeta vocabularios, expanda el vocabulario que creó, **versión 1.0 - publicada**, seleccione un `Get` o `Set` elemento, arrástrelo hasta la superficie del compositor y colóquela en **argumento1**.</span><span class="sxs-lookup"><span data-stu-id="f783d-153">In the Facts Explorer pane, under the Vocabularies folder, expand the vocabulary that you created, expand **Version 1.0 - Published**, select a `Get` or `Set` element, drag it to the composer surface, and drop it on **argument1**.</span></span>  
  
10. <span data-ttu-id="f783d-154">En la carpeta de vocabulario, seleccione un `Get` o `Set` elemento, arrástrelo hasta la superficie del compositor y colóquela en **argumento2**.</span><span class="sxs-lookup"><span data-stu-id="f783d-154">Under the vocabulary folder, select a `Get` or `Set` element, drag it to the composer surface and drop it on **argument2**.</span></span>  
  
11. <span data-ttu-id="f783d-155">En la carpeta de vocabulario, seleccione un `Set` elemento, arrástrelo hasta la superficie del compositor y colóquela en la **acciones** cuadro en el panel entonces.</span><span class="sxs-lookup"><span data-stu-id="f783d-155">Under the vocabulary folder, select a `Set` element, drag it to the composer surface, and drop it in the **Actions** box in the THEN pane.</span></span>  
  
12. <span data-ttu-id="f783d-156">Si una variable está asociada a la `Set` elemento, haga clic en la variable, realizar cambios según corresponda y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f783d-156">If a variable is associated with the `Set` element, click the variable, make changes as appropriate, and then press **Enter**.</span></span> <span data-ttu-id="f783d-157">Si es necesario, repita con otros `Set` elementos.</span><span class="sxs-lookup"><span data-stu-id="f783d-157">If appropriate, repeat with other `Set` elements.</span></span>  
  
### <a name="to-save-publish-and-deploy-the-policy"></a><span data-ttu-id="f783d-158">Para guardar, publicar e implementar la directiva</span><span class="sxs-lookup"><span data-stu-id="f783d-158">To save, publish, and deploy the policy</span></span>  
  
1.  <span data-ttu-id="f783d-159">Cuando haya terminado de definir las reglas, en el Compositor de reglas de negocios, en el panel Explorador de directivas, en la carpeta de directiva que ha creado, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-159">When you have finished defining the rules, in Business Rule Composer, in the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="f783d-160">En el panel Explorador de directivas, en la carpeta de directiva que ha creado, haga clic en **versión 1.0**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-160">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Publish**.</span></span>  
  
3.  <span data-ttu-id="f783d-161">En el panel Explorador de directivas, en la carpeta de directiva que ha creado, haga clic en **versión 1.0**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-161">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Deploy**.</span></span>  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a><span data-ttu-id="f783d-162">Llamar a la regla de negocios desde la orquestación</span><span class="sxs-lookup"><span data-stu-id="f783d-162">To call the business rule from the orchestration</span></span>  
  
1.  <span data-ttu-id="f783d-163">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="f783d-163">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="f783d-164">En el **archivo** menú, seleccione Abrir y, a continuación, haga clic en **proyecto/solución**.</span><span class="sxs-lookup"><span data-stu-id="f783d-164">On the **File** menu, point to Open, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="f783d-165">Busque la solución que contiene la orquestación que se debe llamar a la regla de negocios de y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f783d-165">Locate the solution that contains the orchestration that you must call the business rule from, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="f783d-166">Haga clic en **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="f783d-166">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
5.  <span data-ttu-id="f783d-167">Expanda **Variables**.</span><span class="sxs-lookup"><span data-stu-id="f783d-167">Expand **Variables**.</span></span> <span data-ttu-id="f783d-168">Asegúrese de que la lista de variables de orquestación contiene una variable que corresponde a cada parámetro de la directiva empresarial que se llame desde la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f783d-168">Make sure that the orchestration variable list contains a variable that corresponds to each parameter in the business policy that you call from the orchestration.</span></span> <span data-ttu-id="f783d-169">Asegúrese de que la variable tiene el mismo tipo que el parámetro de directiva.</span><span class="sxs-lookup"><span data-stu-id="f783d-169">Make sure that the variable has the same type as the policy parameter.</span></span> <span data-ttu-id="f783d-170">Si la lista no contiene una variable de orquestación para cada parámetro de la directiva, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**.</span><span class="sxs-lookup"><span data-stu-id="f783d-170">If the list does not contain an orchestration variable for each policy parameter, right-click **Variables**, and then click **New Variable**.</span></span> <span data-ttu-id="f783d-171">En la vista de orquestación, escriba un nombre de variable y, a continuación, en la ventana Propiedades, escriba el tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f783d-171">In Orchestration View, type a variable name, and then in the Properties window, enter the type of the parameter.</span></span>  
  
6.  <span data-ttu-id="f783d-172">Desde el **cuadro de herramientas**, arrastre un **reglas de llamada** dar forma a la superficie de diseño de orquestación y colóquela en la **recepción** forma.</span><span class="sxs-lookup"><span data-stu-id="f783d-172">From the **Toolbox**, drag a **Call Rules** shape to the orchestration design surface, and then drop it under the **Receive** shape.</span></span>  
  
7.  <span data-ttu-id="f783d-173">Haga doble clic en el **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="f783d-173">Double-click the **Call Rules** shape.</span></span>  
  
8.  <span data-ttu-id="f783d-174">En el **seleccione la directiva empresarial que se va a llamar a** , seleccione la directiva empresarial en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f783d-174">In the **Select the business policy you wish to call** box, select the business policy from the drop-down list.</span></span>  
  
9. <span data-ttu-id="f783d-175">Para el primer parámetro que se muestra, para **nombre de parámetro**, seleccione un nombre de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f783d-175">For the first parameter shown, for **Parameter Name**, select a name from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f783d-176">BTARN rellena la **parámetro Policy** lista con todos los parámetros en la directiva empresarial.</span><span class="sxs-lookup"><span data-stu-id="f783d-176">BTARN populates the **Policy Parameter** list with all the parameters in the business policy.</span></span> <span data-ttu-id="f783d-177">Para cada parámetro en la lista, BTARN entra en un valor en **tipo de parámetro** de la directiva empresarial.</span><span class="sxs-lookup"><span data-stu-id="f783d-177">For each parameter in the list, BTARN enters a value in **Parameter Type** from the business policy.</span></span> <span data-ttu-id="f783d-178">En la lista desplegable asociada **nombre de parámetro**, BTARN entra en los nombres de todas las variables de la lista de variables de orquestación que tenga el mismo tipo que los parámetros de directiva.</span><span class="sxs-lookup"><span data-stu-id="f783d-178">In the drop-down list associated with **Parameter Name**, BTARN enters the names of all variables from the orchestration's variable list that has the same type as the policy parameters.</span></span> <span data-ttu-id="f783d-179">Al seleccionar una variable de orquestación, va a asociar esa variable con el parámetro de directiva.</span><span class="sxs-lookup"><span data-stu-id="f783d-179">By selecting an orchestration variable, you are associating that variable with the policy parameter.</span></span> <span data-ttu-id="f783d-180">Puede ver las variables de orquestación en Vista orquestación.</span><span class="sxs-lookup"><span data-stu-id="f783d-180">You can view the orchestration variables in Orchestration View.</span></span>  
  
10. <span data-ttu-id="f783d-181">Repita el paso 9 para todos los demás parámetros.</span><span class="sxs-lookup"><span data-stu-id="f783d-181">Repeat step 9 for all other parameters.</span></span>  
  
11. <span data-ttu-id="f783d-182">En la ventana de diseño de orquestación, escriba todas las formas adicionales necesarias para los procesos asociados con la directiva empresarial, incluida la adición de un **decisión** forma bajo la **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="f783d-182">In the Orchestration Design window, enter all the additional shapes required for the processing associated with the business policy, including adding a **Decision** shape under the **Call Rules** shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f783d-183">Para obtener un ejemplo de cómo usar un **reglas de llamada** forma de una orquestación, vea la orquestación PIP3A4PrivateResponder.odx incluida en el SDK de BTARN.</span><span class="sxs-lookup"><span data-stu-id="f783d-183">For an example of how to use a **Call Rules** shape in an orchestration, see the PIP3A4PrivateResponder.odx orchestration included in the BTARN SDK.</span></span> <span data-ttu-id="f783d-184">Se encuentra en \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\PipAutomation\3A4\PR.</span><span class="sxs-lookup"><span data-stu-id="f783d-184">It is located at \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4\PR.</span></span> <span data-ttu-id="f783d-185">Para obtener más información, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span><span class="sxs-lookup"><span data-stu-id="f783d-185">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
12. <span data-ttu-id="f783d-186">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f783d-186">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f783d-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="f783d-187">See Also</span></span>  
 <span data-ttu-id="f783d-188">[Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="f783d-188">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 <span data-ttu-id="f783d-189">[Directiva empresarial BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span><span class="sxs-lookup"><span data-stu-id="f783d-189">[Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span></span>  
 [<span data-ttu-id="f783d-190">Orquestación del respondedor privado 3A4 mediante una regla de negocio</span><span class="sxs-lookup"><span data-stu-id="f783d-190">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)