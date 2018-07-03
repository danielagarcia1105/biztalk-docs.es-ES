---
title: 'Tutorial: Crear una directiva empresarial sencilla | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02d35735-dce2-4ee2-965e-dae307a125b0
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cecf7078592d322f9cc9777aeb530759c5ecf4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023866"
---
# <a name="walkthrough-creating-a-simple-business-policy"></a><span data-ttu-id="8ac55-102">Tutorial: Crear una directiva empresarial sencilla</span><span class="sxs-lookup"><span data-stu-id="8ac55-102">Walkthrough: Creating a Simple Business Policy</span></span>
<span data-ttu-id="8ac55-103">Este tutorial proporciona procedimientos paso a paso para que usar el Compositor de reglas de negocio para crear una directiva empresarial sencilla denominada **ProcessPurchaseOrder** que contiene una regla denominada **ApprovedRule**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-103">This walkthrough provides step-by-step procedures for using the Business Rule Composer to create a simple business policy named **ProcessPurchaseOrder** containing a rule named **ApprovedRule**.</span></span> <span data-ttu-id="8ac55-104">El **ApprovedRule** regla espera que el usuario envíe un documento XML como un hecho y establece el valor de la **estado** campo en el documento a **aprobado** si el valor de la  **Cantidad** campo es menor o igual que **500**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-104">The **ApprovedRule** rule expects the user to submit an XML document as a fact, and sets the value of the **Status** field in the document to **Approved** if the value of the **Quantity** field is less than or equal to **500**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8ac55-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8ac55-105">Prerequisites</span></span>  
 <span data-ttu-id="8ac55-106">Debe conocer los fundamentos del Marco de trabajo de reglas de negocios para realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="8ac55-106">You must be familiar with the basics of the Business Rules Framework to perform this walkthrough.</span></span> <span data-ttu-id="8ac55-107">Si está familiarizado con el marco de trabajo de reglas de negocios, se recomienda que lea la introducción a la arquitectura del marco de trabajo de reglas de negocios en [motor de reglas de negocios](../core/business-rules-engine.md) antes de realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="8ac55-107">If you are new to the Business Rules Framework, we recommend that you read the architecture overview of the Business Rules Framework at [Business Rules Engine](../core/business-rules-engine.md) before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="8ac55-108">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="8ac55-108">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="8ac55-109">Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ac55-109">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="8ac55-110">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="8ac55-110">Procedure title</span></span>|<span data-ttu-id="8ac55-111">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="8ac55-111">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="8ac55-112">Para crear el archivo de esquema PO</span><span class="sxs-lookup"><span data-stu-id="8ac55-112">To create the PO schema file</span></span>|<span data-ttu-id="8ac55-113">Proporciona instrucciones paso a paso para crear el esquema del documento que el **ProcessPurchaseOrder** directiva utiliza.</span><span class="sxs-lookup"><span data-stu-id="8ac55-113">Provides step-by-step instructions for creating the schema for the document that the **ProcessPurchaseOrder** policy uses.</span></span>|  
|<span data-ttu-id="8ac55-114">Para crear la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="8ac55-114">To create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="8ac55-115">Proporciona instrucciones paso a paso para crear el **ProcessPurchaseOrder** directiva mediante el uso del compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="8ac55-115">Provides step-by-step instructions for creating the **ProcessPurchaseOrder** policy by using the Business Rule Composer.</span></span>|  
  
### <a name="to-create-the-po-schema-file"></a><span data-ttu-id="8ac55-116">Para crear el archivo de esquema PO</span><span class="sxs-lookup"><span data-stu-id="8ac55-116">To create the PO schema file</span></span>  
  
1.  <span data-ttu-id="8ac55-117">En el **iniciar** menú Abrir **el Bloc de notas**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-117">On the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="8ac55-118">En el menú **Archivo** , elija **Nuevo**y haga clic en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-118">On the **File** menu, point to **New**, and then click **File**.</span></span>  
  
