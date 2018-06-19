---
title: Invocar una directiva desde otra directiva | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5bf658a-02a1-426a-abe5-8c9de673cf0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac45c31ef76213e79249e96fe645ecbb5fb66ed4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973562"
---
# <a name="invoking-a-policy-from-another-policy"></a><span data-ttu-id="7bb02-102">Invocar una directiva desde otra directiva</span><span class="sxs-lookup"><span data-stu-id="7bb02-102">Invoking a Policy from Another Policy</span></span>
<span data-ttu-id="7bb02-103">Puede invocar una directiva (secundaria) desde otra directiva (principal) mediante el uso de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="7bb02-103">You can invoke a policy (child) from another policy (parent) by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="7bb02-104">Llamar a la **Policy.Execute** (método) directamente desde la directiva principal</span><span class="sxs-lookup"><span data-stu-id="7bb02-104">Calling the **Policy.Execute** method directly from the parent policy</span></span>  
  
-   <span data-ttu-id="7bb02-105">Llamar a un método de un componente .NET auxiliar que ajusta la **Policy.Execute** método desde la directiva principal</span><span class="sxs-lookup"><span data-stu-id="7bb02-105">Calling a method of a helper .NET component that wraps the **Policy.Execute** method from the parent policy</span></span>  
  
 <span data-ttu-id="7bb02-106">La ventaja de usar el segundo método es que puede agregar código previas y posteriores al procesamiento para la **Policy.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="7bb02-106">The advantage of using the second method is that you can add pre-processing and post-processing code to the **Policy.Execute** method.</span></span> <span data-ttu-id="7bb02-107">Por ejemplo, puede crear cualquier hecho necesario desde la directiva secundaria en este método contenedor.</span><span class="sxs-lookup"><span data-stu-id="7bb02-107">For example, you can create any facts required from the child policy in this wrapper method.</span></span> <span data-ttu-id="7bb02-108">Las siguientes secciones proporcionan un ejemplo para cada método.</span><span class="sxs-lookup"><span data-stu-id="7bb02-108">The following sections provide an example for each method.</span></span>  
  
## <a name="invoking-the-policyexecute-method-directly-from-the-parent-policy"></a><span data-ttu-id="7bb02-109">Invocar el método Policy.Execute directamente desde la directiva principal</span><span class="sxs-lookup"><span data-stu-id="7bb02-109">Invoking the Policy.Execute Method Directly from the Parent Policy</span></span>  
 <span data-ttu-id="7bb02-110">En esta sección se detallan los pasos de alto nivel para invocar la directiva secundaria desde la directiva principal mediante la **Policy.Execute** método directamente.</span><span class="sxs-lookup"><span data-stu-id="7bb02-110">This section presents the high-level steps to invoke the child policy from the parent policy by using the **Policy.Execute** method directly.</span></span>  
  
### <a name="adding-the-policyexecute-action-to-the-parent-policy"></a><span data-ttu-id="7bb02-111">Agregar la acción Policy.Execute a la directiva principal</span><span class="sxs-lookup"><span data-stu-id="7bb02-111">Adding the Policy.Execute Action to the Parent Policy</span></span>  
 <span data-ttu-id="7bb02-112">El procedimiento siguiente tiene pasos para agregar el **Policy.Execute** método como una acción a la directiva principal que transfiere un documento XML como un hecho a la directiva secundaria.</span><span class="sxs-lookup"><span data-stu-id="7bb02-112">The following procedure has steps to add the **Policy.Execute** method as an action to the parent policy that passes an XML document as a fact to the child policy.</span></span>  
  
##### <a name="to-add-the-policyexecute-method-as-an-action-to-a-policy"></a><span data-ttu-id="7bb02-113">Para agregar el método Policy.Execute como acción a una directiva</span><span class="sxs-lookup"><span data-stu-id="7bb02-113">To add the Policy.Execute method as an action to a policy</span></span>  
  
1.  <span data-ttu-id="7bb02-114">En la ventana Explorador de hechos, haga clic en el **clases .NET** ficha.</span><span class="sxs-lookup"><span data-stu-id="7bb02-114">In the Facts Explorer window, click the **.NET Classes** tab.</span></span>  
  
2.  <span data-ttu-id="7bb02-115">Haga clic en **ensamblados .NET**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="7bb02-115">Right-click **.NET Assemblies**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="7bb02-116">Seleccione **Microsoft.RuleEngine** desde el **ensamblados .NET** lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7bb02-116">Select **Microsoft.RuleEngine** from the **.NET Assemblies** list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="7bb02-117">Expanda **directiva**.</span><span class="sxs-lookup"><span data-stu-id="7bb02-117">Expand **Policy**.</span></span>  
  
