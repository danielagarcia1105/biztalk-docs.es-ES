---
title: 'Tutorial: Usar hechos .NET y base de datos | Documentos de Microsoft'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 676d6e46-d9f8-477e-979e-1ac051ad4451
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b18b9b3188ce3d9fb478c3f2d4390d167e5566a9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976050"
---
# <a name="walkthrough-using-database-and-net-facts"></a><span data-ttu-id="6288e-102">Tutorial: Usar hechos .NET y base de datos</span><span class="sxs-lookup"><span data-stu-id="6288e-102">Walkthrough: Using Database and .NET Facts</span></span>
<span data-ttu-id="6288e-103">Este tutorial proporciona procedimientos descritos paso a paso para usar el Compositor de reglas de negocio con el fin de crear una directiva que utilice hechos de base de datos y .NET.</span><span class="sxs-lookup"><span data-stu-id="6288e-103">This walkthrough provides step-by-step procedures for using the Business Rule Composer to create a policy that uses database and .NET facts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6288e-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6288e-104">Prerequisites</span></span>  
 <span data-ttu-id="6288e-105">Debe establecer el valor de la **StaticSupport** clave del registro en 1 o 2 antes de llevar a cabo el tutorial.</span><span class="sxs-lookup"><span data-stu-id="6288e-105">You must set the value of the **StaticSupport** registry key to 1 or 2 before performing the walkthrough.</span></span> <span data-ttu-id="6288e-106">De este modo, permitirá que la directiva invoque los métodos estáticos de una clase .NET sin necesidad de que el cliente imponga una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="6288e-106">This allows the policy to invoke the static methods of a .NET class without requiring the client to assert an instance of the class.</span></span> <span data-ttu-id="6288e-107">Para obtener más información, consulte [invocar miembros estáticos de una clase](../core/invoking-static-members-of-a-class.md).</span><span class="sxs-lookup"><span data-stu-id="6288e-107">For more information, see [Invoking Static Members of a Class](../core/invoking-static-members-of-a-class.md).</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="6288e-108">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="6288e-108">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="6288e-109">Este tutorial contiene cinco procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6288e-109">This walkthrough contains five procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="6288e-110">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="6288e-110">Procedure title</span></span>|<span data-ttu-id="6288e-111">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="6288e-111">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="6288e-112">Para crear la base de datos TestDB y la tabla PO</span><span class="sxs-lookup"><span data-stu-id="6288e-112">To create the TestDB database and the PO table</span></span>|<span data-ttu-id="6288e-113">Proporciona instrucciones paso a paso para crear la **TestDB** base de datos y la **PO** tabla.</span><span class="sxs-lookup"><span data-stu-id="6288e-113">Provides step-by-step instructions for creating the **TestDB** database and the **PO** table.</span></span>|  
|<span data-ttu-id="6288e-114">Para crear el componente POUtility</span><span class="sxs-lookup"><span data-stu-id="6288e-114">To create the POUtility component</span></span>|<span data-ttu-id="6288e-115">Proporciona instrucciones paso a paso para crear la **POUtility** componente.</span><span class="sxs-lookup"><span data-stu-id="6288e-115">Provides step-by-step instructions for creating the **POUtility** component.</span></span>|  
|<span data-ttu-id="6288e-116">Para crear la directiva empresarial ProcessPurchaseOrderDbNet</span><span class="sxs-lookup"><span data-stu-id="6288e-116">To create the ProcessPurchaseOrderDbNet business policy</span></span>|<span data-ttu-id="6288e-117">Proporciona instrucciones paso a paso para crear la **ProcessPurchaseOrderDbNet** directiva.</span><span class="sxs-lookup"><span data-stu-id="6288e-117">Provides step-by-step instructions for creating the **ProcessPurchaseOrderDbNet** policy.</span></span>|  
|<span data-ttu-id="6288e-118">Para probar la directiva ProcessPurchaseOrderDbNet mediante el Compositor de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="6288e-118">To test the ProcessPurchaseOrderDbNet policy by using the Business Rule Composer</span></span>|<span data-ttu-id="6288e-119">Proporciona instrucciones paso a paso para utilizar el Compositor de reglas de negocio para probar el **ProcessPurchaseOrderDbNet** directiva.</span><span class="sxs-lookup"><span data-stu-id="6288e-119">Provides step-by-step instructions for using the Business Rule Composer to test the **ProcessPurchaseOrderDbNet** policy.</span></span>|  
|<span data-ttu-id="6288e-120">Para probar la directiva ProcessPurchaseOrderDbNet mediante el método Policy.Execute</span><span class="sxs-lookup"><span data-stu-id="6288e-120">To test the ProcessPurchaseOrderDbNet policy by using the Policy.Execute method</span></span>|<span data-ttu-id="6288e-121">Proporciona instrucciones paso a paso para probar el **ProcessPurchaseOrderDbNet** directiva mediante el uso de la **Policy.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="6288e-121">Provides step-by-step instructions for testing the **ProcessPurchaseOrderDbNet** policy by using the **Policy.Execute** method.</span></span>|  
  
