---
title: 'Cómo: implementar enrutamiento por contenidos mediante una empresa de reglas de directiva para un tipo de mensaje conocido | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878a6e180aaf7e5f37c5cf98ca0a67790917859a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010045"
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a><span data-ttu-id="c3b64-102">Cómo: implementar enrutamiento por contenidos mediante una empresa de reglas de directiva para un tipo de mensaje conocido</span><span class="sxs-lookup"><span data-stu-id="c3b64-102">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>
## <a name="goal"></a><span data-ttu-id="c3b64-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="c3b64-103">Goal</span></span>  
 <span data-ttu-id="c3b64-104">En esta sección se muestra cómo crear un itinerario que dinámicamente enruta un mensaje, en función del contenido de un tipo de mensaje conocido (esquema implementado en la base de datos de configuración de Microsoft BizTalk Server), utilizando un negocio de reglas de directiva.</span><span class="sxs-lookup"><span data-stu-id="c3b64-104">This section demonstrates how to create an itinerary that dynamically routes a message, based on the content of a known message type (schema deployed to the Microsoft BizTalk Server Configuration database), using a business rules policy.</span></span>  
  
 <span data-ttu-id="c3b64-105">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3b64-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="c3b64-106">Crear una directiva de reglas de negocios que se usará para enrutar un mensaje basado en contenido.</span><span class="sxs-lookup"><span data-stu-id="c3b64-106">Create a business rules policy that will be used to route a message based on content.</span></span>  
  
-   <span data-ttu-id="c3b64-107">Crear una lista de distribución itinerario con una resolución BRE para enrutar un mensaje de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="c3b64-107">Create an itinerary routing slip with a BRE resolver to dynamically route a message.</span></span>  
  
-   <span data-ttu-id="c3b64-108">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="c3b64-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c3b64-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c3b64-109">Prerequisites</span></span>  
 <span data-ttu-id="c3b64-110">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="c3b64-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="c3b64-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c3b64-111">Before You Begin</span></span>  
 <span data-ttu-id="c3b64-112">Complete las tareas siguientes antes de realizar los pasos más adelante en este tema "Cómo...":</span><span class="sxs-lookup"><span data-stu-id="c3b64-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="c3b64-113">Crear el mensaje de prueba GlobalBank West.</span><span class="sxs-lookup"><span data-stu-id="c3b64-113">Create the GlobalBank West test message.</span></span>  
  
-   <span data-ttu-id="c3b64-114">Crear el mensaje de prueba de este GlobalBank.</span><span class="sxs-lookup"><span data-stu-id="c3b64-114">Create the GlobalBank East test message.</span></span>  
  
 <span data-ttu-id="c3b64-115">Los procedimientos siguientes describen cómo realizar cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="c3b64-115">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="c3b64-116">Para crear el mensaje de prueba GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="c3b64-116">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="c3b64-117">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="c3b64-117">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="c3b64-118">Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de West.xml.</span><span class="sxs-lookup"><span data-stu-id="c3b64-118">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="c3b64-119">En el Bloc de notas, abra West.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankWest**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-119">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="c3b64-120">Guardar West.xml como UTF-8 y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="c3b64-120">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="c3b64-121">Para crear el mensaje de prueba de este GlobalBank</span><span class="sxs-lookup"><span data-stu-id="c3b64-121">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="c3b64-122">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="c3b64-122">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="c3b64-123">Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de East.xml.</span><span class="sxs-lookup"><span data-stu-id="c3b64-123">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="c3b64-124">En el Bloc de notas, abra East.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankEast**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-124">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="c3b64-125">Guardar East.xml como UTF-8 y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="c3b64-125">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="c3b64-126">Pasos</span><span class="sxs-lookup"><span data-stu-id="c3b64-126">Steps</span></span>  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a><span data-ttu-id="c3b64-127">Para crear una directiva del BRE para enrutar con propiedades personalizadas de mensajes</span><span class="sxs-lookup"><span data-stu-id="c3b64-127">To create a BRE policy to route using custom message properties</span></span>  
 <span data-ttu-id="c3b64-128">Esta regla utilizará el nombre del cliente para establecer dinámicamente el extremo que se utiliza para enrutar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c3b64-128">This rule will use the customer's name to dynamically set the endpoint used to route the message.</span></span>  
  
