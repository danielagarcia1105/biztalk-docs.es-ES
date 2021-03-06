---
title: 'Tutorial: Probar la directiva | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53ed915d-0f3a-48ea-bfd5-a1f89b9b689c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ddf9dcc459fbee7494a913846f1c9d2a7137579
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001773"
---
# <a name="walkthrough-testing-the-policy"></a>Tutorial: Probar la directiva
Este tutorial proporciona procedimientos paso a paso para probar la directiva creada en el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe completar el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de realizar este tutorial.  

## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.  

|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para crear los archivos de prueba|Proporciona instrucciones paso a paso para crear XML de ejemplo dos archivos, uno con el valor del campo Quantity, como 400 (\<= 500) y el otro con el valor del campo Quantity establecido en 700 (> 500).|  
|Para probar la directiva ProcessPurchaseOrder|Proporciona instrucciones descritas paso a paso para probar la directiva mediante el Compositor de reglas de negocio.|  

### <a name="to-create-the-test-files"></a>Para crear los archivos de prueba  

1.  En el **iniciar** menú Abrir **el Bloc de notas**.  

2.  Copie el texto XML siguiente en el Bloc de notas:  

    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>400</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>    
    ```  

3.  En el **archivo** menú, haga clic en **guardar Archivodetexto1.txt como**.  

4.  Cambie el valor de **Guardar como tipo** desde **documentos de texto (\*.txt)** a **todos los archivos**.  

5.  Cambie el directorio a **C:\BRE-Walkthroughs**.  

6.  Tipo **SamplePO.xml** para **nombre de archivo**y, a continuación, haga clic en **guardar**.  

7.  En el menú **Archivo** , haga clic en **Nuevo**.  

8.  Copie el texto XML siguiente en el Bloc de notas:  

    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>700</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>   
    ```  

9. En el **archivo** menú, haga clic en **guardar Archivodetexto1.txt como**.  

10. Cambie el valor de **Guardar como tipo** desde **documentos de texto (\*.txt)** a **todos los archivos**.  

11. Cambie el directorio a **C:\BRE-Walkthroughs**.  

12. Tipo **SamplePO2.xml** para **nombre de archivo**y, a continuación, haga clic en **guardar**.  

13. Cierre el Bloc de notas.  

### <a name="to-test-the-processpurchaseorder-policy"></a>Para probar la directiva ProcessPurchaseOrder  

1.  En el **iniciar** menú Abrir **compositor**. Si tiene compositor ya abierto, presione F5 para actualizarlo.  

    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  

2.  En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **ladirectivadeprueba**.  

