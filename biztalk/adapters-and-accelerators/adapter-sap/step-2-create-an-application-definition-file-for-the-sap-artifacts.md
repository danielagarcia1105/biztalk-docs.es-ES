---
title: 'Paso 2: Crear un archivo de definición de aplicación para los artefactos SAP | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92e97a54a6818456efd2f4ac55ca7e2fc5bc7c35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970389"
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a>Paso 2: Crear un archivo de definición de aplicación para los artefactos SAP
![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** la característica catálogo de datos empresariales en Microsoft SharePoint Server expone e incorpora datos desde aplicaciones de línea de negocio (LOB) en los portales. Para incorporar estos datos en el sitio del portal, debe crear un archivo de definición de aplicación que pueden usar Microsoft Office SharePoint Server.  
  
 La herramienta Editor de definición de catálogo de datos empresariales, disponible con el SDK de Microsoft Office SharePoint Server 2007, permite crear un archivo de definición de aplicación para el catálogo de datos profesionales. Esta herramienta genera automáticamente un archivo XML para el archivo de definición, por lo que no es necesario crear manualmente el archivo en un documento XML editor.  
  
 El propósito de la aplicación de Microsoft Office SharePoint Server que se va a crear es:  
  
- Buscar un cliente en el sistema SAP según un nombre de cliente.  
  
- Seleccionar a un cliente de la lista de clientes recuperados y recuperar los detalles del cliente.  
  
- Seleccionar a un cliente de la lista de clientes recuperados y recuperar los pedidos de venta para el cliente.  
  
  Para cada uno de estos requisitos, debe completar un conjunto de tareas en la herramienta Editor de definición de catálogo de datos profesionales. Este tema proporciona instrucciones sobre cómo realizar estas tareas.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Asegúrese de que tiene el Editor de definición del catálogo de datos profesionales instalado como parte del SDK de Microsoft Office SharePoint Server 2007. Puede descargar el SDK desde [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130).  
  
-   Publicar el servicio WCF, como se describe en [paso 1: publicar los artefactos SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).  
  
## <a name="creating-an-application-definition-file"></a>Creación de un archivo de definición de aplicación  
 Este tema proporciona instrucciones paso a paso para crear un archivo de definición de aplicación para el servicio WCF.  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a>Conectar con el servicio WCF LOB y crear entidades  
 Debe conectarse al servicio WCF para extraer el lenguaje de descripción de servicios Web (WSDL) para el servicio. Desde el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos. Estos métodos se pueden usar para crear entidades. En este ejemplo, se crean dos entidades, uno de los pedidos de ventas y clientes.  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>Para conectarse al servicio WCF y crear entidades  
  
1. Inicie el Editor de definición del catálogo de datos profesionales. En el **iniciar** menú, haga clic en **Editor de definición de catálogo de datos de Microsoft Business**.  
  
2. En la barra de herramientas, haga clic en **Agregar sistema LOB**.  
  
3. En la ventana Agregar sistema LOB, haga clic en **conectar al servicio Web**.  
  
4. En el **URL** cuadro, escriba la dirección URL del servicio WCF. La dirección URL debe tener el formato siguiente:  
  
   ```  
   https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
   ```  
  
    donde Rfc.svc es el archivo creado para el contrato de Rfc.  
  
    La dirección URL está disponible cuando se prueba si el servicio de WCF se publicó correctamente, tal como se describe en el tema [paso 1: publicar los artefactos SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).  
  
5. Haga clic en **Conectar**.  
  
6. Para ver las operaciones que seleccionó en el Asistente para desarrollo de servicio de adaptador de WCF, haga clic en el **Agregar método Web** ficha. Verá los siguientes métodos:  
  
   - SD_RFC_CUSTOMER_GET  
  
   - BAPI_SALESORDER_GETLIST  
  
      ![Agregar métodos web a la aplicación de BDC](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")  
  
     Arrastre los métodos a la superficie de diseño. Asegúrese de que arrastre ambas operaciones a las distintas entidades.  
  
     ![Crear entidades para los métodos web](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")  
  
7. Haga clic en **Aceptar**.  
  
8. En el **escriba el nombre para el sistema LOB** cuadro de diálogo, escriba un nombre en el **nombre del sistema de LOB** cuadro. En este ejemplo, llámelo **Customer_Order**y, a continuación, haga clic en **Aceptar**.  
  
9. En el Editor datos profesionales catálogo definición, se muestran las dos entidades como **Entity0** y **Entity1**. Proporcionar nombres descriptivos a estas entidades. Cambiar el nombre de la entidad para SD_RFC_CUSTOMER_GET a **cliente**y cambiar el nombre de la entidad para BAPI_SALESORDER_GETLIST a **SalesOrder**. Realice los pasos siguientes para cambiar el nombre de las entidades:  
  
    1.  Expanda el **Customer_Order** nodo y, a continuación, expanda el **entidades** nodo.  
  
    2.  Seleccione el **Entity0** nodo.  
  
    3.  En el panel Propiedades, escriba **cliente** en el **nombre** cuadro.  
  
         ![Cambiar el nombre de la entidad](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")  
  
    4.  Seleccione el **Entity1** nodo.  
  
    5.  En el panel Propiedades, escriba **SalesOrder** en el **nombre** cuadro.  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a>Especifique el nombre de usuario y contraseña encabezados para los métodos  
 Al crear un servicio WCF para los documentos RFC seleccionados en el sistema SAP, los encabezados de nombre y la contraseña del usuario ha especificado como parte de la configuración de comportamiento de punto de conexión. Consulte [paso 1: publicar los artefactos SAP como un servicio WCF](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md). Debe especificar los mismos valores para las propiedades del método.  
  
##### <a name="to-specify-user-name-and-password-headers"></a>Para especificar encabezados de nombre y la contraseña de usuario  
  
1.  Agregue los encabezados de nombre y la contraseña de usuario para el método SD_RFC_CUSTOMER_GET.  
  
    1.  En el panel de objetos de metadatos, expanda el **cliente** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Haga clic en el nodo SD_RFC_CUSTOMER_GET y, en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.  
  
    3.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderUserName** para el **nombre** cuadro. De forma similar, escriba **MyUserHeader** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
         ![Agregar una propiedad](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")  
  
    4.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderPassword** para el **nombre** cuadro. De forma similar, escriba **MyPassHeader** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
    5.  Haga clic en **Aceptar**.  
  
2.  Agregue los encabezados de nombre y la contraseña de usuario para el método BAPI_SALESORDER_GETLIST.  
  
    1.  En el panel de objetos de metadatos, expanda el **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Haga clic en el nodo BAPI_SALESORDER_GETLIST y, en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.  
  
    3.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderUserName** para el **nombre** cuadro. De forma similar, escriba **MyUserHeader** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
    4.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderPassword** para el **nombre** cuadro. De forma similar, escriba **MyPassHeader** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
    5.  Haga clic en **Aceptar**.  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a>Establecer la seguridad de Single Sign-On para conectarse al sistema SAP  
 Cuando haya terminado de realizar todos los procedimientos de este tema, habrá creado un archivo de definición de aplicación que se puede importar a una aplicación de SharePoint. Desde la aplicación, invoca los métodos SAP para recuperar los datos pertinentes desde el sistema SAP. Para habilitar esta opción, debe crear una asignación entre un usuario en el sistema SAP y el usuario en la aplicación de SharePoint. Cree esta asignación en la consola de Administración Central de SharePoint después de importar el archivo de definición de aplicación.  
  
 Sin embargo, para crear la asignación, debe establecer una propiedad **SecondarySsoApplicationId** en el Editor de definición de catálogo de datos de Business.  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a>Para establecer la propiedad SecondarySsoApplicationId  
  
1.  En el panel de objetos de metadatos, expanda el **Customer_Order** nodo y, a continuación, expanda el **instancias** nodo.  
  
2.  Haga clic en **Customer_Order_Instance**y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.  
  
3.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **SecondarySsoApplicationId** para el **nombre** cuadro. De forma similar, escriba **SAPSSO** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
     ![Agregue la propiedad SSO](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")  
  
4.  Haga clic en **Aceptar**.  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a>Requisito 1: Busque los clientes basándose en el nombre del cliente  
 Para crear un archivo de definición de aplicación que puede usarse para buscar los clientes basándose en el nombre del cliente, debe realizar el siguiente conjunto de tareas.  
  
-   En el método SD_RFC_CUSTOMER_GET, cree un filtro y asignarla al parámetro que almacena el nombre del cliente.  
  
-   Crear un **buscador** instancia de método para el método SD_RFC_CUSTOMER_GET. Un **buscador** método recupera una lista de registros basada en un filtro.  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a>Para crear un filtro y asignarla al parámetro de nombre de cliente  
  
1.  Crear un filtro.  
  
    1.  En el panel de objetos de metadatos, expanda el **cliente** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el método SD_RFC_CUSTOMER_GET, haga clic en **filtros**y, a continuación, haga clic en **Agregar filtro**.  
  
         ![Agregar filtro a un método](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")  
  
    3.  En el panel Propiedades, escriba **CustomerName** en el **nombre** cuadro.  
  
         ![Especifique un nombre para el filtro](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")  
  
    4.  Para el **FilterType** propiedad, seleccione **WildcardFilter**.  
  
2.  Asignar el filtro para el **nombre1** parámetro del método SD_RFC_CUSTOMER_GET.  
  
    1.  En el panel de objetos de metadatos, expanda el **cliente** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el método SD_RFC_CUSTOMER_GET y, a continuación, expanda el **parámetros** nodo.  
  
    3.  Expanda el **nombre1** nodo y haga clic en el segundo **nombre1** nodo. El **nombre1** parámetro contiene el nombre del cliente.  
  
    4.  En el panel Propiedades, seleccione **CustomerName** desde el **FilterDescriptor** lista.  
  
         ![Asignar el filtro a un parámetro de método](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a>Para crear una instancia de método de buscador para el método SD_RFC_CUSTOMER_GET  
  
1.  En el panel de objetos de metadatos, expanda el **cliente** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **SD_RFC_CUSTOMER_GET** nodo, haga clic en **instancias**y, a continuación, haga clic en **Agregar instancia del método** para abrir la ventana Crear instancia de método.  
  
     ![Agregar una instancia de método](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  En la ventana Crear instancia de método, haga clic en **buscador** para **tipo de método de instancia**. Seleccione **CUSTOMER_T** para **devolver TypeDescriptor**.  
  
     ![Agregar una instancia de método de buscador](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")  
  
4.  Haga clic en **Aceptar**.  
  
5.  En el panel Propiedades, escriba **GetCustomerByName_Instance** en el **nombre** cuadro.  
  
     ![Especifique un nombre para la instancia de método](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a>Requisito 2: Recuperar los detalles de un cliente específico de la lista de clientes  
 Para crear un archivo de definición de aplicación que puede usarse para buscar los clientes basándose en el nombre del cliente, debe realizar el siguiente conjunto de tareas.  
  
-   En el método SD_RFC_CUSTOMER_GET, crear un identificador y asignarla al parámetro que almacena el número de cliente.  
  
-   Crear un **buscador específico** instancia de método para el método SD_RFC_CUSTOMER_GET. Un **buscador específico** método busca un registro específico basado en un identificador.  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a>Para crear un identificador y asignarla al parámetro de número de cliente  
  
1.  Crear un identificador de la **cliente** entidad.  
  
    1.  En el panel de objetos de metadatos, expanda el **cliente** nodo.  
  
    2.  Haga clic en el **identificadores** nodo y, a continuación, seleccione **Agregar identificador**.  
  
         ![Agregar un identificador a un método](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")  
  
    3.  En el panel Propiedades, escriba **CustomerID** en el **nombre** cuadro.  
  
    4.  Seleccione **System.String** para el **tipo** cuadro.  
  
         ![Especifique un nombre para el identificador](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")  
  
2.  Asignar el identificador para el parámetro de clave para el método SD_RFC_CUSTOMER_GET.  
  
    1.  En el panel de objetos de metadatos, expanda el **cliente** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el método SD_RFC_CUSTOMER_GET y, a continuación, expanda el **parámetros** nodo.  
  
    3.  Expanda el **KUNNR** parámetro y, a continuación, haga clic en el segundo **KUNNR** nodo.  
  
    4.  En el panel Propiedades, seleccione **CustomerID [Customer]** desde el **identificador** lista.  
  
         ![Asignar el identificador a un parámetro](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")  
  
3.  Establecer una asociación entre los parámetros de entrada y salidas.  
  
    1.  En el panel de objetos de metadatos, expanda el **cliente** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el método SD_RFC_CUSTOMER_GET y, a continuación, expanda el **parámetros** nodo.  
  
    3.  Expanda el **CUSTOMER_T** nodo y, a continuación, el segundo **CUSTOMER_T** nodo, el **elemento** nodo y, a continuación, haga clic en el **KUNNR** nodo.  
  
    4.  En el panel Propiedades, seleccione **CustomerID [Customer]** desde el **identificador** lista.  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a>Para crear una instancia de método de buscador específico para el método SD_RFC_CUSTOMER_GET  
  
1.  En el panel de objetos de metadatos, expanda el **cliente** nodo y, a continuación, el **métodos** nodo.  
  
2.  Expanda el **SD_RFC_CUSTOMER_GET** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.  
  
     ![Agregar una instancia de método](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  En la ventana Crear instancia de método, seleccione **buscador específico** para **tipo de método de instancia**. De forma similar, seleccione **CUSTOMER_T** para **TypeDescriptor de devolución**.  
  
     ![Agregar una instancia de método de buscador específico](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")  
  
4.  Haga clic en **Aceptar**.  
  
5.  En el panel Propiedades, escriba **GetCustomerByNumber_Instance** para el **nombre** cuadro.  
  
     ![Especifique un nombre para la instancia de método](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a>Requisito 3: Recuperar los detalles de pedido de ventas para un cliente específico de la lista de clientes  
 Para crear un archivo de definición de aplicación que puede usarse para recuperar los detalles de pedido de ventas para un cliente específico, debe realizar el siguiente conjunto de tareas.  
  
-   Configurar una asociación entre el **cliente** y **SalesOrder** entidades.  
  
-   Crear un **asociación** método para el método BAPI_SALESORDER_GETLIST.  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a>Para crear una asociación entre las entidades Customer y SalesOrder  
  
1.  En el panel de objetos de metadatos, expanda el **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el método BAPI_SALESORDER_GETLIST y, a continuación, expanda el **parámetros** nodo.  
  
3.  Expanda el **CUSTOMER_NUMBER** nodo y, a continuación, haga clic en el segundo **CUSTOMER_NUMBER** nodo.  
  
4.  En el panel Propiedades, seleccione **CustomerID [Customer]** desde el **identificador** lista.  
  
     ![Crear asociación entre las dos entidades](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a>Para crear una instancia de método de asociación para el método BAPI_SALESORDER_GETLIST  
  
1.  En el panel de objetos de metadatos, expanda el **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **BAPI_SALESORDER_GETLIST** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.  
  
     ![Agregar una instancia de método de asociación](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")  
  
3.  En la ventana Crear instancia de método, seleccione **asociación** para **tipo de método de instancia**.  
  
4.  En el **entidades de origen** lista, seleccione **cliente**.  
  
5.  En el **TypeDescriptor de devolución** lista, seleccione **SALES_ORDERS**...  
  
     ![Cree una instancia de método de asociación](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el panel Propiedades, escriba **SalesOrderForCustomer_Instance** para el **nombre** cuadro.  
  
     ![Especifique un nombre para el método de asociación](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")  
  
### <a name="remove-parameters-of-systemnullable-type"></a>Quitar parámetros de tipo System.Nullable  
 Al crear el **asociación** instancia de método para el método BAPI_SALESORDER_GETLIST, seleccionó el tipo de valor devuelto como SALES_ORDERS. Si expande el parámetro SALES_ORDER, observará que algunos parámetros son de tipo System.Nullable. Puede ver que el parámetro de tipo, seleccione el parámetro en el Editor de definición de catálogo de datos de Business y examinando el valor de la **TypeName** propiedad.  
  
 Para estos parámetros, el Editor de definición del catálogo de datos profesionales crea otro parámetro con el mismo nombre pero con un sufijo "Specified". Por ejemplo, examine los parámetros *ITM_NUMBER* y *ITM_NUMBERSpecified*. Microsoft Office SharePoint Server no admite parámetros System.Nullable. Por lo tanto, al intentar registros que contienen el tipo de parámetro System.Nullable, produce una excepción. Por lo tanto, debe quitar los parámetros (con y sin el sufijo "Specified" y que tengan el mismo nombre) desde el Editor de definición de catálogo de datos de Business  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a>Para quitar los parámetros de tipo System.Nullable  
  
1.  En el panel de objetos de metadatos, expanda el **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **BAPI_SALESORDER_GETLIST** nodo y, a continuación, expanda el **parámetros** nodo.  
  
3.  Expanda **SALES_ORDERS**, expanda el segundo **SALES_ORDERS**y, a continuación, expanda **elemento**.  
  
4.  Haga clic en el parámetro que contiene el sufijo "Specified" en el nombre y, a continuación, seleccione **eliminar**.  
  
5.  Haga clic en el parámetro que tiene el mismo nombre que el parámetro que se ha eliminado, sin el sufijo, y, a continuación, seleccione **eliminar**. Normalmente, este parámetro es correcta antes del parámetro que tiene el sufijo "Specified".  
  
### <a name="set-default-parameters"></a>Establecer parámetros predeterminados  
 El BAPI_SALESORDER_GETLIST toma dos parámetros. Uno de estos parámetros, TRANSACTION_GROUP, es el parámetro predeterminado. Por lo tanto, debe establecer el valor predeterminado para este parámetro.  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a>Para establecer el valor predeterminado para TRANSACTION_GROUP  
  
1.  En el panel de objetos de metadatos, expanda el **SalesOrder** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **BAPI_SALESORDER_GETLIST** nodo y, a continuación, expanda el **instancias** nodo.  
  
3.  Seleccione el **SalesOrderForCustomer_Instance** método de instancia y, en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** cuadro.  
  
4.  En la ventana de edición, expanda **TRANSACTION_GROUP** nodo y para el **TRANSACTION_GROUP** , especifique el valor predeterminado 0.  
  
     ![Especifique un valor predeterminado para la instancia de método](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")  
  
5.  Haga clic en **Cerrar**.  
  
### <a name="export-the-application-definition-to-a-file"></a>Exportar la definición de aplicación a un archivo  
 Ahora ha creado una definición de aplicación que contiene los metadatos de instancia del sistema SAP. Esta definición se debe exportar a un archivo XML, que puede importarse en Microsoft Office SharePoint Server.  
  
##### <a name="to-export-the-application-definition-to-a-file"></a>Para exportar la definición de aplicación a un archivo  
  
1.  En el panel de objetos de metadatos, haga clic en el **Customer_Order** nodo y, a continuación, haga clic en **exportar**.  
  
2.  Guarde el archivo como Customer_Order.xml.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora debe crear una aplicación de SharePoint para recuperar datos de un sistema SAP. Consulte [paso 3: crear una aplicación de SharePoint para recuperar datos desde SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) para obtener instrucciones.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentación de datos de un sistema de SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)