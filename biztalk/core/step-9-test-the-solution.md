---
title: 'Paso 9: Probar la solución | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df446ccc-add3-4dd3-b674-253dda385541
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89a3722d6d8e1d4b730341dfaf16d60af1686f21
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973074"
---
# <a name="step-9-test-the-solution"></a>Paso 9: Probar la solución
En este tema, probará la aplicación híbrida enviando un mensaje de pedido de ventas X12 840 al extremo HTTP donde se implementa el acuerdo EDI. El aspecto del mensaje de pedido de ventas de muestra será parecido al siguiente:  
  
```  
ISA*00*          *00*          *ZZ*CONTOSO        *ZZ*NORTHWIND      *991221*1226*U*00401*000000025*0*T*:~  
GS*PO*THEM*US*19991221*1226*1*X*004010~  
ST*840*0002~  
BQT*00*BQT02*20120619*001*20120719~  
PER*1A*John*EM*John@contoso.com~  
N1*001~  
N2*co~  
N3*Contoso*One Contoso Way~  
N4*Redmond*WA*98052*US~  
PO1*PO101*121*01*10*AA*A1*1~  
CTT*475~  
SE*10*0002~  
GE*1*1~  
IEA*1*000000025~  
```  
  
 En este mensaje, el segmento resaltado (la línea que empieza con **PO1**) contiene la cantidad del pedido. La cantidad del pedido en este mensaje es *121*. Por lo tanto, si envía este mensaje, se debe insertar en el **SalesOrder** tabla. Puede actualizar la cantidad a menos de 100 y volver a enviar el mensaje y, después, este debe enviarse a la ubicación de archivo especificada en el puerto de envío de archivos.  
  
 Para enviar este mensaje al acuerdo EDI, puede usar el **MessageSender** herramienta se incluye en los ejemplos para [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]. Puede descargar los ejemplos desde [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).  
  
### <a name="to-send-a-message"></a>Para enviar un mensaje  
  
1.  Busque la **MessageSender** del proyecto en el paquete de ejemplo y genérelo.  
  
2.  Utilice el cuadro **MessageSender** ejecutable de línea de comandos (en la carpeta \bin\Debug del proyecto) para enviar mensajes al acuerdo EDI implementado. Esta herramienta acepta el parámetro de la línea de comandos en el siguiente formato:  
  
    ```  
    MessageSender.exe <ServiceBusNamespace> <IssuerName> <IssuerKey> <EDI agreement endpoint> <MessageFilepath> <ContentType>  
    ```  
  
     Donde  
  
    |Nombre del parámetro|Description|  
    |--------------------|-----------------|  
    |ServiceBusNamespace|Espacio de nombres de Service Bus|  
    |IssuerName|Nombre del emisor del espacio de nombres especificado|  
    |IssuerKey|Clave del emisor del espacio de nombres especificado|  
    |Extremo del acuerdo EDI|El extremo en el que se implementa el acuerdo EDI. Puede obtener esta dirección URL del extremo de la pestaña Configuración de recepción (y dentro de ese, la página de transporte) del acuerdo EDI implementado en [(para Azure) del paso 2: crear un acuerdo de EDI](../core/step-2-for-azure-create-an-edi-agreement.md).|  
    |MessageFilePath|Ruta de acceso al archivo que contiene el mensaje de solicitud de muestra.|  
    |ContentType|Para este tutorial, establezca este parámetro en **texto/sin formato**.|  
  
     Abra un símbolo del sistema y desplácese a la solución en la que compiló el **MessageSender** proyecto. Ejecute el siguiente comando para enviar el mensaje de solicitud con una cantidad de pedido superior a 100:  
  
    ```  
    MessageSender.exe <service bus namespace> owner <issuer key>https://<namespace>.servicebus.appfabriclabs.com/7576ff3d-a0f3-4a46-a4f6-f5be4a50616a/DemoAgreement<path to the sample message> "text/plain"  
    ```  
  
3.  Abra SQL Server Management Studio, conéctese a la base de datos que contiene el **SalesOrder** de tabla y compruebe que se inserta un nuevo registro en la tabla. Tenga en cuenta el valor de la **Qty** columna; debe ser *121*.  
  
4.  Use **MessageSender** enviar otro mensaje, pero esta vez establezca el valor de la cantidad pedida en el mensaje a *99*. Observará que ahora hay ningún registro insertado en el **SalesOrder** tabla. En su lugar, el mensaje se copia en la ubicación de archivo especificada para recibir los mensajes con cantidades de pedido inferior a 100. El mensaje recibido es similar al siguiente:  
  
    ```  
    <ns1:SalesOrder xmlns:ns0="http://schemas.microsoft.com/BizTalk/EDI/X12/2006" xmlns:ns1="http://ECommerceSalesOrder.Inbound">  
      <CompanyCode>co</CompanyCode>  
      <PartID>1</PartID>  
      <Quantity>99</Quantity>  
      <AskPrice>10</AskPrice>  
      <RequestShipmentDate>2012-07-19</RequestShipmentDate>  
      <Address>  
        <Line1>Contoso</Line1>  
        <Line2>One Contoso Way</Line2>  
        <City>Redmond</City>  
        <State>WA</State>  
        <Country>US</Country>  
        <Zipcode>98052</Zipcode>  
      </Address>  
      <Contact>  
        <Firstname>John</Firstname>  
        <Lastname>John@contoso.com</Lastname>  
      </Contact>  
      <Comments>Order from Partnerco</Comments>  
      <DateNow>2012-06-19</DateNow>  
    </ns1:SalesOrder>  
  
    ```  
  
     Tenga en cuenta el valor de la **cantidad** elemento. Es *99*.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)