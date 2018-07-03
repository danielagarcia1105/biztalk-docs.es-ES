---
title: 'Tutorial: Ejecución de la directiva mediante programación | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6398e7af-2ed1-4596-879c-3b7d000b8de2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 666b674e30e548489478af898d5fe88c47d21f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985725"
---
# <a name="walkthrough-executing-the-policy-programmatically"></a>Tutorial: Ejecución de la directiva mediante programación
Este tutorial proporciona procedimientos paso a paso para invocar la directiva que creó en el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial desde una aplicación de consola mediante programación.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe completar el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de realizar este tutorial.  

## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.  

|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para invocar una directiva ProcessPurchaseOrder mediante el método Policy.Execute|Proporciona instrucciones paso a paso para invocar una directiva mediante la **Policy.Execute** método.|  
|Para invocar una directiva ProcessPurchaseOrder mediante el método RuleEngine.Execute|Proporciona instrucciones paso a paso para invocar una directiva mediante la **RuleEngine.Execute** método.|  

### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-policyexecute-method"></a>Para invocar una directiva ProcessPurchaseOrder mediante el método Policy.Execute  

1. Iniciar **Microsoft Visual Studio**.  

2. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  

3. En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  


   |             Use              |                             Para                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **Tipos de proyecto**         |                        Haga clic en **Visual C#**.                         |
   |           **Templates** (Plantillas [C++])           |                   Haga clic en **aplicación de consola**.                    |
   |             **Nombre**              |                       Tipo **ConsoleClient**.                       |
   |           **Ubicación**            |     Especifique una carpeta en la que desea guardar los archivos del proyecto.      |
   |         **Nombre de solución**         |                     Tipo **ConsoleClientSol**.                      |
   | **Crear directorio para la solución** | Seleccione esta casilla para crear un directorio para los archivos de la solución. |


4. Haga clic en **Aceptar**. El **ConsoleClient** proyecto debe aparecer en el Explorador de soluciones. Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.  

5. En el Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  

6. Haga clic en **examinar**, vaya a la **\Program Files\Common Files\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.RuleEngine.dll**.  

7. Agregue las líneas siguientes a la parte superior de la **Program.cs** archivo después de la existente `using` instrucciones:  

   ```  
   //To use the XmlDocument class  
   using System.Xml;  
   //To use the TypedXmlDocument and Policy classes  
   using Microsoft.RuleEngine;   
   ```  

8. Agregue el código siguiente a la **Main** función para crear un **TypedXmlDocument** objeto basado en el documento XML:  

   ```  
   XmlDocument doc = new XmlDocument();  
   //Loading the XML from SamplePO.xml file.  
   //Change the directory as needed  
   doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
   TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
   ```  

9. Agregue el código siguiente a la **Main** función para ejecutar la directiva:  

    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  

10. Imprimir la salida XML para confirmar que el valor de la **estado** campo se establece en **aprobado**. Tenga en cuenta que a diferencia del compositor de reglas de negocio, invocar el **Policy.Execute** método no cambia el documento original.  

    ```  
    //Print the output document  
    Console.WriteLine(txd.Document.OuterXml);   
    ```  

11. En el **compilar** menú, haga clic en **generar ConsoleClient**.  

12. Presione CTRL+F5 para ejecutar la aplicación. Confirme que el valor de la **estado** campo se establece en **aprobado**.  

### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-ruleengineexecute-method"></a>Para invocar una directiva ProcessPurchaseOrder mediante el método RuleEngine.Execute  

1.  En el Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  

2.  Haga clic en **examinar**, vaya a **\Program Files\Common Files\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.BizTalk.RuleEngineExtensions.dll**.  

3.  Comente las líneas siguientes en el **Program.cs** archivo:  

    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  

4.  Agregue el código siguiente después del código marcado como comentario para obtener acceso a la base de datos del motor de reglas:  

    ```  
    //Get access to the SQL rule store   
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    ```  

5.  Agregue el código siguiente para obtener acceso a **RuleSetInfoCollection** de la directiva ProcessPurchaseOrder:  

    ```  
    //Get access to RuleSetInfoCollection for the   
    //ProcessPurchaseOrder policy  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    ```  

6.  Agregue el código siguiente para crear un **RuleSet** objeto según la información del conjunto de reglas de la directiva ProcessPurchaseOrder:  

    ```  
    //Create a RuleSet object based on the rule set information   
    //for the ProcessPurchaseOrder policy  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    ```  

7.  Agregue el código siguiente para crear el **RuleEngine** objeto:  

    ```  
    //Create the RuleEngine object  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    ```  

8.  Agregue el código siguiente para imponer el **TypedXmlDocument** objeto en la memoria de trabajo del motor de reglas:  

    ```  
    //Assert the TypedXmlDocument object into working memory  
    //of the rule engine  
    engine.Assert(txd);  
    ```  

9. Ahora agregue el código para ejecutar la directiva mediante el **RuleEngine.Execute** método:  

    ```  
    //Execute the policy by invoking RuleEngine.Execute method  
    engine.Execute();  
    ```  

10. Asegúrese de que el **Console.WriteLine** instrucción es la última instrucción del **Main** función.  

11. En el **compilar** menú, haga clic en **generar ConsoleClient**.  

12. Presione CTRL+F5 para ejecutar la aplicación. Confirme que el valor de la **estado** campo se establece en **aprobado**.  

## <a name="comments"></a>Comentarios  

-   Completar código para el **Main** función para ejecutar la directiva ProcessPurchaseOrder mediante el **Policy.Execute** método es como sigue:  

    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    policy.Execute(txd);  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  

-   Completar código para ejecutar la directiva ProcessPurchaseOrder mediante el uso de la **RuleEngine.Execute** método es como sigue:  

    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    engine.Assert(txd);  
    engine.Execute();  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  

-   Es posible que desee agregar un **Console.ReadLine ()** instrucción al final de la **Main** función para que la aplicación espera para que pueda finalizar la aplicación.  

-   En este tutorial, el cliente envía sólo un hecho a la directiva ProcessPurchaseOrder. Si el cliente necesita enviar más de un hecho a la directiva, debe crear una matriz de hechos y utilizar sobrecargado **Execute** método que toma una matriz como parámetro. El siguiente código de ejemplo muestra cómo hacerlo:  

    ```  
    Policy policy = new Policy("PolicyName");  
    object[] facts = new object[2];  
    facts[0] = txd;  
    facts[1] = new MyClass();  
    policy.Execute(facts);  
    policy.Dispose();  
    ```  

-   El primer parámetro para el **TypedXmlDocument** constructor en el código es el nombre del tipo utilizado para crear la directiva.  

-   El **Policy.Execute** método es básicamente un contenedor en torno a la **RuleEngine.Execute** método. Por lo tanto, uso el **Policy.Execute** método es la forma más sencilla de invocar una directiva, tal como hemos visto en este tutorial.  

-   Para obtener más control sobre la ejecución de la directiva, es posible que desea utilizar el **RuleEngine.Execute** método en lugar de usar **Policy.Execute**. Por ejemplo, puede detener el motor temporalmente mediante la **Halt** función y, a continuación, reanudar con la **Execute** función. Para obtener más información, consulte [Halt](../core/halt.md).  

## <a name="see-also"></a>Vea también  
 [Cómo ejecutar las directivas](../core/how-to-execute-policies.md)