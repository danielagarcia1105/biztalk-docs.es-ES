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
# <a name="step-1-for-azure-create-the-edi-project"></a><span data-ttu-id="e137b-102">Paso 1 (para Azure): Crear el proyecto EDI</span><span class="sxs-lookup"><span data-stu-id="e137b-102">Step 1 (For Azure): Create the EDI Project</span></span>
<span data-ttu-id="e137b-103">En esta sección, Contoso crea un proyecto de EDI con la versión de [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] de abril de 2012.</span><span class="sxs-lookup"><span data-stu-id="e137b-103">In this section, Contoso creates an EDI project using the [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] April 2012 release.</span></span> <span data-ttu-id="e137b-104">Como parte del proyecto, Contoso agrega lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e137b-104">As part of the project, Contoso adds the following:</span></span>  
  
-   <span data-ttu-id="e137b-105">Un esquema de pedido de ventas interno (**ECommerceSalesOrder.xsd**) a la que el X12 840 esquema de pedido de ventas de EDI que se van a transformar.</span><span class="sxs-lookup"><span data-stu-id="e137b-105">An internal sales order schema (**ECommerceSalesOrder.xsd**) to which the X12 840 EDI sales order schema will be transformed.</span></span> <span data-ttu-id="e137b-106">Contoso usa el esquema interno para procesar el mensaje una vez recibido en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e137b-106">Contoso uses the internal schema to process the message after it is received into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="e137b-107">Una transformación (**EDI840TOSALESORDER. TRFM**) para convertir el X12 esquema de pedidos de 840 venta el **ECommerceSalesOrder** esquema.</span><span class="sxs-lookup"><span data-stu-id="e137b-107">A transform (**EDI840TOSALESORDER.TRFM**) to convert the X12 840 sales order schema to the **ECommerceSalesOrder** schema.</span></span>  
  
 <span data-ttu-id="e137b-108">Contoso usa estos artefactos al crear un acuerdo en el portal Azure de BizTalk en [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e137b-108">Contoso uses these artifacts while creating an agreement in the Azure BizTalk portal in [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span>  
  
### <a name="to-create-edi-project"></a><span data-ttu-id="e137b-109">Para crear un proyecto EDI</span><span class="sxs-lookup"><span data-stu-id="e137b-109">To create EDI project</span></span>  
  
1.  <span data-ttu-id="e137b-110">Abra Visual Studio, desde la **archivo** menú, seleccione **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e137b-110">Open Visual Studio, from the **File** menu point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="e137b-111">En el **nuevo proyecto** cuadro de diálogo, desde el **plantillas instaladas**, seleccione **Bus de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e137b-111">In the **New Project** dialog box, from the **Installed Templates**, select **Service Bus**.</span></span> <span data-ttu-id="e137b-112">Especifique un nombre de proyecto y una ubicación para el proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e137b-112">Specify a project name and a location for the project, and then click **OK**.</span></span>  
  
##  <a name="BKMK_CreateSchema"></a><span data-ttu-id="e137b-113">Para crear un esquema en el proyecto EDI</span><span class="sxs-lookup"><span data-stu-id="e137b-113">To create a schema within the EDI project</span></span>  
  
1.  <span data-ttu-id="e137b-114">En el Explorador de soluciones, haga clic en el nombre del proyecto que acaba de crear, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e137b-114">From the Solution Explorer, right-click the project name you just created, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="e137b-115">En el **Agregar nuevo elemento** cuadro de diálogo, desde el **plantillas instaladas**, seleccione **esquema**, especifique el nombre del esquema como **ECommerceSalesOrder.xsd**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e137b-115">In the **Add New Item** dialog box, from the **Installed Templates**, select **Schema**, specify the name of the schema as **ECommerceSalesOrder.xsd**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="e137b-116">Edite y cree el esquema para que quede de forma similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e137b-116">Edit and build the schema to resemble the following:</span></span>  
  
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
  
     <span data-ttu-id="e137b-117">Puede usar el Editor de esquemas para crear este esquema.</span><span class="sxs-lookup"><span data-stu-id="e137b-117">You can use the Schema Editor to build this schema.</span></span> <span data-ttu-id="e137b-118">Para obtener más información, consulte [utilizando el Editor de BizTalk](../core/using-biztalk-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e137b-118">For more information, see [Using BizTalk Editor](../core/using-biztalk-editor.md).</span></span>  
  
4.  <span data-ttu-id="e137b-119">Guarde el esquema.</span><span class="sxs-lookup"><span data-stu-id="e137b-119">Save the schema.</span></span>  
  
##  <a name="BKMK_CreateTrfm"></a><span data-ttu-id="e137b-120">Para crear una transformación en el proyecto EDI</span><span class="sxs-lookup"><span data-stu-id="e137b-120">To create a transform within the EDI project</span></span>  
  
1.  <span data-ttu-id="e137b-121">En el Explorador de soluciones, haga clic en el nombre del proyecto que acaba de crear, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e137b-121">From the Solution Explorer, right-click the project name you just created, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="e137b-122">En el **Agregar nuevo elemento** cuadro de diálogo, desde el **plantillas instaladas**, seleccione **mapa**, especifique el nombre del esquema como **Edi840ToSalesOrder.trfm**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e137b-122">In the **Add New Item** dialog box, from the **Installed Templates**, select **Map**, specify the name of the schema as **Edi840ToSalesOrder.trfm**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="e137b-123">En el mapa, para el esquema de origen seleccione **X12_00401_840.xsd**.</span><span class="sxs-lookup"><span data-stu-id="e137b-123">In the map, for the source schema select **X12_00401_840.xsd**.</span></span> <span data-ttu-id="e137b-124">Este es el esquema X12 estándar para un pedido de ventas EDI.</span><span class="sxs-lookup"><span data-stu-id="e137b-124">This is the standard X12 schema for an EDI sales order.</span></span> <span data-ttu-id="e137b-125">Ya debe tener agregado este esquema al proyecto EDI que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e137b-125">You must have already added this schema to the EDI project you created.</span></span> <span data-ttu-id="e137b-126">Puede descargar este y otros X12 esquemas a partir de [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span><span class="sxs-lookup"><span data-stu-id="e137b-126">You can download this, and other X12 schemas from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span></span> <span data-ttu-id="e137b-127">El X12 esquemas forman parte de la **MicrosoftEdiXSDTemplates.zip** paquete disponible desde la ubicación de descarga.</span><span class="sxs-lookup"><span data-stu-id="e137b-127">The X12 schemas are part of the **MicrosoftEdiXSDTemplates.zip** package available from the download location.</span></span>  
  
4.  <span data-ttu-id="e137b-128">Para el esquema de destino, seleccione **ECommerceSalesOrder.xsd**.</span><span class="sxs-lookup"><span data-stu-id="e137b-128">For the destination schema, select **ECommerceSalesOrder.xsd**.</span></span> <span data-ttu-id="e137b-129">Ha creado este esquema anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="e137b-129">You created this schema earlier in this topic.</span></span>  
  
5.  <span data-ttu-id="e137b-130">Cree el mapa conectando los nodos correspondientes en los esquemas de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="e137b-130">Create the map by connecting the relevant nodes in the source and target schemas.</span></span>  
  
6.  <span data-ttu-id="e137b-131">Guarde el mapa.</span><span class="sxs-lookup"><span data-stu-id="e137b-131">Save the map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e137b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e137b-132">See Also</span></span>  
 [<span data-ttu-id="e137b-133">Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="e137b-133">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)