1.  <span data-ttu-id="c3b64-129">Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-129">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="c3b64-130">En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="c3b64-131">Nombre de la directiva **RouteBasedOnCustomerKnownType**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-131">Name the policy **RouteBasedOnCustomerKnownType**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a><span data-ttu-id="c3b64-132">Para agregar una regla de enrutamiento de cliente GlobalBank West</span><span class="sxs-lookup"><span data-stu-id="c3b64-132">To add a routing rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="c3b64-133">En el **RouteBasedOnCustomerKnownType** directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-133">In the **RouteBasedOnCustomerKnownType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="c3b64-134">Nombre de la regla **SetWestEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-134">Name the rule **SetWestEndpoint**.</span></span>  
  
2.  <span data-ttu-id="c3b64-135">En el Explorador de hechos, haga clic en el **esquemas XML** pestaña, haga clic en **esquemas**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-135">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="c3b64-136">En el **archivos de esquema** cuadro de diálogo, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas, seleccione **NAOrderDoc.xsd**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-136">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3b64-137">Éste es el esquema que define el mensaje NAOrderDoc.xml, que se usó para crear los mensajes de Oeste y este que va a usar para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="c3b64-137">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="c3b64-138">En el Explorador de hechos, haga clic en **NAOrderDoc.xsd**y, a continuación, en el panel Propiedades, haga clic en el **tipo de documento** propiedad y, a continuación, escriba **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc** .</span><span class="sxs-lookup"><span data-stu-id="c3b64-138">In Facts Explorer, click **NAOrderDoc.xsd**, and then in the Properties pane, click the **Document Type** property, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3b64-139">Este es el nombre completo del esquema.</span><span class="sxs-lookup"><span data-stu-id="c3b64-139">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="c3b64-140">En el Explorador de hechos, expanda **NAOrderDoc.xsd**y, a continuación, expanda **OrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-140">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="c3b64-141">En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-141">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="c3b64-142">En el Explorador de hechos, arrastre el **customerName** elemento a la **argumento1** nodo bajo **condiciones**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-142">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="c3b64-143">Haga clic en el **argumento2** nodo y, a continuación, escriba **GlobalBankWest**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-143">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="c3b64-144">En el Explorador de hechos, haga clic en el **vocabularios** , expanda **ESB. EndPointInfo**y, a continuación, expanda **versión 1.0**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-144">In Facts Explorer, click the **Vocabularies** tab, expand **ESB.EndPointInfo**, and then expand **Version 1.0**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3b64-145">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varios vocabularios que pueden usarse para crear reglas para su uso en ESB.</span><span class="sxs-lookup"><span data-stu-id="c3b64-145">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules for use in the ESB.</span></span> <span data-ttu-id="c3b64-146">Algunos de ellos deben reemplazarse o ampliada con sus propios vocabularios.</span><span class="sxs-lookup"><span data-stu-id="c3b64-146">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="c3b64-147">Por ejemplo, el **DynamicRunTimeMaptypes** tiene definiciones de las asignaciones proporcionadas en el **GlobalBank** ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c3b64-147">For example, the **DynamicRunTimeMaptypes** has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
10. <span data-ttu-id="c3b64-148">En el Explorador de hechos, arrastre el **establecer ubicación de transporte saliente de punto final** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-148">From Facts Explorer, drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
11. <span data-ttu-id="c3b64-149">Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **C:\HowTos\Out\West%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-149">Click **\<empty string\>** and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
12. <span data-ttu-id="c3b64-150">En el Explorador de hechos, arrastre el **establecer tipo de transporte saliente de punto final** definición a **acciones**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-150">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
13. <span data-ttu-id="c3b64-151">En el Explorador de hechos, expanda **ESB. TransportTypes**, expanda **versión 1.0**y, a continuación, arrastre el **proveedores de adaptador** definición a  **\<una cadena vacía\>** .</span><span class="sxs-lookup"><span data-stu-id="c3b64-151">In Facts Explorer, expand **ESB.TransportTypes**, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
14. <span data-ttu-id="c3b64-152">En el **acciones** panel, expanda el **proveedores de adaptador** lista desplegable y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-152">In the **Actions** pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a><span data-ttu-id="c3b64-153">Para agregar una regla de enrutamiento para este GlobalBank de cliente</span><span class="sxs-lookup"><span data-stu-id="c3b64-153">To add a routing rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="c3b64-154">En el Explorador de directivas, haga clic en el **SetWestEndpoint** de regla y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-154">In Policy Explorer, right-click the **SetWestEndpoint** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="c3b64-155">Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-155">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="c3b64-156">En el **nombre de nueva regla** cuadro de diálogo, escriba **SetEastEndpoint**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-156">In the **New Rule Name** dialog box, type **SetEastEndpoint**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c3b64-157">En el Explorador de directivas, haga clic en el **SetEastEndpoint** regla.</span><span class="sxs-lookup"><span data-stu-id="c3b64-157">In Policy Explorer, click the **SetEastEndpoint** rule.</span></span>  
  