### <a name="to-create-the-testdb-database-and-the-po-table"></a><span data-ttu-id="6288e-122">Para crear la base de datos TestDB y la tabla PO</span><span class="sxs-lookup"><span data-stu-id="6288e-122">To create the TestDB database and the PO table</span></span>  
  
1.  <span data-ttu-id="6288e-123">Abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="6288e-123">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="6288e-124">Compruebe el nombre del servidor y la autenticación y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-124">Verify the server name and authentication, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="6288e-125">En la ventana Explorador de objetos de la izquierda, haga clic en el nombre del equipo y, a continuación, haga clic en **nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6288e-125">In the Object Explorer window on the left, right-click the computer name, and then click **New Query**.</span></span>  
  
4.  <span data-ttu-id="6288e-126">Copie las siguientes instrucciones SQL en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="6288e-126">Copy the following SQL statements to the query window:</span></span>  
  
    ```  
    CREATE DATABASE [TestDB]  
    GO  
  
    Use TestDB  
    CREATE TABLE [dbo].[PO]([PONumber] [nvarchar](50) NOT NULL,  
    [Quantity] [int] NOT NULL,  
    [Status] [nchar](10) NULL  
    CONSTRAINT [PK_PO] PRIMARY KEY CLUSTERED ([PONumber] ASC))   
    GO  
  
    INSERT INTO PO VALUES ('PO1', 400, NULL)  
    INSERT INTO PO VALUES ('PO2', 700, NULL)  
    GO  
    ```  
  
5.  <span data-ttu-id="6288e-127">Presione F5 para ejecutar la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="6288e-127">Press F5 to execute the SQL query.</span></span>  
  
6.  <span data-ttu-id="6288e-128">En la ventana Explorador de objetos, expanda el nombre del equipo, **bases de datos**y, a continuación, compruebe que **TestDB** existe.</span><span class="sxs-lookup"><span data-stu-id="6288e-128">In the Object Explorer window, expand the computer name, expand **Databases**, and then verify that **TestDB** exists.</span></span>  
  
7.  <span data-ttu-id="6288e-129">Expanda **TestDB**, expanda **tablas**y, a continuación, compruebe que **dbo. Pedido de compra** existe.</span><span class="sxs-lookup"><span data-stu-id="6288e-129">Expand **TestDB**, expand **Tables**, and then verify that **dbo.PO** exists.</span></span>  
  
8.  <span data-ttu-id="6288e-130">Haga clic en **dbo. Pedido de compra**y, a continuación, haga clic en **Abrir tabla** para comprobar la existen de los siguientes datos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="6288e-130">Right-click **dbo.PO**, and then click **Open Table** to verify that the following data exists in the table.</span></span>  
  
    |<span data-ttu-id="6288e-131">PONumber</span><span class="sxs-lookup"><span data-stu-id="6288e-131">PONumber</span></span>|<span data-ttu-id="6288e-132">Cantidad</span><span class="sxs-lookup"><span data-stu-id="6288e-132">Quantity</span></span>|<span data-ttu-id="6288e-133">Estado</span><span class="sxs-lookup"><span data-stu-id="6288e-133">Status</span></span>|  
    |--------------|--------------|------------|  
    |<span data-ttu-id="6288e-134">PO1</span><span class="sxs-lookup"><span data-stu-id="6288e-134">PO1</span></span>|<span data-ttu-id="6288e-135">400</span><span class="sxs-lookup"><span data-stu-id="6288e-135">400</span></span>|<span data-ttu-id="6288e-136">NULL</span><span class="sxs-lookup"><span data-stu-id="6288e-136">NULL</span></span>|  
    |<span data-ttu-id="6288e-137">PO2</span><span class="sxs-lookup"><span data-stu-id="6288e-137">PO2</span></span>|<span data-ttu-id="6288e-138">700</span><span class="sxs-lookup"><span data-stu-id="6288e-138">700</span></span>|<span data-ttu-id="6288e-139">NULL</span><span class="sxs-lookup"><span data-stu-id="6288e-139">NULL</span></span>|  
  
### <a name="to-create-the-poutility-component"></a><span data-ttu-id="6288e-140">Para crear el componente POUtility</span><span class="sxs-lookup"><span data-stu-id="6288e-140">To create the POUtility component</span></span>  
  
