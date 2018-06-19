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
# <a name="walkthrough-using-database-and-net-facts"></a>Tutorial: Usar hechos .NET y base de datos
Este tutorial proporciona procedimientos descritos paso a paso para usar el Compositor de reglas de negocio con el fin de crear una directiva que utilice hechos de base de datos y .NET.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe establecer el valor de la **StaticSupport** clave del registro en 1 o 2 antes de llevar a cabo el tutorial. De este modo, permitirá que la directiva invoque los métodos estáticos de una clase .NET sin necesidad de que el cliente imponga una instancia de la clase. Para obtener más información, consulte [invocar miembros estáticos de una clase](../core/invoking-static-members-of-a-class.md).  
  
## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene cinco procedimientos, tal y como se muestra en la tabla siguiente.  
  
|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para crear la base de datos TestDB y la tabla PO|Proporciona instrucciones paso a paso para crear la **TestDB** base de datos y la **PO** tabla.|  
|Para crear el componente POUtility|Proporciona instrucciones paso a paso para crear la **POUtility** componente.|  
|Para crear la directiva empresarial ProcessPurchaseOrderDbNet|Proporciona instrucciones paso a paso para crear la **ProcessPurchaseOrderDbNet** directiva.|  
|Para probar la directiva ProcessPurchaseOrderDbNet mediante el Compositor de reglas de negocio|Proporciona instrucciones paso a paso para utilizar el Compositor de reglas de negocio para probar el **ProcessPurchaseOrderDbNet** directiva.|  
|Para probar la directiva ProcessPurchaseOrderDbNet mediante el método Policy.Execute|Proporciona instrucciones paso a paso para probar el **ProcessPurchaseOrderDbNet** directiva mediante el uso de la **Policy.Execute** método.|  
  
### <a name="to-create-the-testdb-database-and-the-po-table"></a>Para crear la base de datos TestDB y la tabla PO  
  
1.  Abra **SQL Server Management Studio**.  
  
2.  Compruebe el nombre del servidor y la autenticación y, a continuación, haga clic en **conectar**.  
  
3.  En la ventana Explorador de objetos de la izquierda, haga clic en el nombre del equipo y, a continuación, haga clic en **nueva consulta**.  
  
4.  Copie las siguientes instrucciones SQL en la ventana de consulta.  
  
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
  
5.  Presione F5 para ejecutar la consulta SQL.  
  
6.  En la ventana Explorador de objetos, expanda el nombre del equipo, **bases de datos**y, a continuación, compruebe que **TestDB** existe.  
  
7.  Expanda **TestDB**, expanda **tablas**y, a continuación, compruebe que **dbo. Pedido de compra** existe.  
  
8.  Haga clic en **dbo. Pedido de compra**y, a continuación, haga clic en **Abrir tabla** para comprobar la existen de los siguientes datos en la tabla.  
  
    |PONumber|Cantidad|Estado|  
    |--------------|--------------|------------|  
    |PO1|400|NULL|  
    |PO2|700|NULL|  
  
### <a name="to-create-the-poutility-component"></a>Para crear el componente POUtility  
  
1.  Iniciar **Microsoft Visual Studio**.  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipos de proyecto**|Haga clic en **Visual C#**.|  
    |**Plantillas**|Haga clic en **biblioteca de clases**.|  
    |**Nombre**|Tipo de **POUtilityLib**.|  
    |**Ubicación**|Especifique **C:\BRE-Walkthroughs** como la ubicación.|  
    |**Nombre de solución**|Tipo de **POUtilitySol**.|  
    |**Crear directorio para la solución**|Seleccione esta casilla para crear un directorio para los archivos de la solución.|  
  
4.  Haga clic en **Aceptar**. El **POUtilityLib** proyecto debe aparecer en el Explorador de soluciones. Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.  
  
5.  En la ventana Propiedades, cambie el nombre del archivo, **Class1.cs**a **POUtility.cs**.  
  