3.  En el **XMLDocuments** nodo, seleccione **RuleTest.PO**y, a continuación, haga clic en **Agregar instancia**.  

     ![Compositor de reglas de negocio&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")  

4.  Seleccione el **SamplePO.xml** archivo que creó anteriormente y, a continuación, haga clic en **abierto**.  

5.  Haga clic en **prueba**.  

6.  Revise el resultado en la ventana Salida. Para obtener una explicación sobre la salida, vea la sección "Análisis de la salida de la primera prueba (samplepo.xml)".  

7.  Abra **SamplePO.xml** en el Bloc de notas y observe que el valor de la **estado** campo se establece en **aprobado**.  

8.  Haga clic en **versión 1.0**y, a continuación, haga clic en **probar directiva**.  

9. Seleccione **SamplePO.xml**, haga clic en **quitar instancia**y, a continuación, haga clic en **Agregar instancia**.  

10. Seleccione el **SamplePO2.xml** archivo que creó anteriormente y, a continuación, haga clic en **abierto**.  

11. Haga clic en **prueba**. Para obtener una explicación sobre la salida, vea la sección "Análisis de la salida de la segunda prueba (samplepo2.xml)".  

12. Abra el **SamplePO2.xml** de archivos en el Bloc de notas y observe que el valor de la **estado** campo sigue siendo **XYZ**.  

## <a name="analysis-of-the-output-from-the-first-test-samplepoxml"></a>Análisis del resultado de la primera prueba (samplepo.xml)  

> [!NOTE]
>  El texto de salida aparece en negrita y la explicación aparece a continuación de éste.  

 **SEGUIMIENTO de motor de reglas para conjunto de reglas: ProcessPurchaseOrder 31/8/2006 1:33:10 P.M.**  

 El seguimiento de motor de reglas para la ejecución de la directiva de **ProcessPurchaseOrder** se inició a 31/8/2006 1:33:10 PM.  

 **ACTIVIDAD DE DATOS 31/8/2006 1:33:10 P.M.**  

 **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Operación: Assert**  

 **Tipo de objeto: TypedXmlDocument:PurchaseOrder**  

 **Identificador de instancia de objeto: 14626574**  

 Al hacer clic en **prueba**, sucede lo siguiente:  

1. El compositor crea un **RuleEngine.Policy** objeto, que a su vez crea una nueva instancia de motor de reglas o adquiere una instancia de motor de reglas de la caché del motor de reglas.  

2. El compositor crea un **TypedXmlDocument** objeto basado en el archivo SamplePO.xml.  

3. El Compositor de reglas de negocio invoca el **Policy.Execute** método con el **TypedXmlDocument** objeto como parámetro.  

4. El **Policy.Execute** método impone (agrega) el **TypedXmlDocument** objeto como un hecho en la memoria de trabajo del motor de reglas.  

5. El motor de reglas utiliza el **TypedXmlDocument** objeto como un hecho y ejecuta el **ProcessPurchaseOrder** directiva.  

   **ACTIVIDAD DE DATOS 31/8/2006 1:33:10 P.M.**  

   **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

   **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

   **Operación: Assert**  

   **Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder**  

   **Identificador de instancia de objeto: 64530307**  

   **ACTIVIDAD DE DATOS 31/8/2006 1:33:10 P.M.**  

   **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

   **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

   **Operación: Assert**  

   **Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder/Item**  

   **Identificador de instancia de objeto: 43901854**  

6. El motor de reglas determina qué elemento secundario **TypedXmlDocument** objetos se deben crear según los selectores XPath que estén definidos en las reglas. Cuando genera reglas en el Compositor de reglas de negocio, el valor del selector XPath predeterminado es el nodo por encima del nodo seleccionado en el **esquemas XML** ficha en el Explorador de hechos. El valor predeterminado del campo XPath es el nodo seleccionado en sí, con respecto al nodo primario. Sin embargo, si el nodo seleccionado tiene elementos secundarios, sólo se crea un enlace del selector XPath para señalar al nodo seleccionado y no se crea ningún enlace del campo XPath.  

7. Los valores de enlace para los campos utilizados en la siguiente tabla muestra el Selector XPath y XPath Field el **ProcessPurchaseOrder** directiva. (La directiva sólo tiene una regla: ApprovalRule.)  

| Nombre de campo |                                                             Selector XPath                                                              |                    Campo XPath                     | Selector XPath (forma simplificada) | Campo XPath<br /><br /> (forma simplificada) |
|------------|-----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|----------------------------------|-------------------------------------------|
|  Cantidad  | /\*[local-name () = 'PurchaseOrder' y espacio ='http://EAISolution.PurchaseOrder'] /\*[local-name () = 'Item' y espacio =''] | \*[local-name () = 'Cantidad' y espacio =''] |       /PurchaseOrder/Item        |                 Cantidad                  |
|   Estado   |                       /\*[local-name () = 'PurchaseOrder' y espacio ='<http://EAISolution.PurchaseOrder>']                        |  \*[local-name () = 'Status' y espacio ='']  |          /PurchaseOrder          |                  Estado                   |

<!---Loc Comment: Please, verify strucutre in line 183 and 184--->

#### <a name="to-view-the-xpath-selector-and-xpath-field-bindings-for-the-quantity-and-status-fields"></a>Para ver los enlaces de Selector Xpath y Campo Xpath de los campos Quantity y Status  

1. En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**y, a continuación, expanda **versión 1.0**.  

2. Haga clic en **ApprovalRule**.  

3. En el panel si a la derecha, haga clic en **PO: / PurchaseOrder/Item/Quantity**.  

4. Compruebe que ve el valor mostrado en la tabla anterior para el **Selector XPath** y **XPath Field** enlaces en la ventana Propiedades.  

5. Repita los pasos 3 y 4 para el **PO: / PurchaseOrder/Status** campo.  

   El motor de reglas crea un elemento secundario **TypedXmlDocument** objeto respecto al original **TypedXmlDocument** enviado para cada selector XPath. Dado que hay dos selectores XPath distintos utilizados en la directiva (**/PurchaseOrder/Item** para el **cantidad** campo y **/PurchaseOrder** para el  **Estado** campo), el motor de reglas crea dos secundarios **TypedXmlDocument** objetos y los impone en la memoria de trabajo del motor de reglas.  

> [!NOTE]
>  Para ver el seguimiento de salida nuevo, haga clic en **versión 1.0** en la ventana del explorador de directivas.  

 **PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 31/8/2006 1:33:10 P.M.**  

 **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Expresión de prueba: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  

 **Deja el valor del operando: 400**  

 **Valor del operando a la derecha: 500**  

 **Resultado de la prueba: True**  

 **ACTUALIZACIÓN DE AGENDA 31/8/2006 1:33:10 P.M.**  

 **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Operación: agregar**  

 **Nombre de regla: ApprovalRule**  

 **Criterios de resolución de conflictos: 0**  

 Para ejecutar las directivas, el motor de reglas usa el algoritmo de tres fases Evaluación de condición – Resolución de conflictos – Ejecución de acciones. En la fase Evaluación de la condición, el motor de reglas evalúa las condiciones de todas las reglas de la directiva y agrega las reglas cuyas condiciones se evalúan como `true` para la agenda. En este sencillo ejemplo, la **ProcessPurchaseOrder** directiva sólo tiene una regla, **ApprovalRule**. Por lo tanto, el motor de reglas evalúa la condición, **cantidad < = 500**, en el **ApprovalRule** con el valor de la **cantidad** campo en el documento XML enviado, que es **400**. La salida anterior muestra los valores del operando izquierdo, el operando derecho y el resultado de la prueba.  

 En la segunda fase, Criterios de resolución de conflictos, las reglas cuyas condiciones se evalúan como `true` se agregan a la agenda en orden según su prioridad. En este escenario, el motor de reglas agrega la **ApprovalRule** a la agenda porque la condición para la **ApprovalRule** se evaluó como `true`. Los criterios de resolución de conflictos que se muestra en la salida anterior es sólo la prioridad en la regla (**ApprovalRule**). Si hace clic en el **ApprovalRule** nodo en la ventana del explorador de directivas, puede ver el valor de la **prioridad** propiedad en la regla en la ventana Propiedades como **0**, que es el valor predeterminado de una regla. Si hay varias reglas en una directiva y desea asegurarse de que las acciones de una regla se ejecutan después de las acciones de otra, debe establecer la prioridad correctamente. Cuanto mayor es el número, mayor es la prioridad.  

 **REGLA ACTIVADA 31/8/2006 1:33:10 P.M.**  

 **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Nombre de regla: ApprovalRule**  

 **Criterios de resolución de conflictos: 0**  

 En la última fase, Ejecución de acción, el motor de reglas inicia la ejecución de las acciones de la regla. Hay una acción en el **ApprovalRule**, que establece el valor de la **estado** campo en el documento XML enviado a **aprobado**.  

 **ACTIVIDAD DE DATOS 31/8/2006 1:33:10 P.M.**  

 **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Operación: retirar**  

 **Tipo de objeto: TypedXmlDocument:PurchaseOrder**  

 **Identificador de instancia de objeto: 14626574**  

 **ACTIVIDAD DE DATOS 31/8/2006 1:33:10 P.M.**  

 **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Operación: retirar**  

 **Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder/Item**  

 **Identificador de instancia de objeto: 43901854**  

 **ACTIVIDAD DE DATOS 31/8/2006 1:33:10 P.M.**  

 **Identificador de instancia del motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Operación: retirar**  

 **Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder**  

 **Identificador de instancia de objeto:** 64530307  

 Todos los hechos enviados (**PurchaseOrder**) a la regla engine y los hechos secundarios creados por el motor de reglas según los selectores XPath (**\PurchaseOrder** y **\PurchaseOrder\Item**) se retiran (quitan) de la memoria de trabajo del motor de reglas.  

## <a name="analysis-of-the-output-from-the-second-test-samplepo2xml"></a>Análisis del resultado de la segunda prueba (samplepo2.xml)  
 **PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 5/9/2006 5:24:42 P.M.**  

 **Identificador de instancia del motor de reglas: b749d2fd-a883-4c2f-9974-5cf688010622**  

 **Nombre del conjunto de reglas: ProcessPurchaseOrder**  

 **Expresión de prueba: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  

 **Deja el valor del operando: 700**  

 **Valor del operando a la derecha: 500**  

 **Resultado de la prueba:** False  

 El motor de reglas evalúa la condición (**cantidad < = 500**) en el **ApprovalRule** con el único **elemento** objeto. Puede ver que el valor del operando izquierdo es el valor de la **cantidad** elemento en el documento XML, **700**. El resultado de prueba es `false` porque **700 < = 500**, por lo que la regla no se agrega a la agenda del motor de reglas. No hay ninguna regla en la agenda. Por lo tanto, hay ninguna acción para ejecutar y el valor de la **estado** campo permanece **XYZ**.  

## <a name="comments"></a>Comentarios  

-   Se recomienda probar las directivas antes de utilizarlas desde aplicaciones cliente, como aplicaciones de BizTalk.  

-   Cuando se prueba una directiva que utiliza hechos de base de datos con el **DataConnection** enlace en el Compositor de reglas de negocio, un **DataConnection** objeto se crea automáticamente para usted. Sin embargo, cuando se llama a la misma directiva desde una orquestación mediante el uso de la **reglas de llamada** dar forma, no **DataConnection** objeto se pasa automáticamente a la directiva. Debe crear un **DataConnection** objeto en la orquestación y pasarlo como parámetro o crear un componente recuperador de datos que imponga el **DataConnection** de objetos y configurar la directiva para usar el componente recuperador de datos.  

-   Para probar una directiva que utiliza un hecho. NET, debe crear un componente de creador de hechos y especificarlo en el **Seleccionar hechos** cuadro de diálogo. Para obtener más información acerca de cómo crear creadores de hechos, vea [cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md). Puede hacer lo mismo cuando la directiva utiliza hechos de base de datos (**TypedDataConnection** o **TypedDataTable** o **TypedDataRow**) o hechos XML ( **TypedXmlDocument**).  

## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha realizado este tutorial, realice el [Tutorial: invocar la directiva desde una orquestación](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) tutorial, lo que le ofrece instrucciones paso a paso para invocar el **ProcessPurchaseOrder**  directiva desde una orquestación.  

## <a name="see-also"></a>Vea también  
 [Resultado de seguimiento de pruebas de directivas](../core/policy-test-trace-output.md)   
 [Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md)   
 [Agenda y prioridad](../core/agenda-and-priority.md)