3.  <span data-ttu-id="8ac55-119">Copie el texto XML siguiente en el editor:</span><span class="sxs-lookup"><span data-stu-id="8ac55-119">Copy the following XML text to the editor:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://EAISolution.PurchaseOrder" targetNamespace="http://EAISolution.PurchaseOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="PurchaseOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="Header">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="ReqID" type="xs:string" />  
                  <xs:element name="Date" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Item">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Description" type="xs:string" />  
                  <xs:element name="Quantity" type="xs:int" />  
                  <xs:element name="UnitPrice" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Status" type="xs:string" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
4.  <span data-ttu-id="8ac55-120">En el **archivo** menú, haga clic en **guardar Archivodetexto1.txt como**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-120">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
5.  <span data-ttu-id="8ac55-121">Cambie el valor de **Guardar como tipo** desde **documentos de texto (\*.txt)** a **todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-121">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
6.  <span data-ttu-id="8ac55-122">Tipo **PO.xsd** en el **nombre de archivo** texto, cambie el directorio a **C:\BRE-Walkthroughs**, cambie el valor de **codificación** a  **Unicode** y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-122">Type **PO.xsd** in the **File name** text box, change the directory to **C:\BRE-Walkthroughs**, change the value of **Encoding** to **Unicode** and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ac55-123">Crear el directorio **BRE-Walkthroughs** en **C:\\**  si no existe y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-123">Create the directory **BRE-Walkthroughs** under **C:\\** if it does not exist, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="8ac55-124">Cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="8ac55-124">Close Notepad.</span></span>  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a><span data-ttu-id="8ac55-125">Para crear la directiva empresarial ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="8ac55-125">To create the ProcessPurchaseOrder business policy</span></span>  
  
1. <span data-ttu-id="8ac55-126">En el **iniciar** menú Abrir **compositor**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-126">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8ac55-127">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="8ac55-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="8ac55-128">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-128">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8ac55-129">Muestra el Compositor de reglas de negocio la **abierto regla Store** cuadro de diálogo cuando se abre por primera vez en un equipo.</span><span class="sxs-lookup"><span data-stu-id="8ac55-129">The Business Rule Composer displays the **Open Rule Store** dialog box when it is opened for the first time on a computer.</span></span> <span data-ttu-id="8ac55-130">Si ve el **abierto regla Store** cuadro de diálogo, haga clic en **Aceptar** después de comprobar el nombre de SQL server y el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8ac55-130">If you see the **Open Rule Store** dialog box, click **OK** after verifying the SQL server name and database name.</span></span>  
  
2. <span data-ttu-id="8ac55-131">En la ventana Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-131">In the Policy Explorer window, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
3. <span data-ttu-id="8ac55-132">Edite el nombre de la directiva, **Policy1**a **ProcessPurchaseOrder** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8ac55-132">Edit the name of the policy, **Policy1**, to **ProcessPurchaseOrder** and press ENTER.</span></span> <span data-ttu-id="8ac55-133">También puede cambiar el nombre de la directiva en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="8ac55-133">You can also change the name of the policy in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="8ac55-134">Haga clic en **versión 1.0**y, a continuación, haga clic en **AddNewRule**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-134">Right-click **Version 1.0**, and then click **AddNewRule**.</span></span>  
  
5. <span data-ttu-id="8ac55-135">Edite el nombre de la regla de **Rule1** a **ApprovalRule** y presione ENTRAR<strong>.</strong></span><span class="sxs-lookup"><span data-stu-id="8ac55-135">Edit the name of the rule from **Rule1** to **ApprovalRule** and press ENTER<strong>.</strong></span></span> <span data-ttu-id="8ac55-136">También puede cambiar el nombre de la regla en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="8ac55-136">You can also change the name of the rule in the **Properties** window.</span></span>  
  
6. <span data-ttu-id="8ac55-137">En la ventana Explorador de hechos, haga clic en el **esquemas XML** ficha.</span><span class="sxs-lookup"><span data-stu-id="8ac55-137">In the Facts Explorer window, click the **XML Schemas** tab.</span></span>  
  
