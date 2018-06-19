---
title: 'Paso 3: Crear una aplicación de SharePoint para recuperar datos de SAP | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO application, creating an
- Business Data Catalog Definition Editor
- application definition file, importing
- Web Part
- SSP
- Web Part page, creating a
- Shared Services Provider, creating a
ms.assetid: 7158caec-9dc0-477c-9db3-179e634e5196
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879a4b48da7645471e53db357f7c0a6260117f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219540"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a>Paso 3: Crear una aplicación de SharePoint para recuperar datos de SAP
![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** ahora debe dejar el archivo de definición de aplicación que ha creado mediante la herramienta Editor de definición de catálogo de datos profesionales e importarlo en Microsoft Office SharePoint Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Deberá haber creado un archivo de definición de aplicación tal como se describe en [paso 2: crear un archivo de definición de aplicación para los artefactos de SAP](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).  
  
-   Debe ejecutar el servicio Microsoft Single Sign-on.  
  
## <a name="how-to-create-a-sharepoint-application"></a>Cómo crear una aplicación de SharePoint  
 Crear una aplicación de SharePoint implica los pasos siguientes:  
  
-   Crear una aplicación de inicio de sesión único (SSO) en SharePoint  
  
-   Crear un proveedor de servicios compartidos  
  
-   Importe el archivo de definición de aplicación  
  
-   Crear una página de elementos Web y agregar elementos Web  
  
 Este tema muestra cómo realizar estos pasos.  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>Crear una aplicación de SSO en SharePoint  
 Para obtener acceso a los datos en un sistema SAP desde una aplicación de SharePoint, debe configurar una aplicación de SSO que se asigna un usuario de SharePoint a un usuario SAP. Crear una aplicación de SSO en SharePoint implica los pasos siguientes:  
  
1.  **Administrar la configuración de servidor de inicio de sesión único**. En este paso, especifique una cuenta de usuario que puede administrar y configurar el servicio de inicio de sesión único. Puede hacerlo en la página Administrar configuración de servidor. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información acerca de este paso, consulte la sección "Configurar inicio de sesión único para Office SharePoint Server 2007" en [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
2.  **Administrar la configuración de las definiciones de aplicaciones de empresa**. En este paso, configurará la configuración de la definición de aplicación empresarial. Puede hacerlo desde la página Administrar configuración de definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint.  
  
    1.  En Administración Central, en la barra de navegación superior, haga clic en **Operations**.  
  
    2.  En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.  
  
    3.  En la página Administrar configuración de inicio de sesión único, en el **configuración de definición de aplicaciones de empresa** sección, haga clic en **administrar la configuración de las definiciones de aplicaciones de empresa**.  
  
    4.  En la página Administrar las definiciones de aplicación de empresa, proporcione los valores de la **nombre para mostrar**, **nombre de la aplicación**y el **póngase en contacto con la dirección de correo electrónico** campos.  
  
        > [!IMPORTANT]
        >  Para el **nombre de la aplicación** campo, asegúrese de especificar el mismo nombre de aplicación de SSO que ha especificado para la **SecondarySsoApplicationId** variable al crear el archivo de definición de aplicación, como se describe en [paso 2: crear un archivo de definición de aplicación para los artefactos de SAP](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).  
  
    5.  Deje el resto de campos como valor predeterminado y haga clic en **Aceptar**.  
  
3.  **Administrar la información de cuenta para definiciones de aplicación de empresa**. En este paso, se habilitan usuarios individuales o grupos para conectarse a una aplicación empresarial de SharePoint. Básicamente, en este paso se asigna un usuario individual o un grupo a un usuario en el sistema LOB. Especificar las credenciales para conectarse al sistema de LOB. Puede hacerlo desde la cuenta de administrar la información para la página de definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información acerca de este paso, consulte la sección "Administrar la información de cuenta para una definición de aplicación de empresa" en [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
## <a name="creating-a-shared-services-provider"></a>Crear un proveedor de servicios compartidos  
 Un proveedor de servicios compartidos es una agrupación lógica de servicios compartidos y sus recursos de soporte. Puede crear un SSP mediante la consola de Administración Central de SharePoint.  
  
 Debe definir un sitio Web al crear un SSP. Recuerde que el número de puerto y la dirección del sitio que cree. Volverá a importar la definición de aplicación de catálogo de datos profesionales a este sitio.  
  
 Para obtener más información acerca de cómo crear un SSP, vea "información general de capítulo: crear y configurar los proveedores de servicios compartidos" en [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).  
  
## <a name="importing-the-application-definition-file"></a>Importar el archivo de definición de aplicación  
 Ahora debe importar el archivo de definición de aplicación en el SSP.  
  
#### <a name="to-import-the-application-definition-file"></a>Para importar el archivo de definición de aplicación  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3.  En el **catálogo de datos profesionales** sección, haga clic en **Importar definición de la aplicación**.  
  
4.  En la página de definición de la aplicación de importación que se abre, vaya a Customer_Orders.xml, seleccione el archivo y, a continuación, haga clic en **abiertos**.  
  
5.  Haga clic en **Importar**.  
  
6.  Haga clic en **Aceptar**.  
  
     Después de importar la aplicación, puede ver la aplicación, vaya a la **ver aplicaciones** vínculo. Haga clic en el nombre de la aplicación para ver las entidades en la aplicación.  
  
## <a name="creating-web-parts"></a>Crear elementos Web  
 Ahora debe crear elementos Web en el sitio de SharePoint para ver y administrar los datos empresariales que se van a extraer desde el sistema SAP. Elementos Web son componentes reutilizables que pueden contener cualquier tipo de información basada en Web, incluidos analíticos, colaboración y obtener información de la base de datos.  
  
 En este tutorial, se crean elementos Web para el método de instancia que se crearon en el Editor de definición de catálogo de datos de Business. Office SharePoint Server proporciona diferentes tipos de elementos Web para su uso específico. Los siguientes elementos Web se usan aquí:  
  
-   **Lista de datos económicos** elemento Web para la **buscador** instancia de método. Este elemento Web le permite especificar una expresión de búsqueda para recuperar una lista de clientes desde el sistema SAP. Para este tutorial, esto se denomina el elemento Web de los clientes de búsqueda.  
  
-   **Elemento de datos económicos** elemento Web para la **método Finder específico** instancia de método. Este elemento Web muestra los detalles de un cliente específico que se selecciona en el elemento Web de los clientes de búsqueda. Este elemento Web está asignado al elemento Web de cliente de búsqueda.  Para este tutorial, esto se denomina el elemento Web detalles del cliente.  
  
-   **Lista de datos económicos relacionados** elemento Web para la **asociación** instancia de método. Este elemento Web muestra los pedidos de venta para un cliente específico que se selecciona en el elemento Web de los clientes de búsqueda. Este elemento Web está asociado con el elemento Web de cliente de búsqueda.  Para este tutorial, esto se denomina el elemento Web de Sales Order Details.  
  
 Esta sección proporciona instrucciones para crear estos elementos Web y crear asociaciones entre ellos. Para obtener más información acerca de cómo crear elementos Web, vea "Personalizar listas de datos de negocio, elementos Web y sitios" en [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).  
  
 Los elementos Web se agregará a una sola página de elemento Web. Debe crear una página de elementos Web antes de agregar los elementos Web. En este tutorial, esta página de elementos Web se denomina Customer_SalesOrders.  
  
### <a name="creating-a-web-part-page"></a>Crear una página de elementos Web  
 Esta sección proporciona instrucciones para crear una página de elementos Web.  
  
##### <a name="to-create-a-web-part-page"></a>Para crear una página de elementos Web  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3.  En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
     ![Menú para crear un elemento web](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  En la página Crear, en el **páginas Web** sección, haga clic en **página de elementos Web**.  
  
5.  En la página nuevo elemento Web, haga lo siguiente:  
  
    1.  En el **nombre** , escriba un nombre para la página. Para este tutorial, escriba el nombre como **Customer_SalesOrders**.  
  
    2.  Seleccione el **sobrescribir si ya existe el archivo** casilla de verificación si desea sobrescribir páginas anteriores con el mismo nombre que la página nueva que cree.  
  
    3.  En el **diseño** sección, desde el **elegir una plantilla de diseño** , seleccione un diseño para la página de elementos Web. Para este tutorial, seleccione **encabezado, columna izquierda, cuerpo**.  
  
    4.  En el **ubicación de almacenamiento** sección, en la **biblioteca de documentos** lista, haga clic en **plantillas de formulario**.  
  
    5.  Haga clic en **Crear**. La siguiente ilustración muestra una página de elementos Web después de se acaba de crear.  
  
         ![Página de elementos Web vacía](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")  
  
    6.  Ahora debe agregar las distintas partes Web a esta página.  
  
### <a name="adding-a-business-data-list-web-part"></a>Agregar un elemento Web de lista de datos de negocio  
 Ahora debe agregar un elemento Web de lista de datos de negocio a la página de elementos Web. Con este elemento Web recuperará una lista de clientes desde el sistema SAP que coincide con una expresión de búsqueda. Este elemento Web corresponde a la **buscador** instancia de método (*GetCustomerByName_Instance*) que creó en el Editor de definición de catálogo de datos de Business.  
  
##### <a name="to-add-a-business-data-list-web-part"></a>Para agregar un elemento Web de lista de datos de negocio  
  
1.  En la página Customer_SalesOrders, en la **encabezado** sección, haga clic en **agregar un elemento Web**.  
  
2.  En el **agregar elementos Web** cuadro de diálogo, en la **datos económicos** sección, seleccione la **lista de datos económicos** casilla de verificación y, a continuación, haga clic en **agregar**.  
  
     ![Opciones para crear un elemento Web de datos empresariales](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  En la parte de Web de recién agregado Business datos de lista, haga clic en el **abrir el panel de herramientas** vínculo.  
  
     ![Abra el panel de herramientas para el elemento Web](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  El panel de herramientas de la lista de datos económicos se abre en el panel derecho. En el **lista de datos económicos** sección, para la **tipo** , a continuación, haga clic en el **examinar** botón.  
  
     ![Panel de herramientas de lista de datos de negocio](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")  
  
5.  En el **selector de tipo de datos profesionales** cuadro de diálogo, seleccione la **Customer_Order_Instance** aplicación y, a continuación, haga clic en **Aceptar**.  
  
     ![Seleccione la instancia de aplicación](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")  
  
6.  Expanda el **apariencia** nodo y en el **título** , escriba un título para el elemento Web. Para este elemento Web, escriba **lista de clientes**.  
  
7.  En el panel de herramientas de la lista de datos económicos, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**. El elemento Web de lista de datos de negocio ahora el siguiente aspecto:  
  
     ![Elemento Web de lista de datos económicos](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")  
  
8.  El elemento Web se enumeran los campos que se devuelven mediante la ejecución de la solicitud de cambio de SD_RFC_CUSTOMER_GET. Puede quitar los campos que no desea que aparezca en el portal de SharePoint. Para quitar los campos, haga clic en el **Editar vista** situado en la esquina superior derecha del elemento Web.  
  
9. En la página Editar vista, en la sección de columnas, desactive las casillas de las columnas que no desea que aparezca.  
  
     ![Ver columnas específicas en SharePoint](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")  
  
10. Haga clic en **Aceptar**.  
  
### <a name="adding-a-business-data-item-web-part"></a>Agregar un elemento Web del elemento datos empresariales  
 Ahora debe agregar un elemento Web del elemento datos empresariales en la página de elementos Web. También se conectará este elemento Web para el elemento Web de lista de datos empresariales que acaba de crear. Al hacerlo, podrá ver los detalles de un cliente que seleccionó en el elemento Web de lista de datos de negocio. Este elemento Web corresponde a la **método Finder específico** instancia de método (*GetCustomerByNumber_Instance*) que creó en el Editor de definición de catálogo de datos de Business.  
  
##### <a name="to-add-a-business-data-item-web-part"></a>Para agregar un elemento Web del elemento datos empresariales  
  
1.  En la página Customer_SalesOrders, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **Editar página**.  
  
2.  En la página Customer_SalesOrders, en la **columna izquierda** sección, haga clic en **agregar un elemento Web**.  
  
3.  En el **agregar elementos Web** cuadro de diálogo la **datos económicos** sección, seleccione la **elemento de datos económicos** casilla de verificación y, a continuación, haga clic en **agregar**.  
  
4.  En el recién agregado Business datos elemento Web, haga clic en el **abrir el panel de herramientas** vínculo.  
  
5.  Se abre el panel de herramientas del elemento de datos profesionales en el panel derecho. En el **elemento de datos económicos** sección, para la **tipo** , a continuación, haga clic en el **examinar** botón.  
  
     ![Panel de herramientas del elemento de datos de negocio](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")  
  
6.  En el **selector de tipo de datos profesionales** cuadro de diálogo, seleccione la **Customer_Order_Instance** aplicación y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **vista** lista, seleccione **predeterminado**.  
  
8.  Deje el **elemento** lista vacía.  
  
    > [!NOTE]
    >  Para el **elemento** campo, debe especificar un nombre de cliente o el número de cliente para el que desea ver los detalles. Que actúa como un parámetro de entrada para este elemento Web. Dado que se está recibiendo el parámetro de entrada mediante la conexión para el elemento Web de lista de datos de negocio, no es necesario especificar un elemento explícitamente.  
  
9. En el **campos** sección, haga clic en **elegir** para seleccionar los campos que desea mostrar en la página.  
  
10. Expanda el **apariencia** nodo y en el **título** , especifique un título para el elemento Web. Para este elemento Web, especifique **detalles para un cliente específico**.  
  
11. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
12. Conectar el elemento Web a la **lista de clientes** elemento Web. Para ello:  
  
    1.  Haga clic en **editar** hacia la esquina superior derecha del elemento Web.  
  
    2.  En el menú contextual seleccione **conexiones**, seleccione **obtener elemento de**y haga clic en **lista de clientes**.  
  
         ![Conectar dos elementos Web](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")  
  
### <a name="adding-a-business-data-related-list-web-part"></a>Agregar datos de un negocio relacionados con el elemento Web de lista  
 Ahora debe agregar un elemento de Web de lista relacionados de negocio datos a la página de elementos Web. También se conectará este elemento Web para el elemento de lista de datos del negocio Web que creó anteriormente. Al hacerlo, podrá ver los pedidos de venta para un cliente que seleccionó en el elemento Web de lista de datos de negocio. Este elemento Web corresponde a la **asociación** instancia de método (*SalesOrderForCustomer_Instance*) que creó en el Editor de definición de catálogo de datos de Business.  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a>Para agregar los datos empresariales relacionados con elementos Web de lista  
  
1.  En la página Customer_SalesOrders, en la **cuerpo** sección, haga clic en **agregar un elemento Web**.  
  
2.  En el **agregar elementos Web** cuadro de diálogo la **datos económicos** sección, seleccione la **lista relacionados de datos económicos** casilla de verificación y haga clic en **agregar**.  
  
3.  En el recién agregado Business datos relacionados elemento Web de lista, haga clic en el **abrir el panel de herramientas** vínculo.  
  
4.  Se abre el panel de herramientas de la lista de datos económicos relacionados en el panel derecho. En el **lista relacionados de datos económicos** sección, para la **tipo** , a continuación, haga clic en el **examinar** botón.  
  
     ![Datos económicos relacionados con la lista](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")  
  
5.  En el **selector de tipo de datos profesionales** cuadro de diálogo, seleccione la **Customer_Order_Instance** aplicación y, a continuación, haga clic en **Aceptar**. El **relación** lista se rellena con el nombre de la **asociación** instancia de método (*SalesOrderForCustomer_Instance*).  
  
6.  Expanda el **apariencia** nodo y en el **título** , escriba un título para el elemento Web. Para este elemento Web, escriba **pedido de venta para un cliente específico**.  
  
7.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
8.  El elemento Web se enumeran los campos que se devuelven mediante la ejecución de la solicitud de cambio de BAPI_SALESORDER_GETLIST. Puede quitar los campos que no desea que aparezca en el portal de SharePoint. Para quitar los campos, haga clic en el **Editar vista** situado en la esquina superior derecha del elemento Web.  
  
9. En la página Editar vista, en la **columnas** sección, desactive los cuadros de texto en las columnas que no desea que aparezca.  
  
10. Haga clic en **Aceptar**.  
  
11. Conectar el elemento Web a la **lista de clientes** elemento Web. Para ello:  
  
    1.  Haga clic en **editar** hacia la esquina superior derecha de la **pedido de venta para un cliente específico** elemento Web.  
  
    2.  En el menú contextual, seleccione **conexiones**, seleccione **obtener elemento relacionado de**y, a continuación, haga clic en **lista de clientes**.  
  
12. Haga clic en **salir del modo de edición** desde la esquina superior derecha de la página.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Probar la aplicación de SharePoint mediante la recuperación de datos desde un sistema SAP. Vea [paso 4: probar la aplicación de SharePoint](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)