1.  <span data-ttu-id="6288e-141">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="6288e-141">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="6288e-142">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6288e-142">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="6288e-143">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6288e-143">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6288e-144">Use</span><span class="sxs-lookup"><span data-stu-id="6288e-144">Use this</span></span>|<span data-ttu-id="6288e-145">Para</span><span class="sxs-lookup"><span data-stu-id="6288e-145">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6288e-146">**Tipos de proyecto**</span><span class="sxs-lookup"><span data-stu-id="6288e-146">**Project types**</span></span>|<span data-ttu-id="6288e-147">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="6288e-147">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="6288e-148">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="6288e-148">**Templates**</span></span>|<span data-ttu-id="6288e-149">Haga clic en **biblioteca de clases**.</span><span class="sxs-lookup"><span data-stu-id="6288e-149">Click **Class Library**.</span></span>|  
    |<span data-ttu-id="6288e-150">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6288e-150">**Name**</span></span>|<span data-ttu-id="6288e-151">Tipo de **POUtilityLib**.</span><span class="sxs-lookup"><span data-stu-id="6288e-151">Type **POUtilityLib**.</span></span>|  
    |<span data-ttu-id="6288e-152">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="6288e-152">**Location**</span></span>|<span data-ttu-id="6288e-153">Especifique **C:\BRE-Walkthroughs** como la ubicación.</span><span class="sxs-lookup"><span data-stu-id="6288e-153">Specify **C:\BRE-Walkthroughs** as the location.</span></span>|  
    |<span data-ttu-id="6288e-154">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="6288e-154">**Solution Name**</span></span>|<span data-ttu-id="6288e-155">Tipo de **POUtilitySol**.</span><span class="sxs-lookup"><span data-stu-id="6288e-155">Type **POUtilitySol**.</span></span>|  
    |<span data-ttu-id="6288e-156">**Crear directorio para la solución**</span><span class="sxs-lookup"><span data-stu-id="6288e-156">**Create directory for solution**</span></span>|<span data-ttu-id="6288e-157">Seleccione esta casilla para crear un directorio para los archivos de la solución.</span><span class="sxs-lookup"><span data-stu-id="6288e-157">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="6288e-158">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-158">Click **OK**.</span></span> <span data-ttu-id="6288e-159">El **POUtilityLib** proyecto debe aparecer en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="6288e-159">The **POUtilityLib** project should appear in Solution Explorer.</span></span> <span data-ttu-id="6288e-160">Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="6288e-160">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="6288e-161">En la ventana Propiedades, cambie el nombre del archivo, **Class1.cs**a **POUtility.cs**.</span><span class="sxs-lookup"><span data-stu-id="6288e-161">In the Properties window, change the name of the file, **Class1.cs**, to **POUtility.cs**.</span></span>  
  
6.  <span data-ttu-id="6288e-162">Agregue un constructor público a la clase como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6288e-162">Add a public constructor to the class as shown in the following code:</span></span>  
  
    ```  
    public POUtility()  
    {  
    }  
    ```  
  
7.  <span data-ttu-id="6288e-163">Agregar un método estático denominado **GetMaxAllowed** a la **POUtility** clase tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6288e-163">Add a static method named **GetMaxAllowed** to the **POUtility** class as shown in the following code:</span></span>  
  
    ```  
    public static int GetMaxAllowed()  
    {  
    return 500;  
    }   
    ```  
  
8.  <span data-ttu-id="6288e-164">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="6288e-164">Start **Visual Studio Command Prompt**.</span></span>  
  
9. <span data-ttu-id="6288e-165">Cambie el directorio a **C:\BRE-Walkthroughs\POUtilitySol**y, a continuación, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="6288e-165">Change the directory to **C:\BRE-Walkthroughs\POUtilitySol**, and then execute the following command:</span></span>  
  
     <span data-ttu-id="6288e-166">**Sn -k POUtility.snk**</span><span class="sxs-lookup"><span data-stu-id="6288e-166">**Sn -k POUtility.snk**</span></span>  
  
10. <span data-ttu-id="6288e-167">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, expanda **propiedades**y, a continuación, haga doble clic en **AssemblyInfo.cs**.</span><span class="sxs-lookup"><span data-stu-id="6288e-167">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, expand **Properties**, and then double-click **AssemblyInfo.cs**.</span></span>  
  