6.  Agregue un constructor público a la clase como se muestra en el código siguiente:  
  
    ```  
    public POUtility()  
    {  
    }  
    ```  
  
7.  Agregar un método estático denominado **GetMaxAllowed** a la **POUtility** clase tal como se muestra en el código siguiente:  
  
    ```  
    public static int GetMaxAllowed()  
    {  
    return 500;  
    }   
    ```  
  
8.  Iniciar **símbolo del sistema de Visual Studio**.  
  
9. Cambie el directorio a **C:\BRE-Walkthroughs\POUtilitySol**y, a continuación, ejecute el comando siguiente:  
  
     **Sn -k POUtility.snk**  
  
10. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, expanda **propiedades**y, a continuación, haga doble clic en **AssemblyInfo.cs**.  
  
11. Agregue la instrucción siguiente a la **AssemblyInfo.cs** archivo al final:  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POUtilitySol\POUtility.snk")]  
    ```  
  
12. En la ventana Explorador de soluciones, haga clic en **POUtilityLib**y, a continuación, haga clic en **generar**.  
  
13. En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie al directorio **C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**y, a continuación, ejecute el siguiente comando para registrar el componente POUtility en la GAC (global caché de ensamblados). Si el símbolo del sistema no está abierto, siga el paso 8 para abrirlo.  
  
     **Gacutil -i POUtilityLib.dll**  
  
### <a name="to-create-the-processpurchaseorderdbnet-business-policy"></a>Para crear la directiva empresarial ProcessPurchaseOrderDbNet  
  
1.  En el **iniciar** menú Abrir **Compositor de reglas de negocios**. Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de hechos, haga clic en **bases de datos**.  
  
3.  Haga clic en **servidores**y, a continuación, haga clic en **examinar**.  
  
4.  Compruebe la información de autenticación de servidor y y, a continuación, haga clic en **Aceptar**.  
  
5.  Expanda **TestDB**y, a continuación, expanda **pedido**.  
  
6.  En la ventana Explorador de hechos, haga clic en **clases .NET**.  
  
7.  Haga clic en **. NETAssemblies**y, a continuación, haga clic en **examinar**.  
  
8.  Seleccione **POUtility**y, a continuación, haga clic en **Aceptar**.  
  
9. Expanda **Class1**.  
  
10. En la ventana Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.  
  
11. Cambiar el nombre de la directiva de **Policy1** a **ProcessPurchaseOrderDbNet** y, a continuación, presione ENTRAR. También puede cambiar el nombre de la directiva en la ventana Propiedades.  
  
12. Haga clic en **versión 1.0**y, a continuación, haga clic en **AddNewRule**.  
  
13. Cambiar el nombre de la regla de **Rule1** a **ApprovalRule** y, a continuación, presione ENTRAR. También puede cambiar el nombre de la regla en la ventana Propiedades.  
  
14. En el panel si (superior) a la derecha, haga clic en **condiciones**, haga clic en **predicados**y, a continuación, haga clic en **Menorqueigual**.  
  
15. En la ventana Explorador de hechos, haga clic en **bases de datos**.  
  
16. Arrastre el **cantidad** nodo desde la ventana Explorador de hechos hasta **argumento1** en el panel si.  
  
17. En la ventana Explorador de hechos, haga clic en **clases .NET**.  
  
18. Arrastre **GetMaxAllowed** nodo desde la ventana Explorador de hechos hasta **argumento2** en el panel si.  
  
19. En la ventana Explorador de hechos, haga clic en **bases de datos**.  
  
20. Arrastre el **estado** nodo desde la ventana Explorador de hechos hasta el panel, a continuación, en la parte inferior derecha del compositor de reglas de negocios.  
  
21. En el panel, a continuación, haga clic en  **\<escriba un valor\>**  y, a continuación, escriba **aprobado**.  
  
22. En la ventana Explorador de hechos, haga clic en **versión 1.0** en **ProcessPurchaseOrderDbNet**y, a continuación, haga clic en **AddNewRule**.  
  
23. Cambiar el nombre de la regla de **Rule1** a **DeniedRule** y, a continuación, presione ENTRAR. También puede cambiar el nombre de la regla en la ventana Propiedades.  
  
24. En el panel si (superior) a la derecha, haga clic en **condiciones**, haga clic en **predicados**y, a continuación, haga clic en **GreaterThan**.  
  
25. En la ventana Explorador de hechos, haga clic en **bases de datos**.  
  
26. Arrastre el **cantidad** nodo desde la ventana Explorador de hechos hasta **argumento1** en el panel si.  
  
27. En la ventana Explorador de hechos, haga clic en **clases .NET**.  
  
28. Arrastre el **GetMaxAllowed** nodo desde la ventana Explorador de hechos hasta **argumento2** en el panel si.  
  
29. En la ventana Explorador de hechos, haga clic en **bases de datos**.  
  
30. Arrastre el **estado** nodo desde la ventana Explorador de hechos hasta el panel, a continuación, en la parte inferior derecha del compositor de reglas de negocios.  
  
31. En el panel, a continuación, haga clic en  **\<escriba un valor\>**  y, a continuación, escriba **denegado**.  
  
32. En la ventana Explorador de directivas, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **guardar**.  
  
### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-business-rule-composer"></a>Para probar la directiva ProcessPurchaseOrderDbNet mediante el Compositor de reglas de negocio  
  
1.  En el **iniciar** menú Abrir **Compositor de reglas de negocios**. Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.  
  
2.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrderDbNet**, haga clic en **versión 1.0**y, a continuación, haga clic en **probar directiva** .  
  
3.  Haga clic en **TestDB: PO (conexión de datos)** y, a continuación, haga clic en **Agregar instancia**.  
  
4.  En el **conectar con SQL Server** cuadro de diálogo, compruebe la información de nombre y la autenticación de servidor y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **Seleccionar enlace** cuadro de diálogo, expanda **TestDB**, haga clic en **pedido**y, a continuación, haga clic en **Aceptar**.  
  
6.  Haga clic en **prueba**.  
  
7.  En la ventana resultados, compruebe que tanto el **ApprovalRule** y **DeniedRule** se activan.  
  
8.  En SQL Server Management Studio, haga clic en **dbo. Pedido de compra**y, a continuación, haga clic en **Abrir tabla**.  
  
9. Compruebe que el valor de la **estado** campo está establecido en **aprobado** para el primer registro.  
  
10. Compruebe que el valor de la **estado** campo está establecido en **denegado** para el segundo registro.  
  
    > [!NOTE]
    >  Si aún aparece el valor de la **estado** campo como NULL, haga clic en la lista que contiene los datos y, a continuación, haga clic en **ejecutar SQL**, que actualiza la vista.  
  
11. Mantenga abierta la aplicación SQL Server Management Studio.  
  
### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-policyexecute-method"></a>Para probar la directiva ProcessPurchaseOrderDbNet mediante el método Policy.Execute  
  
1.  Iniciar **Microsoft Visual Studio**.  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipos de proyecto**|Haga clic en **Visual C#**.|  
    |**Plantillas**|Haga clic en **aplicación de consola**.|  
    |**Nombre**|Tipo de **TestProcessPODbNet**.|  
    |**Ubicación**|Especifique **C:\BRE-Walkthroughs** como la ubicación.|  
    |**Nombre de solución**|Tipo de **TestProcessPODbNetSol**.|  
    |**Crear directorio para la solución**|Seleccione esta casilla para crear un directorio para los archivos de la solución.|  
  
4.  Haga clic en **Aceptar**. El **TestProcessPODbNet** proyecto debe aparecer en el Explorador de soluciones. Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.  
  
5.  En el Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
6.  Haga clic en **examinar**, vaya a **\Program Files\Common Files\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.RuleEngine.dll**.  
  
7.  Agregue el código siguiente a la parte superior de la **Program.cs** archivo después de las existentes `using` instrucciones:  
  
    ```  
    //To use the SQLConnection class  
    using System.Data.SqlClient;  
  
    //To use the Policy and DataConnection classes  
    using Microsoft.RuleEngine;  
    ```  
  
8.  Agregue el código siguiente a la **Main** función para crear y abrir un **SQLConnection** objeto:  
  
    ```  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    ```  
  
9. Agregue el código siguiente a la **Main** función al final para crear una **DataConnection** objeto basado en la **SQLConnection** objeto creado en el paso anterior:  
  
    ```  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    ```  
  
10. Agregue el código siguiente a la **Main** función al final para crear una **directiva** de objetos y ejecutar la directiva:  
  
    ```  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    ```  
  
11. Agregue el código siguiente a la **Main** función al final para actualizar la base de datos:  
  
    ```  
    dc.Update();  
    ```  
  
12. Agregue el código siguiente a la **Main** función al final para cerrar la conexión con la base de datos:  
  
    ```  
    cn.Close();  
    ```  
  
13. Agregar un bloque try-catch para detectar las excepciones generadas en el **Main** método.  
  
14. Compruebe que el código completo de la **Main** función es como se muestra en el código siguiente:  
  
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
  
15. En el **generar** menú, haga clic en **generar TestProcessPODbNet**.  
  
16. En el Compositor de reglas de negocio, expanda **directivas**, expanda **ProcessPurchaseOrderDbNet**, haga clic en **versión 1.0**y, a continuación, haga clic en **publicar**.  
  
17. Haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  
  
18. En SQL Server Management Studio, establezca el valor de la **estado** campo **NULL** para los registros de pedido de compra.  
  
19. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], presione CTRL + F5 para ejecutar el **TestProcessPODbNet** aplicación.  
  
20. Presione cualquier tecla para cerrar la ventana de símbolo del sistema.  
  
21. En SQL Server Management Studio, haga clic en la tabla con registros de pedido de compra y, a continuación, haga clic en **ejecutar SQL**.  
  
22. Compruebe que el valor de la **estado** campo está establecido en **aprobado** para el primer registro.  
  
23. Compruebe que el valor de la **estado** campo está establecido en **denegado** para el segundo registro.  
  
## <a name="comments"></a>Comentarios  
  
-   Si una directiva utiliza los métodos no estáticos de una clase .NET, deberá usar un componente de creador de hechos que imponga una instancia de la clase .NET para probar la directiva mediante el Compositor de reglas de negocio.  
  
-   Es muy importante recordar que el Compositor de reglas de negocios crea una instancia de la **DataConnection** de objeto y la impone en la memoria de trabajo del motor de reglas automáticamente para usted. Sin embargo, cuando se invoca la directiva desde una aplicación cliente (BizTalk o no sean de BizTalk), el **DataConnection** objeto no se crea automáticamente para usted. El cliente debe crear una **DataConnection** objeto y pasarlo como parámetro o hecho al motor de reglas para ejecutar la directiva.  
  
-   Puede usar el **DebugTrackingInterceptor** clase para realizar el seguimiento de los detalles de ejecución de directiva. El código de ejemplo siguiente muestra cómo crear una instancia de la **DebugTrackingInterceptor** clase y utilizarla al ejecutar la directiva:  
  
    ```  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    ```  
  
-   Puede usar el **SqlTransaction** clase para actualizar la base de datos de la **ProcessPODbNet** directiva de forma transaccional. El código siguiente muestra cómo iniciar una transacción, pasarla como un parámetro a la **DataConnection** de objetos y confirmar los cambios de la base de datos. Para obtener más información, consulte [compatibilidad con transacciones](../core/transaction-support.md).  
  
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
  
## <a name="see-also"></a>Vea también  
 [Selección de hechos](../core/selecting-facts.md)