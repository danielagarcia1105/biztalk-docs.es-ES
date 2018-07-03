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
# <a name="walkthrough-creating-a-simple-business-policy"></a>Tutorial: Crear una directiva empresarial sencilla
Este tutorial proporciona procedimientos paso a paso para que usar el Compositor de reglas de negocio para crear una directiva empresarial sencilla denominada **ProcessPurchaseOrder** que contiene una regla denominada **ApprovedRule**. El **ApprovedRule** regla espera que el usuario envíe un documento XML como un hecho y establece el valor de la **estado** campo en el documento a **aprobado** si el valor de la  **Cantidad** campo es menor o igual que **500**.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conocer los fundamentos del Marco de trabajo de reglas de negocios para realizar este tutorial. Si está familiarizado con el marco de trabajo de reglas de negocios, se recomienda que lea la introducción a la arquitectura del marco de trabajo de reglas de negocios en [motor de reglas de negocios](../core/business-rules-engine.md) antes de realizar este tutorial.  
  
## <a name="overview-of-this-walkthrough"></a>Información general de este tutorial  
 Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.  
  
|Título del procedimiento|Descripción del procedimiento|  
|---------------------|---------------------------|  
|Para crear el archivo de esquema PO|Proporciona instrucciones paso a paso para crear el esquema del documento que el **ProcessPurchaseOrder** directiva utiliza.|  
|Para crear la directiva ProcessPurchaseOrder|Proporciona instrucciones paso a paso para crear el **ProcessPurchaseOrder** directiva mediante el uso del compositor de reglas de negocios.|  
  
### <a name="to-create-the-po-schema-file"></a>Para crear el archivo de esquema PO  
  
1.  En el **iniciar** menú Abrir **el Bloc de notas**.  
  
2.  En el menú **Archivo** , elija **Nuevo**y haga clic en **Archivo**.  
  
3.  Copie el texto XML siguiente en el editor:  
  
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
  
4.  En el **archivo** menú, haga clic en **guardar Archivodetexto1.txt como**.  
  
5.  Cambie el valor de **Guardar como tipo** desde **documentos de texto (\*.txt)** a **todos los archivos**.  
  
6.  Tipo **PO.xsd** en el **nombre de archivo** texto, cambie el directorio a **C:\BRE-Walkthroughs**, cambie el valor de **codificación** a  **Unicode** y, a continuación, haga clic en **guardar**.  
  
    > [!NOTE]
    >  Crear el directorio **BRE-Walkthroughs** en **C:\\**  si no existe y, a continuación, haga clic en **guardar**.  
  
7.  Cierre el Bloc de notas.  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a>Para crear la directiva empresarial ProcessPurchaseOrder  
  
1. En el **iniciar** menú Abrir **compositor**.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos. Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.  
  
   > [!NOTE]
   >  Muestra el Compositor de reglas de negocio la **abierto regla Store** cuadro de diálogo cuando se abre por primera vez en un equipo. Si ve el **abierto regla Store** cuadro de diálogo, haga clic en **Aceptar** después de comprobar el nombre de SQL server y el nombre de la base de datos.  
  
2. En la ventana Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.  
  
3. Edite el nombre de la directiva, **Policy1**a **ProcessPurchaseOrder** y presione ENTRAR. También puede cambiar el nombre de la directiva en el **propiedades** ventana.  
  
4. Haga clic en **versión 1.0**y, a continuación, haga clic en **AddNewRule**.  
  
5. Edite el nombre de la regla de **Rule1** a **ApprovalRule** y presione ENTRAR<strong>.</strong> También puede cambiar el nombre de la regla en el **propiedades** ventana.  
  
6. En la ventana Explorador de hechos, haga clic en el **esquemas XML** ficha.  
  
7. Haga clic en **esquemas**, haga clic en **examinar**y, a continuación, seleccione el **PO.xsd** archivo que creó anteriormente.  
  
8. En la ventana Propiedades, cambie el valor de la **tipo de documento** propiedad desde **PO** a **RuleTest.PO**.  
  
   > [!NOTE]
   >  Va a crear un proyecto de BizTalk denominado **RuleTest** más adelante en el [Tutorial: invocar la directiva desde una orquestación](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) tutorial. En que el tutorial, agregará el **PO.xsd** al proyecto, cree una orquestación que invoca la **ProcessPurchaseOrder** directiva y, a continuación, probar la directiva. Para probar la directiva desde la orquestación, deberá asegurarse de que cambie el **tipo de documento** propiedad  **\<nombre del proyecto\>.\< SchemaName\>**, que es **RuleTest.PO** en este caso.  
  
    ![BRE&#45;tutorial&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")  
  
9. En la ventana Explorador de hechos, expanda **PurchaseOrder**y, a continuación, expanda **elemento**.  
  
10. En el panel si (superior) de la derecha, haga clic en **condiciones**, haga clic en **predicados**y, a continuación, haga clic en **Menorqueigual**.  
  
     ![Compositor de reglas de negocio &#45; menor o igual](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")  
  
11. Arrastre el **cantidad** nodo desde la ventana Explorador de hechos para **argumento1** en el panel IF.  
  
     ![Compositor de reglas de negocio &#45; DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")  
  
     ![Compositor de reglas de negocio&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")  
  
12. En el panel si, haga clic en **argumento2**, tipo `500`, y, a continuación, presione ENTRAR.  
  
13. Arrastre el **estado** nodo desde la ventana Explorador de hechos hasta el panel, a continuación, en la parte inferior derecha del compositor de reglas de negocios.  
  
     ![Compositor de reglas de negocio&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")  
  
14. En el panel entonces, haga clic en **\<escriba un valor\>** y, a continuación, escriba **aprobado**.  
  
15. En la ventana Explorador de directivas, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **guardar**.  
  
## <a name="comments"></a>Comentarios  
  
-   Una directiva puede tener una o varias reglas. Va a agregar otra regla **DeniedRule**, en el [Tutorial: agregar una regla a la directiva](../core/walkthrough-adding-a-rule-to-the-policy.md) tutorial.  
  
-   Puede modificar la directiva para agregar más reglas, cambiar condiciones y modificar acciones cuando la directiva está en estado guardado.  
  
-   Puede dar prioridad a la ejecución de reglas mediante la especificación de la **prioridad** propiedad en las reglas de Compositor de reglas de negocios. Por ejemplo, si hace clic en el **ApprovedRule** nodo en la ventana del explorador de directivas, puede ver el **prioridad** propiedad en la ventana Propiedades. Cuanto mayor es el número, mayor es la prioridad de la regla.  
  
-   Puede usar un esquema XML, una base de datos o un ensamblado .NET como origen de datos para la directiva. En este tutorial, se usó un esquema XML como origen de datos. Para ejecutar la directiva, debe enviar una instancia del documento XML del esquema como un hecho al motor de reglas.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha realizado este tutorial, realice el [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) tutorial, lo que le ofrece instrucciones paso a paso para probar la **ProcessPurchaseOrder** directiva se creó en este tutorial.  
  
## <a name="see-also"></a>Vea también  
 [Acerca de las reglas de negocio](../core/about-business-rules.md)