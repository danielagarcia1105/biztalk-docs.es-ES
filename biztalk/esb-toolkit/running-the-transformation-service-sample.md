---
title: "Ejecutar el ejemplo de servicio de transformación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42064d32-5ec5-4219-a338-c5769969b958
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ac733f3164a319ed0b86e0f609de8ccd03bdbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-transformation-service-sample"></a><span data-ttu-id="34bea-102">Ejecutar el ejemplo de servicio de transformación</span><span class="sxs-lookup"><span data-stu-id="34bea-102">Running the Transformation Service Sample</span></span>
<span data-ttu-id="34bea-103">Puede ejecutar el ejemplo de servicios de transformación mediante cualquier herramienta o utilidad que se puede ejecutar métodos de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="34bea-103">You can execute the Transformation Service sample using any tool or utility that can execute Web service methods.</span></span> <span data-ttu-id="34bea-104">Por ejemplo, puede usar Storm, disponible en [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762)), o bien puede crear su propio cliente de prueba que invoca el servicio Web de transformación.</span><span class="sxs-lookup"><span data-stu-id="34bea-104">For example, you can use Storm, available from [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762)), or you can create your own test client that invokes the Transformation Web service.</span></span>  
  
 <span data-ttu-id="34bea-105">Para usar el servicio de Web .NET Studio para comprobar la correcta instalación de la muestra del servicio de transformación, escriba la dirección URL para el servicio Web basados en ASMX de transformación en el **extremo del WSDL** cuadro de texto y, a continuación, haga clic en el  **Obtener** botón.</span><span class="sxs-lookup"><span data-stu-id="34bea-105">To use the .NET Web Service Studio to test for correct installation of the Transformation Service sample, enter the URL for the ASMX-based Transformation Web service into the **WSDL EndPoint** text box, and then click the **Get** button.</span></span> <span data-ttu-id="34bea-106">Esto genera una interfaz de front-end de cliente que puede usar para llamar al servicio Web de transformación de ESB, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="34bea-106">This generates a client front-end interface that you can use to call the ESB Transformation Web Service, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="34bea-107">![Servicios de transformación](../esb-toolkit/media/ch6-transformationservice.gif "Ch6-TransformationService")</span><span class="sxs-lookup"><span data-stu-id="34bea-107">![Transformation Service](../esb-toolkit/media/ch6-transformationservice.gif "Ch6-TransformationService")</span></span>  
  
 <span data-ttu-id="34bea-108">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="34bea-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="34bea-109">**Mediante el estudio de servicio Web de .NET para probar el ejemplo de servicio de transformación**</span><span class="sxs-lookup"><span data-stu-id="34bea-109">**Using the .NET Web Service Studio to test the Transformation Service sample**</span></span>  
  
 <span data-ttu-id="34bea-110">El ejemplo de servicio de transformación contiene dos asignaciones de BizTalk de Microsoft y dos documentos de mensaje XML de prueba.</span><span class="sxs-lookup"><span data-stu-id="34bea-110">The Transformation Service sample contains two Microsoft BizTalk maps and two test XML message documents.</span></span> <span data-ttu-id="34bea-111">Puede ejecutar el servicio Web de transformación con los mensajes XML denominados TEST_CanonicalOrder_to_OrderConfirmation.xml y TEST_RetailOrder_to_CanonicalOrder.xml (que se encuentra en la carpeta \Source\Samples\TransformServices\Test\Data).</span><span class="sxs-lookup"><span data-stu-id="34bea-111">You can execute the Transformation Web service with the XML messages named TEST_CanonicalOrder_to_OrderConfirmation.xml and TEST_RetailOrder_to_CanonicalOrder.xml (located in the \Source\Samples\TransformServices\Test\Data folder).</span></span>  
  
 <span data-ttu-id="34bea-112">El servicio transformará automáticamente los mensajes con los esquemas CanonicalOrder.xsd y RetailOrder.xsd y OrderConfirmation.xsd (que se encuentra en la \Source\Samples\TransformServices\Source\ESB. Carpeta TransformServices.Schemas), y .NET del servicio Web Studio mostrará los mensajes resultantes transformados.</span><span class="sxs-lookup"><span data-stu-id="34bea-112">The service will automatically transform the messages using the schemas CanonicalOrder.xsd and RetailOrder.xsd and OrderConfirmation.xsd (located in the \Source\Samples\TransformServices\Source\ESB.TransformServices.Schemas folder), and .NET Web Service Studio will display the resulting transformed messages.</span></span> <span data-ttu-id="34bea-113">El siguiente procedimiento muestra cómo puede probar la asignación de CanonicalOrder_To_OrderConfirmation.</span><span class="sxs-lookup"><span data-stu-id="34bea-113">The following procedure shows how you can test the CanonicalOrder_To_OrderConfirmation map.</span></span>  
  
 <span data-ttu-id="34bea-114">**Para probar la asignación de GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation**</span><span class="sxs-lookup"><span data-stu-id="34bea-114">**To test the GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation map**</span></span>  
  
1.  <span data-ttu-id="34bea-115">Si no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="34bea-115">If the GlobalBank.ESB application is not running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="34bea-116">Escriba la siguiente representación de cadena del archivo TEST_CanonicalOrder_to_OrderConfirmation.xml como el valor de la **mensaje** parámetro en el **entrada** vista de árbol del servicio de Web .NET Studio.</span><span class="sxs-lookup"><span data-stu-id="34bea-116">Enter the following string representation of the TEST_CanonicalOrder_to_OrderConfirmation.xml file as the value of the **message** parameter in the **Input** tree view of .NET Web Service Studio.</span></span> <span data-ttu-id="34bea-117">Esta cadena se ajusta al esquema GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder:</span><span class="sxs-lookup"><span data-stu-id="34bea-117">This string conforms to the GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder schema:</span></span>  
  
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
  
3.  <span data-ttu-id="34bea-118">Escriba la siguiente cadena como el valor de la **Nombredemapa** parámetro en el **entrada** vista de árbol del servicio de Web .NET Studio.</span><span class="sxs-lookup"><span data-stu-id="34bea-118">Enter the following string as the value of the **mapName** parameter in the **Input** tree view of .NET Web Service Studio.</span></span> <span data-ttu-id="34bea-119">Esto es el nombre completo con tipo de la asignación de BizTalk que se ejecuta en el mensaje:</span><span class="sxs-lookup"><span data-stu-id="34bea-119">This is the fully typed name of the BizTalk map to execute against the message:</span></span>  
  
    ```  
    GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_  
        OrderConfirmation, GlobalBank.ESB.TransformServices.Maps,   
        Version=1.0.0.0, Culture=neutral, PublicKeyToken=<insertYourPublicKeyTokenHere>  
    ```  
  
4.  <span data-ttu-id="34bea-120">Haga clic en el **Invoke** botón para ejecutar el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="34bea-120">Click the **Invoke** button to execute the Web service.</span></span> <span data-ttu-id="34bea-121">El **salida** prueba cuadro muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="34bea-121">The **Output** test box displays the results.</span></span>