5.  <span data-ttu-id="7bb02-118">Arrastre **Execute (Object facts)** o **Execute (Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** al panel entonces.</span><span class="sxs-lookup"><span data-stu-id="7bb02-118">Drag **Execute(Object facts)** or **Execute(Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** to the THEN pane.</span></span>  
  
6.  <span data-ttu-id="7bb02-119">Haga clic en el **esquemas XML** nodo.</span><span class="sxs-lookup"><span data-stu-id="7bb02-119">Click the **XML Schemas** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bb02-120">En este escenario de ejemplo, un documento XML que se envía como un hecho a la directiva principal se transfiere como hecho a la directiva secundaria.</span><span class="sxs-lookup"><span data-stu-id="7bb02-120">In this sample scenario, an XML document that is submitted as a fact to the parent policy is passed as a fact to the child policy.</span></span> <span data-ttu-id="7bb02-121">En lugar de ello, puede invocar un método .NET que cree los hechos para la directiva secundaria.</span><span class="sxs-lookup"><span data-stu-id="7bb02-121">Instead, you can invoke a .NET method that creates the facts for the child policy.</span></span>  
  
7.  <span data-ttu-id="7bb02-122">Haga clic en **esquemas**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="7bb02-122">Right-click **Schemas**, and then click **Browse**.</span></span>  
  
8.  <span data-ttu-id="7bb02-123">Seleccione el esquema del documento XML que desea transferir como hecho y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="7bb02-123">Select the schema for the XML document you want to pass as a fact, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="7bb02-124">Arrastre  *\<nombre de esquema\>*.xsd al primer argumento de la **Policy.Execute** método para pasar el documento XML que se pasa a la directiva principal como un hecho a la directiva secundaria.</span><span class="sxs-lookup"><span data-stu-id="7bb02-124">Drag *\<Schema name\>*.xsd to the first argument of the **Policy.Execute** method to pass the XML document that is passed to the parent policy as a fact to the child policy.</span></span>  
  
10. <span data-ttu-id="7bb02-125">Si usas el **Execute** método que no tome el **IRuleSetTrackingInterceptor** como segundo argumento, omita los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7bb02-125">If you use the **Execute** method that does not take the **IRuleSetTrackingInterceptor** as the second argument, skip the following steps.</span></span>  
  
11. <span data-ttu-id="7bb02-126">Haga clic en el **clases .NET** ficha.</span><span class="sxs-lookup"><span data-stu-id="7bb02-126">Click the **.NET Classes** tab.</span></span>  
  
12. <span data-ttu-id="7bb02-127">Arrastre **DebugTrackingInterceptor** en **Microsoft.RuleEngine** para el segundo argumento de la **Policy.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="7bb02-127">Drag **DebugTrackingInterceptor** in **Microsoft.RuleEngine** to the second argument of the **Policy.Execute** method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bb02-128">Si realiza esta acción, el cliente debe pasar una instancia de la **DebugTrackingInterceptor** clase como un hecho a la directiva principal, que a su vez pasa la instancia como un hecho a la directiva secundaria.</span><span class="sxs-lookup"><span data-stu-id="7bb02-128">If you perform this action, the client must pass an instance of the **DebugTrackingInterceptor** class as a fact to the parent policy, which in turn passes the instance as a fact to the child policy.</span></span> <span data-ttu-id="7bb02-129">En su lugar, puede arrastrar el constructor de la **DebugTrackingInterceptor** clase para que la instancia se crea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7bb02-129">Instead you could drag the constructor of the **DebugTrackingInterceptor** class so that the instance is automatically created for you.</span></span>  
  
### <a name="modifying-the-client-application-that-invokes-the-parent-policy"></a><span data-ttu-id="7bb02-130">Modificar la aplicación cliente que invoca la directiva principal</span><span class="sxs-lookup"><span data-stu-id="7bb02-130">Modifying the Client Application that Invokes the Parent Policy</span></span>  
 <span data-ttu-id="7bb02-131">El cliente que invoca la directiva principal crea una instancia de la **directiva** clase con el nombre de la directiva secundaria como parámetro y lo pasa como un hecho a la directiva principal junto con otros hechos.</span><span class="sxs-lookup"><span data-stu-id="7bb02-131">The client that invokes the parent policy creates an instance of the **Policy** class with the child policy name as a parameter and passes it as a fact to the parent policy along with other facts.</span></span> <span data-ttu-id="7bb02-132">En el siguiente código de ejemplo se ilustra esta acción:</span><span class="sxs-lookup"><span data-stu-id="7bb02-132">The following sample code illustrates this action:</span></span>  
  
```  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
Policy policy = new Policy("ParentPolicy");  
object[] facts = new object[3];  
facts[0] = txd;  
facts[1] = new Policy("ChildPolicy");  
facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
 <span data-ttu-id="7bb02-133">Si el cliente es una orquestación de BizTalk, debe colocar el código para crear hechos en un **expresión** forma y, a continuación, transferirlos como parámetros a la **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="7bb02-133">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>  
  
## <a name="invoking-a-net-wrapper-method-from-the-parent-policy"></a><span data-ttu-id="7bb02-134">Invocar un método contenedor .NET desde la directiva principal</span><span class="sxs-lookup"><span data-stu-id="7bb02-134">Invoking a .NET Wrapper Method from the Parent Policy</span></span>  
 <span data-ttu-id="7bb02-135">En esta sección se detallan los pasos de alto nivel para invocar un método de .NET que contiene la llamada a la **Policy.Execute** método desde la directiva principal.</span><span class="sxs-lookup"><span data-stu-id="7bb02-135">This section presents the high-level steps to invoke a .NET method that wraps the call to the **Policy.Execute** method from the parent policy.</span></span>  
  
### <a name="creating-the-utility-net-class"></a><span data-ttu-id="7bb02-136">Crear la clase de utilidad .NET</span><span class="sxs-lookup"><span data-stu-id="7bb02-136">Creating the Utility .NET Class</span></span>  
  
##### <a name="to-create-the-utility-class"></a><span data-ttu-id="7bb02-137">Para crear la clase de utilidad</span><span class="sxs-lookup"><span data-stu-id="7bb02-137">To create the utility class</span></span>  
  
1.  <span data-ttu-id="7bb02-138">Cree un proyecto de biblioteca de clases .NET y, a continuación, agregue una clase al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7bb02-138">Create a .NET class library project, and then add a class to the project.</span></span>  
  
2.  <span data-ttu-id="7bb02-139">Agregue un método estático que llama el **Policy.Execute** método que se invoca la directiva cuyo nombre se pasa como un parámetro, tal como se muestra en el código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7bb02-139">Add a static method that calls the **Policy.Execute** method to invoke the policy whose name is passed as a parameter, as shown in the following sample code:</span></span>  
  
    ```  
    public static void Execute(string policyName, TypedXmlDocument txd)  
    {  
        DebugTrackingInterceptor dti = new   DebugTrackingInterceptor("PolicyTracking.txt");  
        Policy policy = new Policy("ParentPolicy");  
        object[] facts = new object[3];  
        facts[0] = txd;  
        facts[1] = new Policy("ChildPolicy");  
        facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
        policy.Execute(facts, dti);  
        policy.Dispose();  
    }   
    ```  
  
3.  <span data-ttu-id="7bb02-140">Asegúrese de que el **StaticSupport** clave del registro se establece en 1 o 2.</span><span class="sxs-lookup"><span data-stu-id="7bb02-140">Make sure that the **StaticSupport** registry key is set to 1 or 2.</span></span> <span data-ttu-id="7bb02-141">Para obtener más información acerca de la clave del registro, consulte [invocar miembros estáticos de una clase](../core/invoking-static-members-of-a-class.md).</span><span class="sxs-lookup"><span data-stu-id="7bb02-141">For more information about the registry key, see [Invoking Static Members of a Class](../core/invoking-static-members-of-a-class.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bb02-142">Puede usar un método de instancia en lugar de un método estático.</span><span class="sxs-lookup"><span data-stu-id="7bb02-142">You can use an instance method instead of a static method.</span></span> <span data-ttu-id="7bb02-143">Recuerde que si usa un método de instancia, el cliente debe transferir una instancia de la clase .NET auxiliar como hecho a la directiva principal.</span><span class="sxs-lookup"><span data-stu-id="7bb02-143">Remember that, if you use an instance method, the client must pass an instance of the helper .NET class as a fact to the parent policy.</span></span>  
  
### <a name="modifying-the-client-application"></a><span data-ttu-id="7bb02-144">Modificar la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="7bb02-144">Modifying the Client Application</span></span>  
 <span data-ttu-id="7bb02-145">El cliente invoca la directiva principal y ésta invoca el método auxiliar que invoca la directiva secundaria.</span><span class="sxs-lookup"><span data-stu-id="7bb02-145">The client invokes the parent policy, and the parent policy invokes the helper method that invokes the child policy.</span></span> <span data-ttu-id="7bb02-146">El código de ejemplo para el cliente es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="7bb02-146">The sample code for the client is as follows:</span></span>  
  
```  
facts[0] = txd;  
facts[1] = new PolicyExecutor(txd);  
//call the first or parent policy  
Policy policy = new Policy(policyName);  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
> [!NOTE]
>  <span data-ttu-id="7bb02-147">Si el método es de instancia, el cliente debe crear una instancia de la clase .NET auxiliar y transferirla como hecho a la directiva principal.</span><span class="sxs-lookup"><span data-stu-id="7bb02-147">If the method is an instance method, the client must create an instance of the helper .NET class, and pass it as a fact to the parent policy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bb02-148">Si el cliente es una orquestación de BizTalk, debe colocar el código para crear hechos en un **expresión** forma y, a continuación, transferirlos como parámetros a la **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="7bb02-148">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>