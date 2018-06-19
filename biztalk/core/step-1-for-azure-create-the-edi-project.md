---
title: 'Paso 1 (para Azure): Crear el proyecto EDI | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d353129-04f0-456b-b371-b346959f5155
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51264a79480031bd334dfb7d699a3a701f2c0254
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010005"
---
# <a name="step-1-for-azure-create-the-edi-project"></a>Paso 1 (para Azure): Crear el proyecto EDI
En esta sección, Contoso crea un proyecto de EDI con la versión de [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] de abril de 2012. Como parte del proyecto, Contoso agrega lo siguiente:  
  
-   Un esquema de pedido de ventas interno (**ECommerceSalesOrder.xsd**) a la que el X12 840 esquema de pedido de ventas de EDI que se van a transformar. Contoso usa el esquema interno para procesar el mensaje una vez recibido en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Una transformación (**EDI840TOSALESORDER. TRFM**) para convertir el X12 esquema de pedidos de 840 venta el **ECommerceSalesOrder** esquema.  
  
 Contoso usa estos artefactos al crear un acuerdo en el portal Azure de BizTalk en [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].  
  
### <a name="to-create-edi-project"></a>Para crear un proyecto EDI  
  
1.  Abra Visual Studio, desde la **archivo** menú, seleccione **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, desde el **plantillas instaladas**, seleccione **Bus de servicio**. Especifique un nombre de proyecto y una ubicación para el proyecto y, a continuación, haga clic en **Aceptar**.  
  
##  <a name="BKMK_CreateSchema"></a>Para crear un esquema en el proyecto EDI  
  
1.  En el Explorador de soluciones, haga clic en el nombre del proyecto que acaba de crear, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, desde el **plantillas instaladas**, seleccione **esquema**, especifique el nombre del esquema como **ECommerceSalesOrder.xsd**y, a continuación, haga clic en **agregar**.  
  
3.  Edite y cree el esquema para que quede de forma similar a la siguiente:  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns="http://ECommerceSalesOrder.Inbound" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://ECommerceSalesOrder.Inbound" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="SalesOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="CompanyCode" type="xs:string" />  
            <xs:element name="PartID" type="xs:int" />  
            <xs:element name="Quantity" type="xs:int" />  
            <xs:element name="AskPrice" type="xs:decimal" />  
            <xs:element name="RequestShipmentDate" type="xs:date" />  
            <xs:element name="Address">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Line1" type="xs:string" />  
                  <xs:element name="Line2" type="xs:string" />  
                  <xs:element name="City" type="xs:string" />  
                  <xs:element name="State" type="xs:string" />  
                  <xs:element name="Country" type="xs:string" />  
                  <xs:element name="Zipcode" type="xs:int" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Contact">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Firstname" type="xs:string" />  
                  <xs:element name="Lastname" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Comments" type="xs:string" />  
            <xs:element name="DateNow" type="xs:date" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
     Puede usar el Editor de esquemas para crear este esquema. Para obtener más información, consulte [utilizando el Editor de BizTalk](../core/using-biztalk-editor.md).  
  
4.  Guarde el esquema.  
  
##  <a name="BKMK_CreateTrfm"></a>Para crear una transformación en el proyecto EDI  
  
1.  En el Explorador de soluciones, haga clic en el nombre del proyecto que acaba de crear, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, desde el **plantillas instaladas**, seleccione **mapa**, especifique el nombre del esquema como **Edi840ToSalesOrder.trfm**y, a continuación, haga clic en **agregar**.  
  
3.  En el mapa, para el esquema de origen seleccione **X12_00401_840.xsd**. Este es el esquema X12 estándar para un pedido de ventas EDI. Ya debe tener agregado este esquema al proyecto EDI que ha creado. Puede descargar este y otros X12 esquemas a partir de [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057). El X12 esquemas forman parte de la **MicrosoftEdiXSDTemplates.zip** paquete disponible desde la ubicación de descarga.  
  
4.  Para el esquema de destino, seleccione **ECommerceSalesOrder.xsd**. Ha creado este esquema anteriormente en este tema.  
  
5.  Cree el mapa conectando los nodos correspondientes en los esquemas de origen y destino.  
  
6.  Guarde el mapa.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)