5.  <span data-ttu-id="c3b64-158">En el **condiciones** sección, haga clic en **GlobalBankWest**y, a continuación, haga clic en **Restablecer argumento**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-158">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="c3b64-159">Haga clic en **argumento2**y, a continuación, escriba **GlobalBankEast**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-159">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="c3b64-160">En el **acciones** sección, haga clic en **C:\HowTos\Out\West%MessageID%.xml**y, a continuación, haga clic en **Restablecer argumento**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-160">In the **Actions** section, right-click **C:\HowTos\Out\West%MessageID%.xml**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="c3b64-161">Haga clic en  **\<una cadena vacía\>** y, a continuación, escriba **C:\HowTos\Out\East%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-161">Click **\<empty string\>**, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a><span data-ttu-id="c3b64-162">Para agregar una regla de enrutamiento para los clientes desconocidos</span><span class="sxs-lookup"><span data-stu-id="c3b64-162">To add a routing rule for unknown customers</span></span>  
  
1.  <span data-ttu-id="c3b64-163">En la directiva RouteBasedOnCustomerKnownType, haga clic en la versión 1.0 (sin guardar) y, a continuación, haga clic en Agregar nueva regla.</span><span class="sxs-lookup"><span data-stu-id="c3b64-163">In the RouteBasedOnCustomerKnownType policy, right-click Version 1.0 (not saved), and then click Add New Rule.</span></span> <span data-ttu-id="c3b64-164">Nombre de la regla SetUnknownCustomerEndpoint.</span><span class="sxs-lookup"><span data-stu-id="c3b64-164">Name the rule SetUnknownCustomerEndpoint.</span></span>  
  
2.  <span data-ttu-id="c3b64-165">En la ventana de la regla, haga clic en condiciones y, a continuación, haga clic en Agregar operador lógico AND.</span><span class="sxs-lookup"><span data-stu-id="c3b64-165">In the Rule window, right-click Conditions, and then click Add logical AND.</span></span>  
  
3.  <span data-ttu-id="c3b64-166">En la ventana de la regla, haga clic en, elija predicados y, a continuación, haga clic en Distintode.</span><span class="sxs-lookup"><span data-stu-id="c3b64-166">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
4.  <span data-ttu-id="c3b64-167">En el Explorador de hechos, haga clic en la pestaña esquemas XML, expanda NAOrderDoc.xsd y, a continuación, expanda OrderDoc.</span><span class="sxs-lookup"><span data-stu-id="c3b64-167">In Facts Explorer, click the XML Schemas tab, expand NAOrderDoc.xsd, and then expand OrderDoc.</span></span>  
  
5.  <span data-ttu-id="c3b64-168">Desde el Explorador de hechos, arrastre el elemento customerName al nodo argumento1 en condiciones.</span><span class="sxs-lookup"><span data-stu-id="c3b64-168">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
6.  <span data-ttu-id="c3b64-169">Haga clic en el nodo argumento2 y, a continuación, escriba GlobalBankWest.</span><span class="sxs-lookup"><span data-stu-id="c3b64-169">Click the argument2 node, and then type GlobalBankWest.</span></span>  
  
7.  <span data-ttu-id="c3b64-170">En la ventana de la regla, haga clic en, elija predicados y, a continuación, haga clic en Distintode.</span><span class="sxs-lookup"><span data-stu-id="c3b64-170">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
8.  <span data-ttu-id="c3b64-171">Desde el Explorador de hechos, arrastre el elemento customerName al nodo argumento1 en condiciones.</span><span class="sxs-lookup"><span data-stu-id="c3b64-171">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
9. <span data-ttu-id="c3b64-172">Haga clic en el nodo argumento2 y, a continuación, escriba GlobalBankEast.</span><span class="sxs-lookup"><span data-stu-id="c3b64-172">Click the argument2 node, and then type GlobalBankEast.</span></span>  
  
10. <span data-ttu-id="c3b64-173">En el Explorador de hechos, haga clic en la pestaña vocabularios, expanda ESB. EndPointInfo y, a continuación, expanda la versión 1.0.</span><span class="sxs-lookup"><span data-stu-id="c3b64-173">In Facts Explorer, click the Vocabularies tab, expand ESB.EndPointInfo, and then expand Version 1.0.</span></span>  
  
