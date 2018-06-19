---
title: 'Tutorial: Crear un creador de hechos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041c8f73-c72e-43fd-8446-144cecdc95ef
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a1c91417cb58eb53e35c724513d4f955e4e6b6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290308"
---
# <a name="walkthrough-creating-a-fact-creator"></a>Tutorial: Crear un creador de hechos
Este tutorial proporciona procedimientos paso a paso para crear un componente de creador de hechos, **POFactCreator**, que puede utilizar para probar el **ProcessPurchaseOrder** directiva creada en versiones anteriores tutoriales.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe completar la [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de realizar este tutorial.  
  
## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.  
  
|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para crear el componente POFactCreator|Proporciona instrucciones paso a paso para crear un componente de creador de hechos, **POFactCreator**.|  
|Para probar la directiva ProcessPurchaseOrder mediante POFactCreator|Proporciona instrucciones paso a paso para usar la herramienta de Compositor de reglas de negocio para probar el **ProcessPurchaseOrder** directiva mediante el uso de la **POFactCreator** componente.|  
  
### <a name="to-create-the-pofactcreator-component"></a>Para crear el componente POFactCreator  
  
1.  Iniciar **Microsoft Visual Studio**.  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
3.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipos de proyecto**|Haga clic en **Visual C#**.|  
    |**Plantillas**|Haga clic en **biblioteca de clases**.|  
    |**Nombre**|Tipo de **POFactCreatorLib**.|  
    |**Ubicación**|Especifique **C:\BRE-Walkthroughs** como la ubicación.|  
    |**Nombre de solución**|Tipo de **POFactCreatorSol**.|  
    |**Crear directorio para la solución**|Seleccione esta casilla para crear un directorio para los archivos de la solución.|  
  
4.  Haga clic en **Aceptar**. El **POFactCreatorLib** proyecto debe aparecer en el Explorador de soluciones. Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.  
  
5.  En la ventana Propiedades, cambie el nombre del archivo, **Class1.cs**a **POFactCreator.cs**.  
  
6.  En la ventana Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
7.  Haga clic en **examinar**, vaya a **C:\Program programa\Archivos comunes\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.RuleEngine.dll**.  
  
8.  Agregue las líneas siguientes a la parte superior de la **POFactCreator.cs** archivo después de las existentes `using` instrucciones:  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
9. Modificar el **POFactCreator** clase se deriva de la **IFactCreator** interfaz:  
  
    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  
  
10. Haga clic en **IFactCreator**, seleccione **Implementar interfaz**y, a continuación, haga clic en **Implementar interfaz**.  
  
     ![BRE &#45; Tutorial &#45; ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")  
  
11. Agregue un constructor público para el **POFactCreator** clase tal y como se muestra a continuación:  
  
    ```  
    public POFactCreator()  
    {  
    }  
    ```  
  
12. Quite la instrucción única en el **CreateFacts** método.  
  
13. Agregue el código siguiente a la **CreateFacts** método para crear un **TypedXmlDocument** objeto basado en la **SamplePO.xml** documento:  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
14. Agregue el código siguiente para crear una matriz de hechos con el **TypedXmlDocument** objeto como único hecho:  
  
    ```  
    object[] facts = new object[1];  
    facts[0] = txd;   
    ```  
  
15. Devuelve la matriz de hechos de la **CreateFacts** método:  
  
    ```  
    return facts;  
    ```  
  
16. Compruebe que el código completo en el **CreateFacts** método es similar al siguiente:  
  
    ```  
    public object[] CreateFacts(RuleSetInfo ruleSetInfo)  
    {  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
  
    object[] facts = new object[1];  
    facts[0] = txd;  
    return facts;  
    }  
    ```  
  
17. Quite la instrucción única en el **GetFactTypes** método.  
  
18. Agregue el código siguiente a la **GetFactTypes** método para devolver una matriz de tipos que contiene el tipo de la **TypedXmlDocument** clase:  
  
    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  
  
19. Iniciar **símbolo del sistema de Visual Studio**.  
  
20. Cambie el directorio a **C:\BRE-Walkthroughs\POFactCreatorSol**y, a continuación, ejecute el comando siguiente:  
  
     **Sn -k POFactCreator.snk**  
  
21. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, expanda **propiedades**y, a continuación, haga doble clic en **AssemblyInfo.cs**.  
  
22. Agregue la instrucción siguiente a la **AssemblyInfo.cs** archivo al final:  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  
  
23. En la ventana Explorador de soluciones, haga clic en **POFactCreatorLib**y, a continuación, haga clic en **generar**.  
  
24. En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie al directorio **C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**y, a continuación, ejecute el siguiente comando para registrar el **POFactCreator** componente con la GAC (caché global de ensamblados). Si no tiene el símbolo del sistema abierto, siga el paso 19 para abrirlo.  
  
     **Gacutil -i POFactCreatorLib.dll**  
  
### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a>Para probar la directiva ProcessPurchaseOrder mediante POFactCreator  
  
1.  En el **iniciar** menú, elija **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**. Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
2.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en la versión más reciente y, a continuación, haga clic en **probar directiva**.  
  
     ![Compositor de reglas de negocios &#45; TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")  
  
3.  En la parte inferior del cuadro de diálogo, haga clic en **agregar**.  
  
4.  En el **ensamblados .NET** cuadro de diálogo, seleccione **POFactCreatorLib**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **Seleccionar enlace** cuadro de diálogo, haga clic en **POFactCreator** en **POFactCreatorLib, 10.0.0**y, a continuación, haga clic en **Aceptar**.  
  
6.  Haga clic en **prueba**.  
  
7.  Compruebe que la **ApprovalRule** se activa en la ventana de salida.  
  
## <a name="comments"></a>Comentarios  
  
-   Para probar una directiva que utiliza métodos no estáticos de una clase .NET mediante el Compositor de reglas de negocio, es preciso crear un componente de creador de hechos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md)