11. <span data-ttu-id="6288e-168">Agregue la instrucción siguiente a la **AssemblyInfo.cs** archivo al final:</span><span class="sxs-lookup"><span data-stu-id="6288e-168">Add the following statement to the **AssemblyInfo.cs** file at the end:</span></span>  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POUtilitySol\POUtility.snk")]  
    ```  
  
12. <span data-ttu-id="6288e-169">En la ventana Explorador de soluciones, haga clic en **POUtilityLib**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-169">In the Solution Explorer window, right-click **POUtilityLib**, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="6288e-170">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie al directorio **C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**y, a continuación, ejecute el siguiente comando para registrar el componente POUtility en la GAC (global caché de ensamblados).</span><span class="sxs-lookup"><span data-stu-id="6288e-170">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt, change the directory to **C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**, and then execute the following command to register the POUtility component with the GAC (global assembly cache).</span></span> <span data-ttu-id="6288e-171">Si el símbolo del sistema no está abierto, siga el paso 8 para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="6288e-171">If you do not have the command prompt open, follow step 8 to open it.</span></span>  
  
     <span data-ttu-id="6288e-172">**Gacutil -i POUtilityLib.dll**</span><span class="sxs-lookup"><span data-stu-id="6288e-172">**Gacutil -i POUtilityLib.dll**</span></span>  
  
### <a name="to-create-the-processpurchaseorderdbnet-business-policy"></a><span data-ttu-id="6288e-173">Para crear la directiva empresarial ProcessPurchaseOrderDbNet</span><span class="sxs-lookup"><span data-stu-id="6288e-173">To create the ProcessPurchaseOrderDbNet business policy</span></span>  
  
1.  <span data-ttu-id="6288e-174">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="6288e-174">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="6288e-175">Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="6288e-175">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6288e-176">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6288e-176">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="6288e-177">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="6288e-177">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="6288e-178">En la ventana Explorador de hechos, haga clic en **bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="6288e-178">In the Facts Explorer window, click **Databases**.</span></span>  
  
3.  <span data-ttu-id="6288e-179">Haga clic en **servidores**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-179">Right-click **Servers**, and then click **Browse**.</span></span>  
  
4.  <span data-ttu-id="6288e-180">Compruebe la información de autenticación de servidor y y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-180">Verify the server and authentication information, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6288e-181">Expanda **TestDB**y, a continuación, expanda **pedido**.</span><span class="sxs-lookup"><span data-stu-id="6288e-181">Expand **TestDB**, and then expand **PO**.</span></span>  
  
6.  <span data-ttu-id="6288e-182">En la ventana Explorador de hechos, haga clic en **clases .NET**.</span><span class="sxs-lookup"><span data-stu-id="6288e-182">In the Facts Explorer window, click **.NET Classes**.</span></span>  
  
7.  <span data-ttu-id="6288e-183">Haga clic en **. NETAssemblies**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-183">Right-click **.NETAssemblies**, and then click **Browse**.</span></span>  
  
8.  <span data-ttu-id="6288e-184">Seleccione **POUtility**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-184">Select **POUtility**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="6288e-185">Expanda **Class1**.</span><span class="sxs-lookup"><span data-stu-id="6288e-185">Expand **Class1**.</span></span>  
  
10. <span data-ttu-id="6288e-186">En la ventana Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="6288e-186">In the Policy Explorer window, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
11. <span data-ttu-id="6288e-187">Cambiar el nombre de la directiva de **Policy1** a **ProcessPurchaseOrderDbNet** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6288e-187">Change the name of the policy from **Policy1** to **ProcessPurchaseOrderDbNet** and then press ENTER.</span></span> <span data-ttu-id="6288e-188">También puede cambiar el nombre de la directiva en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="6288e-188">You can also change the name of the policy in the Properties window.</span></span>  
  
12. <span data-ttu-id="6288e-189">Haga clic en **versión 1.0**y, a continuación, haga clic en **AddNewRule**.</span><span class="sxs-lookup"><span data-stu-id="6288e-189">Right-click **Version 1.0**, and then click **AddNewRule**.</span></span>  
  
13. <span data-ttu-id="6288e-190">Cambiar el nombre de la regla de **Rule1** a **ApprovalRule** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6288e-190">Change the name of the rule from **Rule1** to **ApprovalRule** and then press ENTER.</span></span> <span data-ttu-id="6288e-191">También puede cambiar el nombre de la regla en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="6288e-191">You can also change the name of the rule in the Properties window.</span></span>  
  
14. <span data-ttu-id="6288e-192">En el panel si (superior) a la derecha, haga clic en **condiciones**, haga clic en **predicados**y, a continuación, haga clic en **Menorqueigual**.</span><span class="sxs-lookup"><span data-stu-id="6288e-192">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **LessThanEqual**.</span></span>  
  
15. <span data-ttu-id="6288e-193">En la ventana Explorador de hechos, haga clic en **bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="6288e-193">In the Facts Explorer window, click **Databases**.</span></span>  
  
16. <span data-ttu-id="6288e-194">Arrastre el **cantidad** nodo desde la ventana Explorador de hechos hasta **argumento1** en el panel si.</span><span class="sxs-lookup"><span data-stu-id="6288e-194">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  
  
17. <span data-ttu-id="6288e-195">En la ventana Explorador de hechos, haga clic en **clases .NET**.</span><span class="sxs-lookup"><span data-stu-id="6288e-195">In the Facts Explorer window, click **.NET Classes**.</span></span>  
  
18. <span data-ttu-id="6288e-196">Arrastre **GetMaxAllowed** nodo desde la ventana Explorador de hechos hasta **argumento2** en el panel si.</span><span class="sxs-lookup"><span data-stu-id="6288e-196">Drag **GetMaxAllowed** node from the Facts Explorer window to **argument2** in the IF pane.</span></span>  
  
19. <span data-ttu-id="6288e-197">En la ventana Explorador de hechos, haga clic en **bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="6288e-197">In the Facts Explorer window, click **Databases**.</span></span>  
  
20. <span data-ttu-id="6288e-198">Arrastre el **estado** nodo desde la ventana Explorador de hechos hasta el panel, a continuación, en la parte inferior derecha del compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="6288e-198">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom right of the Business Rule Composer.</span></span>  
  
21. <span data-ttu-id="6288e-199">En el panel, a continuación, haga clic en  **\<escriba un valor\>**  y, a continuación, escriba **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="6288e-199">In the THEN pane, click **\<Enter a value\>** and then type **Approved**.</span></span>  
  
22. <span data-ttu-id="6288e-200">En la ventana Explorador de hechos, haga clic en **versión 1.0** en **ProcessPurchaseOrderDbNet**y, a continuación, haga clic en **AddNewRule**.</span><span class="sxs-lookup"><span data-stu-id="6288e-200">In the Facts Explorer window, right-click **Version 1.0** in **ProcessPurchaseOrderDbNet**, and then click **AddNewRule**.</span></span>  
  
23. <span data-ttu-id="6288e-201">Cambiar el nombre de la regla de **Rule1** a **DeniedRule** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6288e-201">Change the name of the rule from **Rule1** to **DeniedRule** and then press ENTER.</span></span> <span data-ttu-id="6288e-202">También puede cambiar el nombre de la regla en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="6288e-202">You can also change the name of the rule in the Properties window.</span></span>  
  
24. <span data-ttu-id="6288e-203">En el panel si (superior) a la derecha, haga clic en **condiciones**, haga clic en **predicados**y, a continuación, haga clic en **GreaterThan**.</span><span class="sxs-lookup"><span data-stu-id="6288e-203">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **GreaterThan**.</span></span>  
  
25. <span data-ttu-id="6288e-204">En la ventana Explorador de hechos, haga clic en **bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="6288e-204">In the Facts Explorer window, click **Databases**.</span></span>  
  
26. <span data-ttu-id="6288e-205">Arrastre el **cantidad** nodo desde la ventana Explorador de hechos hasta **argumento1** en el panel si.</span><span class="sxs-lookup"><span data-stu-id="6288e-205">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  
  
27. <span data-ttu-id="6288e-206">En la ventana Explorador de hechos, haga clic en **clases .NET**.</span><span class="sxs-lookup"><span data-stu-id="6288e-206">In the Facts Explorer window, click **.NET Classes**.</span></span>  
  
28. <span data-ttu-id="6288e-207">Arrastre el **GetMaxAllowed** nodo desde la ventana Explorador de hechos hasta **argumento2** en el panel si.</span><span class="sxs-lookup"><span data-stu-id="6288e-207">Drag the **GetMaxAllowed** node from the Facts Explorer window to **argument2** in the IF pane.</span></span>  
  
29. <span data-ttu-id="6288e-208">En la ventana Explorador de hechos, haga clic en **bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="6288e-208">In the Facts Explorer window, click **Databases**.</span></span>  
  
30. <span data-ttu-id="6288e-209">Arrastre el **estado** nodo desde la ventana Explorador de hechos hasta el panel, a continuación, en la parte inferior derecha del compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="6288e-209">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom right of the Business Rule Composer.</span></span>  
  
31. <span data-ttu-id="6288e-210">En el panel, a continuación, haga clic en  **\<escriba un valor\>**  y, a continuación, escriba **denegado**.</span><span class="sxs-lookup"><span data-stu-id="6288e-210">In the THEN pane, click **\<Enter a value\>** and then type **Denied**.</span></span>  
  
32. <span data-ttu-id="6288e-211">En la ventana Explorador de directivas, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-211">In the Policy Explorer window, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-business-rule-composer"></a><span data-ttu-id="6288e-212">Para probar la directiva ProcessPurchaseOrderDbNet mediante el Compositor de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="6288e-212">To test the ProcessPurchaseOrderDbNet policy by using the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="6288e-213">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="6288e-213">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="6288e-214">Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="6288e-214">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="6288e-215">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrderDbNet**, haga clic en **versión 1.0**y, a continuación, haga clic en **probar directiva** .</span><span class="sxs-lookup"><span data-stu-id="6288e-215">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrderDbNet**, right-click **Version 1.0**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="6288e-216">Haga clic en **TestDB: PO (conexión de datos)** y, a continuación, haga clic en **Agregar instancia**.</span><span class="sxs-lookup"><span data-stu-id="6288e-216">Click **TestDB:PO (Data Connection)**, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="6288e-217">En el **conectar con SQL Server** cuadro de diálogo, compruebe la información de nombre y la autenticación de servidor y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-217">In the **Connect to SQL Server** dialog box, verify the server name and authentication information, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6288e-218">En el **Seleccionar enlace** cuadro de diálogo, expanda **TestDB**, haga clic en **pedido**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-218">In the **Select Binding** dialog box, expand **TestDB**, click **PO**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="6288e-219">Haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="6288e-219">Click **Test**.</span></span>  
  
7.  <span data-ttu-id="6288e-220">En la ventana resultados, compruebe que tanto el **ApprovalRule** y **DeniedRule** se activan.</span><span class="sxs-lookup"><span data-stu-id="6288e-220">In the Output window, verify that both the **ApprovalRule** and the **DeniedRule** are fired.</span></span>  
  
8.  <span data-ttu-id="6288e-221">En SQL Server Management Studio, haga clic en **dbo. Pedido de compra**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="6288e-221">In SQL Server Management Studio, right-click **dbo.PO**, and then click **Open Table**.</span></span>  
  
9. <span data-ttu-id="6288e-222">Compruebe que el valor de la **estado** campo está establecido en **aprobado** para el primer registro.</span><span class="sxs-lookup"><span data-stu-id="6288e-222">Verify that the value of the **Status** field is set to **Approved** for the first record.</span></span>  
  
10. <span data-ttu-id="6288e-223">Compruebe que el valor de la **estado** campo está establecido en **denegado** para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="6288e-223">Verify that the value of the **Status** field is set to **Denied** for the second record.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6288e-224">Si aún aparece el valor de la **estado** campo como NULL, haga clic en la lista que contiene los datos y, a continuación, haga clic en **ejecutar SQL**, que actualiza la vista.</span><span class="sxs-lookup"><span data-stu-id="6288e-224">If you still see the value of the **Status** field as NULL, right-click the list containing the data, and then click **Execute SQL**, which refreshes the view.</span></span>  
  
11. <span data-ttu-id="6288e-225">Mantenga abierta la aplicación SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="6288e-225">Keep SQL Server Management Studio open.</span></span>  
  
### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-policyexecute-method"></a><span data-ttu-id="6288e-226">Para probar la directiva ProcessPurchaseOrderDbNet mediante el método Policy.Execute</span><span class="sxs-lookup"><span data-stu-id="6288e-226">To test the ProcessPurchaseOrderDbNet policy by using the Policy.Execute method</span></span>  
  
1.  <span data-ttu-id="6288e-227">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="6288e-227">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="6288e-228">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6288e-228">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="6288e-229">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6288e-229">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6288e-230">Use</span><span class="sxs-lookup"><span data-stu-id="6288e-230">Use this</span></span>|<span data-ttu-id="6288e-231">Para</span><span class="sxs-lookup"><span data-stu-id="6288e-231">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6288e-232">**Tipos de proyecto**</span><span class="sxs-lookup"><span data-stu-id="6288e-232">**Project types**</span></span>|<span data-ttu-id="6288e-233">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="6288e-233">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="6288e-234">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="6288e-234">**Templates**</span></span>|<span data-ttu-id="6288e-235">Haga clic en **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="6288e-235">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="6288e-236">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6288e-236">**Name**</span></span>|<span data-ttu-id="6288e-237">Tipo de **TestProcessPODbNet**.</span><span class="sxs-lookup"><span data-stu-id="6288e-237">Type **TestProcessPODbNet**.</span></span>|  
    |<span data-ttu-id="6288e-238">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="6288e-238">**Location**</span></span>|<span data-ttu-id="6288e-239">Especifique **C:\BRE-Walkthroughs** como la ubicación.</span><span class="sxs-lookup"><span data-stu-id="6288e-239">Specify **C:\BRE-Walkthroughs** as the location.</span></span>|  
    |<span data-ttu-id="6288e-240">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="6288e-240">**Solution Name**</span></span>|<span data-ttu-id="6288e-241">Tipo de **TestProcessPODbNetSol**.</span><span class="sxs-lookup"><span data-stu-id="6288e-241">Type **TestProcessPODbNetSol**.</span></span>|  
    |<span data-ttu-id="6288e-242">**Crear directorio para la solución**</span><span class="sxs-lookup"><span data-stu-id="6288e-242">**Create directory for solution**</span></span>|<span data-ttu-id="6288e-243">Seleccione esta casilla para crear un directorio para los archivos de la solución.</span><span class="sxs-lookup"><span data-stu-id="6288e-243">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="6288e-244">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-244">Click **OK**.</span></span> <span data-ttu-id="6288e-245">El **TestProcessPODbNet** proyecto debe aparecer en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="6288e-245">The **TestProcessPODbNet** project should appear in Solution Explorer.</span></span> <span data-ttu-id="6288e-246">Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="6288e-246">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="6288e-247">En el Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="6288e-247">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="6288e-248">Haga clic en **examinar**, vaya a **\Program Files\Common Files\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.RuleEngine.dll**.</span><span class="sxs-lookup"><span data-stu-id="6288e-248">Click **Browse**, browse to **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  
  
7.  <span data-ttu-id="6288e-249">Agregue el código siguiente a la parte superior de la **Program.cs** archivo después de las existentes `using` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="6288e-249">Add the following code to the top of the **Program.cs** file after the existing `using` statements:</span></span>  
  
    ```  
    //To use the SQLConnection class  
    using System.Data.SqlClient;  
  
    //To use the Policy and DataConnection classes  
    using Microsoft.RuleEngine;  
    ```  
  
8.  <span data-ttu-id="6288e-250">Agregue el código siguiente a la **Main** función para crear y abrir un **SQLConnection** objeto:</span><span class="sxs-lookup"><span data-stu-id="6288e-250">Add the following code to the **Main** function to create and open a **SQLConnection** object:</span></span>  
  
    ```  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    ```  
  
9. <span data-ttu-id="6288e-251">Agregue el código siguiente a la **Main** función al final para crear una **DataConnection** objeto basado en la **SQLConnection** objeto creado en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="6288e-251">Add the following code to the **Main** function at the end to create a **DataConnection** object based on the **SQLConnection** object you created in the previous step:</span></span>  
  
    ```  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    ```  
  
10. <span data-ttu-id="6288e-252">Agregue el código siguiente a la **Main** función al final para crear una **directiva** de objetos y ejecutar la directiva:</span><span class="sxs-lookup"><span data-stu-id="6288e-252">Add the following code to the **Main** function at the end to create a **Policy** object and execute the policy:</span></span>  
  
    ```  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    ```  
  
11. <span data-ttu-id="6288e-253">Agregue el código siguiente a la **Main** función al final para actualizar la base de datos:</span><span class="sxs-lookup"><span data-stu-id="6288e-253">Add the following code to the **Main** function at the end to update the database:</span></span>  
  
    ```  
    dc.Update();  
    ```  
  
12. <span data-ttu-id="6288e-254">Agregue el código siguiente a la **Main** función al final para cerrar la conexión con la base de datos:</span><span class="sxs-lookup"><span data-stu-id="6288e-254">Add the following code to the **Main** function at the end to close the connection to the database:</span></span>  
  
    ```  
    cn.Close();  
    ```  
  
13. <span data-ttu-id="6288e-255">Agregar un bloque try-catch para detectar las excepciones generadas en el **Main** método.</span><span class="sxs-lookup"><span data-stu-id="6288e-255">Add a try-catch block to catch any exception generated in the **Main** method.</span></span>  
  
14. <span data-ttu-id="6288e-256">Compruebe que el código completo de la **Main** función es como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6288e-256">Verify that the complete code for the **Main** function is as shown in the following code:</span></span>  
  
    ```  
    try  
    {  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    dc.Update();  
    cn.Close();  
    }  
    catch (Exception ex)  
    {  
    Console.WriteLine(ex.Message);  
    }  
    ```  
  
15. <span data-ttu-id="6288e-257">En el **generar** menú, haga clic en **generar TestProcessPODbNet**.</span><span class="sxs-lookup"><span data-stu-id="6288e-257">On the **Build** menu, click **Build TestProcessPODbNet**.</span></span>  
  
16. <span data-ttu-id="6288e-258">En el Compositor de reglas de negocio, expanda **directivas**, expanda **ProcessPurchaseOrderDbNet**, haga clic en **versión 1.0**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-258">In the Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrderDbNet**, right-click **Version 1.0**, and then click **Publish**.</span></span>  
  
17. <span data-ttu-id="6288e-259">Haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="6288e-259">Right-click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
18. <span data-ttu-id="6288e-260">En SQL Server Management Studio, establezca el valor de la **estado** campo **NULL** para los registros de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="6288e-260">In SQL Server Management Studio, set the value of the **Status** field to **NULL** for both the PO records.</span></span>  
  
19. <span data-ttu-id="6288e-261">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], presione CTRL + F5 para ejecutar el **TestProcessPODbNet** aplicación.</span><span class="sxs-lookup"><span data-stu-id="6288e-261">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], Press CTRL+F5 to execute the **TestProcessPODbNet** application.</span></span>  
  
20. <span data-ttu-id="6288e-262">Presione cualquier tecla para cerrar la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="6288e-262">Press any key to close the command prompt window.</span></span>  
  
21. <span data-ttu-id="6288e-263">En SQL Server Management Studio, haga clic en la tabla con registros de pedido de compra y, a continuación, haga clic en **ejecutar SQL**.</span><span class="sxs-lookup"><span data-stu-id="6288e-263">In SQL Server Management Studio, right-click the table with PO records, and then click **Execute SQL**.</span></span>  
  
22. <span data-ttu-id="6288e-264">Compruebe que el valor de la **estado** campo está establecido en **aprobado** para el primer registro.</span><span class="sxs-lookup"><span data-stu-id="6288e-264">Verify that the value of the **Status** field is set to **Approved** for the first record.</span></span>  
  
23. <span data-ttu-id="6288e-265">Compruebe que el valor de la **estado** campo está establecido en **denegado** para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="6288e-265">Verify that the value of the **Status** field is set to **Denied** for the second record.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="6288e-266">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6288e-266">Comments</span></span>  
  
-   <span data-ttu-id="6288e-267">Si una directiva utiliza los métodos no estáticos de una clase .NET, deberá usar un componente de creador de hechos que imponga una instancia de la clase .NET para probar la directiva mediante el Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="6288e-267">If a policy uses the non-static methods of a .NET class, you need to use a fact creator component that asserts an instance of the .NET class to test the policy by using the Business Rule Composer.</span></span>  
  
-   <span data-ttu-id="6288e-268">Es muy importante recordar que el Compositor de reglas de negocios crea una instancia de la **DataConnection** de objeto y la impone en la memoria de trabajo del motor de reglas automáticamente para usted.</span><span class="sxs-lookup"><span data-stu-id="6288e-268">It is very important to remember that the Business Rule Composer creates an instance of the **DataConnection** object and asserts it into the working memory of the rule engine automatically for you.</span></span> <span data-ttu-id="6288e-269">Sin embargo, cuando se invoca la directiva desde una aplicación cliente (BizTalk o no sean de BizTalk), el **DataConnection** objeto no se crea automáticamente para usted.</span><span class="sxs-lookup"><span data-stu-id="6288e-269">However, when you invoke the policy from a client (BizTalk or non-BizTalk) application, the **DataConnection** object is not created automatically for you.</span></span> <span data-ttu-id="6288e-270">El cliente debe crear una **DataConnection** objeto y pasarlo como parámetro o hecho al motor de reglas para ejecutar la directiva.</span><span class="sxs-lookup"><span data-stu-id="6288e-270">The client should create a **DataConnection** object and pass it as a parameter or fact to the rule engine to execute the policy.</span></span>  
  
-   <span data-ttu-id="6288e-271">Puede usar el **DebugTrackingInterceptor** clase para realizar el seguimiento de los detalles de ejecución de directiva.</span><span class="sxs-lookup"><span data-stu-id="6288e-271">You can use the **DebugTrackingInterceptor** class to track the policy execution details.</span></span> <span data-ttu-id="6288e-272">El código de ejemplo siguiente muestra cómo crear una instancia de la **DebugTrackingInterceptor** clase y utilizarla al ejecutar la directiva:</span><span class="sxs-lookup"><span data-stu-id="6288e-272">The following sample code shows how to create an instance of the **DebugTrackingInterceptor** class, and use it when executing the policy:</span></span>  
  
    ```  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    ```  
  
-   <span data-ttu-id="6288e-273">Puede usar el **SqlTransaction** clase para actualizar la base de datos de la **ProcessPODbNet** directiva de forma transaccional.</span><span class="sxs-lookup"><span data-stu-id="6288e-273">You can use the **SqlTransaction** class to update the database from the **ProcessPODbNet** policy in a transactional manner.</span></span> <span data-ttu-id="6288e-274">El código siguiente muestra cómo iniciar una transacción, pasarla como un parámetro a la **DataConnection** de objetos y confirmar los cambios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6288e-274">The following code shows how to begin a transaction, pass the transaction as a parameter to the **DataConnection** object, and commit the database changes.</span></span> <span data-ttu-id="6288e-275">Para obtener más información, consulte [compatibilidad con transacciones](../core/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="6288e-275">For more information, see [Transaction Support](../core/transaction-support.md).</span></span>  
  
    ```  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    //Begin the transaction  
    SqlTransaction  tn = cn.BeginTransaction();  
    //Pass the transaction object to the DataConnection constructor  
    DataConnection dc = new DataConnection("TestDB", "PO", cn, tn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    dc.Update();  
    //Commit the database transaction  
    tn.Commit();  
    cn.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6288e-276">Vea también</span><span class="sxs-lookup"><span data-stu-id="6288e-276">See Also</span></span>  
 [<span data-ttu-id="6288e-277">Selección de hechos</span><span class="sxs-lookup"><span data-stu-id="6288e-277">Selecting Facts</span></span>](../core/selecting-facts.md)