11. <span data-ttu-id="c3b64-174">Desde el Explorador de hechos, arrastre la definición de establecer ubicación de transporte saliente de punto de conexión a las acciones.</span><span class="sxs-lookup"><span data-stu-id="c3b64-174">From Facts Explorer, drag the Set End Point Outbound Transport Location definition to Actions.</span></span>  
  
12. <span data-ttu-id="c3b64-175">Haga clic en \<una cadena vacía\>, y, a continuación, escriba C:\HowTos\Out\CustomerUnknown%MessageID%.xml.</span><span class="sxs-lookup"><span data-stu-id="c3b64-175">Click \<empty string\>, and then type C:\HowTos\Out\CustomerUnknown%MessageID%.xml.</span></span>  
  
13. <span data-ttu-id="c3b64-176">Desde el Explorador de hechos, arrastre la definición de tipo de transporte saliente punto final establecido a las acciones.</span><span class="sxs-lookup"><span data-stu-id="c3b64-176">From Facts Explorer, drag the Set End Point Outbound Transport Type definition to Actions.</span></span>  
  
14. <span data-ttu-id="c3b64-177">En el Explorador de hechos, expanda ESB. TransportTypes, expanda versión 1.0 y, a continuación, arrastre la definición de proveedores de adaptador para \<una cadena vacía\>.</span><span class="sxs-lookup"><span data-stu-id="c3b64-177">In Facts Explorer, expand ESB.TransportTypes, expand Version 1.0, and then drag the Adaptor Providers definition to \<empty string\>.</span></span>  
  
15. <span data-ttu-id="c3b64-178">En el panel Acciones, expanda la lista desplegable de proveedores de adaptador y, a continuación, haga clic en archivo.</span><span class="sxs-lookup"><span data-stu-id="c3b64-178">In the Actions pane, expand the Adaptor Providers drop-down list, and then click FILE.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="c3b64-179">Para publicar e implementar la directiva</span><span class="sxs-lookup"><span data-stu-id="c3b64-179">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="c3b64-180">En el Explorador de directivas, en la **RouteBasedOnCustomerKnownType** directiva, haga clic derecho **versión 1.0 (sin guardar)** y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-180">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="c3b64-181">En el Explorador de directivas, en la **RouteBasedOnCustomerKnownType** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-181">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="c3b64-182">Para crear un modelo DSL itinerario de ESB</span><span class="sxs-lookup"><span data-stu-id="c3b64-182">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="c3b64-183">En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="c3b64-183">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="c3b64-184">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-184">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="c3b64-185">En el **Agregar nuevo elemento** cuadro de diálogo, en la **nombre** , escriba **CbrKnownType**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-185">In the **Add New Item** dialog box, in the **Name** box, type **CbrKnownType**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="c3b64-186">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="c3b64-186">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="c3b64-187">En Visual Studio, haga clic en la superficie de diseño de **CbrKnownType.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-187">In Visual Studio, click the design surface of **CbrKnownType.itinerary**.</span></span> <span data-ttu-id="c3b64-188">En el **CbrKnownType** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c3b64-188">In the **CbrKnownType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c3b64-189">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-189">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="c3b64-190">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="c3b64-190">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="c3b64-191">En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\CbrKnownType** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-191">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\CbrKnownType** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c3b64-192">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="c3b64-192">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="c3b64-193">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="c3b64-193">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="c3b64-194">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="c3b64-194">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="c3b64-195">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="c3b64-195">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="c3b64-196">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="c3b64-196">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="c3b64-197">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c3b64-197">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c3b64-198">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-198">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="c3b64-199">En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-199">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="c3b64-200">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-200">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="c3b64-201">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-201">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="c3b64-202">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="c3b64-202">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="c3b64-203">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c3b64-203">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c3b64-204">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendRegionalOrders**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-204">Click the **Name** property, and then type **SendRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="c3b64-205">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-205">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="c3b64-206">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-206">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="c3b64-207">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-207">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="c3b64-208">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendRegionalOrders**elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="c3b64-208">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendRegionalOrders** model element.</span></span> <span data-ttu-id="c3b64-209">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c3b64-209">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c3b64-210">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-210">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="c3b64-211">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-211">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="c3b64-212">En el **fuera de rampa** lista desplegable lista, expanda **SendRegionalOrders**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-212">In the **Off-Ramp** drop-down list, expand **SendRegionalOrders**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="c3b64-213">Haga clic en el **resolución** colección de la **SendPortFilter** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-213">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="c3b64-214">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c3b64-214">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c3b64-215">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteRegionalOrders**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-215">Click the **Name** property, and then type **RouteRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="c3b64-216">En el **nombre del transporte** la lista desplegable, haga clic en **BRE**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-216">In the **Transport Name** drop-down list, click **BRE**.</span></span>  
  
    3.  <span data-ttu-id="c3b64-217">En el **implementación de la resolución** la lista desplegable, haga clic en **Bre resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-217">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    4.  <span data-ttu-id="c3b64-218">En el **directiva** la lista desplegable, haga clic en **RouteBasedOnCustomerKnownType**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-218">In the **Policy** drop-down list, click **RouteBasedOnCustomerKnownType**.</span></span>  
  
    5.  <span data-ttu-id="c3b64-219">En el **reconoce el formato de mensaje** lista desplegable y haga clic en **True**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-219">In the **Recognize Message Format** drop-down list click **True**.</span></span>  
  
    6.  <span data-ttu-id="c3b64-220">En el **UseMsg** la lista desplegable, haga clic en **True**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-220">In the **UseMsg** drop-down list, click **True**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c3b64-221">Si utiliza la extensión de la resolución de BRE de orquestación, el **recognizeMessageFormat** propiedad debe establecerse en **False**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-221">If you use the BRE Resolver Extension from orchestration, the **recognizeMessageFormat** property must be set to **False**.</span></span>  
  
