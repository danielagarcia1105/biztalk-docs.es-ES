---
title: 'Paso 2: Crear los esquemas de aplicación de LOB de Contoso para el precio y disponibilidad del proyecto mediante el Editor de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB schemas
ms.assetid: 70e26dc9-4299-4d30-8f8b-5cc3469a2025
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f899a6614ea5d5d28c555be1b39e72b5880fe3ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999333"
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a><span data-ttu-id="15096-102">Paso 2: Creación de los esquemas de aplicación de LOB de Contoso para el proyecto precio y disponibilidad mediante el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="15096-102">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>
<span data-ttu-id="15096-103">En este paso, se genera el esquema se utiliza para consultar el sistema de ERP de Contoso para el precio y disponibilidad de un producto determinado.</span><span class="sxs-lookup"><span data-stu-id="15096-103">In this step, you generate the schema to use to query the Contoso ERP system for the price and availability of a particular product.</span></span> <span data-ttu-id="15096-104">Generar este esquema mediante el uso del adaptador de SQL de Microsoft® para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="15096-104">You generate this schema by using the Microsoft® SQL Adapter for BizTalk Server.</span></span>  

### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a><span data-ttu-id="15096-105">Para actualizar el código SQL el procedimiento almacenado para generar esquemas</span><span class="sxs-lookup"><span data-stu-id="15096-105">To update the SQL stored procedure for schema generation</span></span>  

1.  <span data-ttu-id="15096-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="15096-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  

2.  <span data-ttu-id="15096-107">En Microsoft SQL Server Management Studio, expanda **bases de datos**, expanda **Contoso**, expanda **programación**y, a continuación, expanda **procedimientos almacenados** .</span><span class="sxs-lookup"><span data-stu-id="15096-107">In the Microsoft SQL Server Management Studio, expand **Databases**, expand **Contoso**, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  

3.  <span data-ttu-id="15096-108">Haga clic en **dbo. SP_GetInventoryForProductID**y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="15096-108">Right-click **dbo.SP_GetInventoryForProductID**, and then click **Modify**.</span></span>  

4.  <span data-ttu-id="15096-109">En la ventana de consulta, insertar una coma, un espacio y, a continuación, "xmldata" inmediatamente después de "for xml auto".</span><span class="sxs-lookup"><span data-stu-id="15096-109">In the query window, insert a comma, a space, and then "xmldata" immediately following "for xml auto".</span></span> <span data-ttu-id="15096-110">La línea de código debería ser la siguiente:</span><span class="sxs-lookup"><span data-stu-id="15096-110">The line of code should be the following:</span></span>  

    ```  
    for xml auto, xmldata  
    ```  

5.  <span data-ttu-id="15096-111">Haga clic en **Execute** para guardar los cambios en el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="15096-111">Click **Execute** to save the changes to the stored procedure.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="15096-112">Deje que Microsoft SQL Server Management Studio abierta para el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="15096-112">Leave the Microsoft SQL Server Management Studio open for the next procedure.</span></span>  

### <a name="to-create-the-contoso-price-and-availability-schema"></a><span data-ttu-id="15096-113">Para crear el esquema Contoso Price y disponibilidad</span><span class="sxs-lookup"><span data-stu-id="15096-113">To create the Contoso Price and Availability schema</span></span>  

1. <span data-ttu-id="15096-114">Abra la solución de Contoso en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15096-114">Open the Contoso solution in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

2. <span data-ttu-id="15096-115">En el Explorador de soluciones, haga clic en el **ContosoPriceAndAvailability** , seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="15096-115">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, point to **Add**, and then click **Add Generated Items**.</span></span>  

3. <span data-ttu-id="15096-116">En el cuadro de diálogo Agregar fluyan generados con **agregar metadatos de adaptador** seleccionado en el panel izquierdo, haga clic en **agregar metadatos de adaptador** en el panel derecho y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="15096-116">In the Add Generated Iems dialog box, with **Add Adapter Metadata** selected in the left pane, click **Add Adapter Metadata** in the right pane, and then click **Add**.</span></span>  

4. <span data-ttu-id="15096-117">En el **Asistente para agregar adaptador** página, seleccione **SQL** en la lista de adaptadores registrados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="15096-117">On the **Add Adapter Wizard** page, select **SQL** from the list of registered adapters, and then click **Next**.</span></span>  

5. <span data-ttu-id="15096-118">En el **información de la base de datos** página, haga clic en **establecer**.</span><span class="sxs-lookup"><span data-stu-id="15096-118">On the **Database Information** page, click **Set**.</span></span>  

6. <span data-ttu-id="15096-119">En el cuadro de diálogo Propiedades de vínculo de datos, en el cuadro **Seleccione o escriba un nombre de servidor** , escriba **localhost**.</span><span class="sxs-lookup"><span data-stu-id="15096-119">In the Data Link Properties dialog box, in the **Select or enter a server name** box, type **localhost**.</span></span> <span data-ttu-id="15096-120">Seleccionar **Usar seguridad integrada de Windows**.</span><span class="sxs-lookup"><span data-stu-id="15096-120">Select **Use Windows NT Integrated security**.</span></span> <span data-ttu-id="15096-121">Para **seleccione la base de datos en el servidor**, seleccione el **Contoso** base de datos de la lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="15096-121">For **Select the database on the server**, select the **Contoso** database from the database list.</span></span> <span data-ttu-id="15096-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15096-122">Click **OK**.</span></span>  

7. <span data-ttu-id="15096-123">En el **información de la base de datos** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="15096-123">On the **Database Information** page, click **Next**.</span></span>  

