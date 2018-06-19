---
title: Ejecutar el ejemplo de servicio de transformación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42064d32-5ec5-4219-a338-c5769969b958
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ac733f3164a319ed0b86e0f609de8ccd03bdbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295236"
---
# <a name="running-the-transformation-service-sample"></a>Ejecutar el ejemplo de servicio de transformación
Puede ejecutar el ejemplo de servicios de transformación mediante cualquier herramienta o utilidad que se puede ejecutar métodos de servicio Web. Por ejemplo, puede usar Storm, disponible en [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762)), o bien puede crear su propio cliente de prueba que invoca el servicio Web de transformación.  
  
 Para usar el servicio de Web .NET Studio para comprobar la correcta instalación de la muestra del servicio de transformación, escriba la dirección URL para el servicio Web basados en ASMX de transformación en el **extremo del WSDL** cuadro de texto y, a continuación, haga clic en el  **Obtener** botón. Esto genera una interfaz de front-end de cliente que puede usar para llamar al servicio Web de transformación de ESB, tal como se muestra en la figura 1.  
  
 ![Servicios de transformación](../esb-toolkit/media/ch6-transformationservice.gif "Ch6-TransformationService")  
  
 **Figura 1**  
  
 **Mediante el estudio de servicio Web de .NET para probar el ejemplo de servicio de transformación**  
  
 El ejemplo de servicio de transformación contiene dos asignaciones de BizTalk de Microsoft y dos documentos de mensaje XML de prueba. Puede ejecutar el servicio Web de transformación con los mensajes XML denominados TEST_CanonicalOrder_to_OrderConfirmation.xml y TEST_RetailOrder_to_CanonicalOrder.xml (que se encuentra en la carpeta \Source\Samples\TransformServices\Test\Data).  
  
 El servicio transformará automáticamente los mensajes con los esquemas CanonicalOrder.xsd y RetailOrder.xsd y OrderConfirmation.xsd (que se encuentra en la \Source\Samples\TransformServices\Source\ESB. Carpeta TransformServices.Schemas), y .NET del servicio Web Studio mostrará los mensajes resultantes transformados. El siguiente procedimiento muestra cómo puede probar la asignación de CanonicalOrder_To_OrderConfirmation.  
  
 **Para probar la asignación de GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation**  
  
1.  Si no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
2.  Escriba la siguiente representación de cadena del archivo TEST_CanonicalOrder_to_OrderConfirmation.xml como el valor de la **mensaje** parámetro en el **entrada** vista de árbol del servicio de Web .NET Studio. Esta cadena se ajusta al esquema GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder:  
  
    ```  
    <ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
        Status="Status_2" xmlns:ns0=  
        "http://schemas.globalbank.esb.transformservices.com">  
        <OrderHeader><CustomerName>CustomerName_0</CustomerName>  
        <CustomerID>CustomerID_0</CustomerID><ShipToLine1>  
        ShipToLine1_0</ShipToLine1><ShipToLine2>ShipToLine2_0  
        </ShipToLine2><BillToLine1>BillToLine1_0</BillToLine1>  
        <BillToLine2>BillToLine2_0</BillToLine2><OrderTotal>OrderTotal_0  
        </OrderTotal></OrderHeader><OrderDetails><LineItem Qty="Qty_0"   
        PartNum="PartNum_1" Description="Description_2"   
        UnitPrice="UnitPrice_3" Ext="Ext_4" /></OrderDetails>  
        <B2BPartnerDetails CreditLimit="CreditLimit_0"   
        AccountBalance="AccountBalance_1"   
        LastOrderedData="LastOrderedData_2"   
        DiscountLevel="DiscountLevel_3" /></ns0:CanonicalOrder>  
    ```  
  
3.  Escriba la siguiente cadena como el valor de la **Nombredemapa** parámetro en el **entrada** vista de árbol del servicio de Web .NET Studio. Esto es el nombre completo con tipo de la asignación de BizTalk que se ejecuta en el mensaje:  
  
    ```  
    GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_  
        OrderConfirmation, GlobalBank.ESB.TransformServices.Maps,   
        Version=1.0.0.0, Culture=neutral, PublicKeyToken=<insertYourPublicKeyTokenHere>  
    ```  
  
4.  Haga clic en el **Invoke** botón para ejecutar el servicio Web. El **salida** prueba cuadro muestra los resultados.