5.  <span data-ttu-id="c3b64-222">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-222">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="c3b64-223">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="c3b64-223">Drag a connection from the **ReceiveNAOrder** model element to the **SendPortFilter** model element.</span></span>  
  
6.  <span data-ttu-id="c3b64-224">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="c3b64-225">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendRegionalOrders** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="c3b64-225">Drag a connection from the **SendPortFilter** model element to the **SendRegionalOrders** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="c3b64-226">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="c3b64-226">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="c3b64-227">En Visual Studio, haga clic en la superficie de diseño de la **CbrKnownType** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-227">In Visual Studio, right-click the design surface of the **CbrKnownType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3b64-228">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3b64-228">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c3b64-229">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3b64-229">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="c3b64-230">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (CbrKnownType.xml).</span><span class="sxs-lookup"><span data-stu-id="c3b64-230">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (CbrKnownType.xml).</span></span>  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a><span data-ttu-id="c3b64-231">Para probar las itinerarios y reglas del negocio</span><span class="sxs-lookup"><span data-stu-id="c3b64-231">To test the itinerary and business rules</span></span>  
  
1.  <span data-ttu-id="c3b64-232">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="c3b64-232">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="c3b64-233">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="c3b64-233">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="c3b64-234">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="c3b64-234">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="c3b64-235">Seleccione **CbrKnownType.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="c3b64-235">Select **CbrKnownType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="c3b64-236">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="c3b64-236">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="c3b64-237">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="c3b64-237">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="c3b64-238">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="c3b64-238">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="c3b64-239">Seleccione **West.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="c3b64-239">Select **West.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="c3b64-240">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="c3b64-240">Click the **Submit Request** button.</span></span> <span data-ttu-id="c3b64-241">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3b64-241">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="c3b64-242">En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje West%MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="c3b64-242">In Windows Explorer, browse to C:\HowTos\Out. Verify that the West%MessageID%.xml message has been written to the directory.</span></span>  
  
9. <span data-ttu-id="c3b64-243">Repita el proceso de prueba con el mensaje East.xml.</span><span class="sxs-lookup"><span data-stu-id="c3b64-243">Repeat the test process using the East.xml message.</span></span>  
  
10. <span data-ttu-id="c3b64-244">En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje East%MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="c3b64-244">In Windows Explorer, browse to C:\HowTos\Out. Verify that the East%MessageID%.xml message has been written to the directory.</span></span>  
  
11. <span data-ttu-id="c3b64-245">Repita el proceso de prueba con el mensaje NAOrderDoc.xml.</span><span class="sxs-lookup"><span data-stu-id="c3b64-245">Repeat the test process using the NAOrderDoc.xml message.</span></span>  
  
12. <span data-ttu-id="c3b64-246">En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje CustomerUnknown%MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="c3b64-246">In Windows Explorer, browse to C:\HowTos\Out. Verify that the CustomerUnknown%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="c3b64-247">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c3b64-247">Additional Resources</span></span>  
 <span data-ttu-id="c3b64-248">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="c3b64-248">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="c3b64-249">Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="c3b64-249">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="c3b64-250">Cómo: Enrutar dinámicamente un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="c3b64-250">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="c3b64-251">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="c3b64-251">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="c3b64-252">Patrones de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="c3b64-252">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)