7. <span data-ttu-id="8ac55-138">Haga clic en **esquemas**, haga clic en **examinar**y, a continuación, seleccione el **PO.xsd** archivo que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8ac55-138">Right-click **Schemas**, click **Browse**, and then select the **PO.xsd** file that you created earlier.</span></span>  
  
8. <span data-ttu-id="8ac55-139">En la ventana Propiedades, cambie el valor de la **tipo de documento** propiedad desde **PO** a **RuleTest.PO**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-139">In the properties window, change the value of the **Document Type** property from **PO** to **RuleTest.PO**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8ac55-140">Va a crear un proyecto de BizTalk denominado **RuleTest** más adelante en el [Tutorial: invocar la directiva desde una orquestación](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) tutorial.</span><span class="sxs-lookup"><span data-stu-id="8ac55-140">You will be creating a BizTalk project named **RuleTest** later in the [Walkthrough: Invoking the Policy from an Orchestration](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) walkthrough.</span></span> <span data-ttu-id="8ac55-141">En que el tutorial, agregará el **PO.xsd** al proyecto, cree una orquestación que invoca la **ProcessPurchaseOrder** directiva y, a continuación, probar la directiva.</span><span class="sxs-lookup"><span data-stu-id="8ac55-141">In that walkthrough, you will add the **PO.xsd** file to the project, create an orchestration that invokes the **ProcessPurchaseOrder** policy, and then test the policy.</span></span> <span data-ttu-id="8ac55-142">Para probar la directiva desde la orquestación, deberá asegurarse de que cambie el **tipo de documento** propiedad  **\<nombre del proyecto\>.\< SchemaName\>**, que es **RuleTest.PO** en este caso.</span><span class="sxs-lookup"><span data-stu-id="8ac55-142">To test the policy from the orchestration, you need to make sure that you change the **Document Type** property to **\<Project Name\>.\<SchemaName\>**, which is **RuleTest.PO** in this case.</span></span>  
  
    <span data-ttu-id="8ac55-143">![BRE&#45;tutorial&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span><span class="sxs-lookup"><span data-stu-id="8ac55-143">![BRE&#45;Walkthrough&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span></span>  
  
9. <span data-ttu-id="8ac55-144">En la ventana Explorador de hechos, expanda **PurchaseOrder**y, a continuación, expanda **elemento**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-144">In the Facts Explorer window, expand **PurchaseOrder**, and then expand **Item**.</span></span>  
  
10. <span data-ttu-id="8ac55-145">En el panel si (superior) de la derecha, haga clic en **condiciones**, haga clic en **predicados**y, a continuación, haga clic en **Menorqueigual**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-145">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **LessThanEqual**.</span></span>  
  
     <span data-ttu-id="8ac55-146">![Compositor de reglas de negocio &#45; menor o igual](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span><span class="sxs-lookup"><span data-stu-id="8ac55-146">![Business Rule Composer &#45; Less Than or Equal](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span></span>  
  
11. <span data-ttu-id="8ac55-147">Arrastre el **cantidad** nodo desde la ventana Explorador de hechos para **argumento1** en el panel IF.</span><span class="sxs-lookup"><span data-stu-id="8ac55-147">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  
  
     <span data-ttu-id="8ac55-148">![Compositor de reglas de negocio &#45; DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span><span class="sxs-lookup"><span data-stu-id="8ac55-148">![Business Rule Composer &#45; DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span></span>  
  
     <span data-ttu-id="8ac55-149">![Compositor de reglas de negocio&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span><span class="sxs-lookup"><span data-stu-id="8ac55-149">![Business Rule Composer&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span></span>  
  
12. <span data-ttu-id="8ac55-150">En el panel si, haga clic en **argumento2**, tipo `500`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8ac55-150">In the IF pane, click **argument2**, type `500`, and then press ENTER.</span></span>  
  
13. <span data-ttu-id="8ac55-151">Arrastre el **estado** nodo desde la ventana Explorador de hechos hasta el panel, a continuación, en la parte inferior derecha del compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="8ac55-151">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom-right side of Business Rule Composer.</span></span>  
  
     <span data-ttu-id="8ac55-152">![Compositor de reglas de negocio&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span><span class="sxs-lookup"><span data-stu-id="8ac55-152">![Business Rule Composer&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span></span>  
  
14. <span data-ttu-id="8ac55-153">En el panel entonces, haga clic en **\<escriba un valor\>** y, a continuación, escriba **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-153">In the THEN pane, click **\<Enter a value\>** and then type **Approved**.</span></span>  
  
15. <span data-ttu-id="8ac55-154">En la ventana Explorador de directivas, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ac55-154">In the Policy Explorer window, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="8ac55-155">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ac55-155">Comments</span></span>  
  
-   <span data-ttu-id="8ac55-156">Una directiva puede tener una o varias reglas.</span><span class="sxs-lookup"><span data-stu-id="8ac55-156">A policy can have one or more rules.</span></span> <span data-ttu-id="8ac55-157">Va a agregar otra regla **DeniedRule**, en el [Tutorial: agregar una regla a la directiva](../core/walkthrough-adding-a-rule-to-the-policy.md) tutorial.</span><span class="sxs-lookup"><span data-stu-id="8ac55-157">You will be adding another rule, **DeniedRule**, in the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough.</span></span>  
  
-   <span data-ttu-id="8ac55-158">Puede modificar la directiva para agregar más reglas, cambiar condiciones y modificar acciones cuando la directiva está en estado guardado.</span><span class="sxs-lookup"><span data-stu-id="8ac55-158">You can modify the policy to add more rules, change conditions, and change actions when the policy is in the Saved state.</span></span>  
  
-   <span data-ttu-id="8ac55-159">Puede dar prioridad a la ejecución de reglas mediante la especificación de la **prioridad** propiedad en las reglas de Compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="8ac55-159">You can prioritize execution of rules by specifying the **Priority** property on rules in Business Rule Composer.</span></span> <span data-ttu-id="8ac55-160">Por ejemplo, si hace clic en el **ApprovedRule** nodo en la ventana del explorador de directivas, puede ver el **prioridad** propiedad en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="8ac55-160">For example, if you click the **ApprovedRule** node in the Policy Explorer window, you can see the **Priority** property in the Properties window.</span></span> <span data-ttu-id="8ac55-161">Cuanto mayor es el número, mayor es la prioridad de la regla.</span><span class="sxs-lookup"><span data-stu-id="8ac55-161">The larger the number, the higher the rule priority.</span></span>  
  
-   <span data-ttu-id="8ac55-162">Puede usar un esquema XML, una base de datos o un ensamblado .NET como origen de datos para la directiva.</span><span class="sxs-lookup"><span data-stu-id="8ac55-162">You can use an XML schema, a database, or a .NET assembly as a data source for the policy.</span></span> <span data-ttu-id="8ac55-163">En este tutorial, se usó un esquema XML como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8ac55-163">In this walkthrough, you used an XML schema as a data source.</span></span> <span data-ttu-id="8ac55-164">Para ejecutar la directiva, debe enviar una instancia del documento XML del esquema como un hecho al motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="8ac55-164">You should submit an XML document instance of the schema as a fact to the rule engine to execute the policy.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8ac55-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ac55-165">Next Steps</span></span>  
 <span data-ttu-id="8ac55-166">Ahora que ha realizado este tutorial, realice el [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) tutorial, lo que le ofrece instrucciones paso a paso para probar la **ProcessPurchaseOrder** directiva se creó en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="8ac55-166">Now that you have completed this walkthrough, perform the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough, which gives you step-by-step instructions for testing the **ProcessPurchaseOrder** policy you created in this walkthrough.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac55-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ac55-167">See Also</span></span>  
 [<span data-ttu-id="8ac55-168">Acerca de las reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="8ac55-168">About Business Rules</span></span>](../core/about-business-rules.md)