8. <span data-ttu-id="15096-124">En el **información del esquema** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15096-124">On the **Schema Information** page, do the following:</span></span>  


   |                <span data-ttu-id="15096-125">Use</span><span class="sxs-lookup"><span data-stu-id="15096-125">Use this</span></span>                 |              <span data-ttu-id="15096-126">Para</span><span class="sxs-lookup"><span data-stu-id="15096-126">To do this</span></span>              |
   |-----------------------------------------|--------------------------------------|
   |          <span data-ttu-id="15096-127">**Espacio de nombres de destino**</span><span class="sxs-lookup"><span data-stu-id="15096-127">**Target namespace**</span></span>           | <span data-ttu-id="15096-128">Tipo **<http://Contoso.com/Price>**.</span><span class="sxs-lookup"><span data-stu-id="15096-128">Type **<http://Contoso.com/Price>**.</span></span> |
   |        <span data-ttu-id="15096-129">**Seleccione el tipo de puerto**</span><span class="sxs-lookup"><span data-stu-id="15096-129">**Select the port type**</span></span>         |        <span data-ttu-id="15096-130">Seleccione **puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="15096-130">Select **Send port**.</span></span>         |
   | <span data-ttu-id="15096-131">**Nombre de elemento raíz de documento de solicitud**</span><span class="sxs-lookup"><span data-stu-id="15096-131">**Request document root element name**</span></span>  |      <span data-ttu-id="15096-132">Tipo **rootPriceRequest**.</span><span class="sxs-lookup"><span data-stu-id="15096-132">Type **rootPriceRequest**.</span></span>      |
   | <span data-ttu-id="15096-133">**Nombre de elemento raíz de documento de respuesta**</span><span class="sxs-lookup"><span data-stu-id="15096-133">**Response document root element name**</span></span> |     <span data-ttu-id="15096-134">Tipo **rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="15096-134">Type **rootPriceResponse**.</span></span>      |


9. <span data-ttu-id="15096-135">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="15096-135">Click **Next**.</span></span>  

10. <span data-ttu-id="15096-136">En el **información de tipo de instrucción** página, seleccione **Stored Procedure**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="15096-136">On the **Statement type information** page, select **Stored Procedure**, and then click **Next**.</span></span>  

11. <span data-ttu-id="15096-137">En el **instrucción** página, para  **\<seleccionar un procedimiento almacenado\>**, seleccione **SP_GetInventoryForProductID** desde el lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="15096-137">On the **Statement Information** page, for **\<Select a stored procedure\>**, select **SP_GetInventoryForProductID** from the drop-down list.</span></span> <span data-ttu-id="15096-138">Haga clic en **generar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="15096-138">Click **Generate**, and then click **Next**.</span></span>  

12. <span data-ttu-id="15096-139">En el **completando el Asistente para generación de esquema de transporte SQL** página, haga clic en **finalizar** para importar el esquema en el proyecto de ContosoPriceAndAvailability BizTalk.</span><span class="sxs-lookup"><span data-stu-id="15096-139">On the **Completing the SQL Transport Schema Generation Wizard** page, click **Finish** to import the schema into the ContosoPriceAndAvailability BizTalk project.</span></span>  

13. <span data-ttu-id="15096-140">En el Explorador de soluciones, haga clic en el esquema generado (SQLService_Price.xsd), haga clic en **cambiar el nombre de**y el tipo **ContosoPriceAndAvailability.xsd** como el nuevo nombre para el esquema.</span><span class="sxs-lookup"><span data-stu-id="15096-140">In Solution Explorer, right-click the generated schema (SQLService_Price.xsd), click **Rename**, and type **ContosoPriceAndAvailability.xsd** as the new name for the schema.</span></span> <span data-ttu-id="15096-141">Haga clic en **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="15096-141">Click **Enter**.</span></span>  

14. <span data-ttu-id="15096-142">En la ventana Propiedades para el esquema ContosoPriceAndAvailability, establezca el **nombre de tipo** propiedad **ContosoPriceSchema**.</span><span class="sxs-lookup"><span data-stu-id="15096-142">In the Properties window for the ContosoPriceAndAvailability schema, set the **Type Name** property to **ContosoPriceSchema**.</span></span>  

15. <span data-ttu-id="15096-143">De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] crea una orquestación de BizTalk denominada **BizTalk Orchestration.odx**.</span><span class="sxs-lookup"><span data-stu-id="15096-143">By default, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] creates a BizTalk orchestration named **BizTalk Orchestration.odx**.</span></span> <span data-ttu-id="15096-144">Haga clic en esta orquestación y, a continuación, haga clic en **eliminar** porque no necesita esta orquestación.</span><span class="sxs-lookup"><span data-stu-id="15096-144">Right-click this orchestration, and then click **Delete** because you do not need this orchestration.</span></span> <span data-ttu-id="15096-145">En la ventana emergente que indica que se eliminará permanentemente la orquestación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15096-145">In the popup indicating that the orchestration will be deleted permanently, click **OK**.</span></span>  

16. <span data-ttu-id="15096-146">En Microsoft SQL Server Management Studio, quite el `xmldata` predicado y el punto y coma de los `SP_GetInventoryForProductID` el procedimiento almacenado que agregó en el paso anterior y, a continuación, haga clic en **Execute**.</span><span class="sxs-lookup"><span data-stu-id="15096-146">In the Microsoft SQL Server Management Studio, remove the `xmldata` predicate and the comma from the `SP_GetInventoryForProductID` stored procedure that you added in the previous step, and then click **Execute**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="15096-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="15096-147">See Also</span></span>  
 [<span data-ttu-id="15096-148">Paso 3: Creación de los mapas de aplicación de LOB de Contoso para el proyecto Precio y disponibilidad mediante el Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="15096-148">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)