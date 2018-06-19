---
title: 'Paso 3: Crear una aplicación de SharePoint para recuperar datos de Siebel | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86bde531-2daf-452b-b3e6-5481d66f72e7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94537b57a731e5d71459518fcbb0a528b6240d19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225972"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a>Paso 3: Crear una aplicación de SharePoint para recuperar datos de Siebel
![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 15 minutos.  
  
 **Objetivo:** ahora debe dejar el archivo de definición de aplicación creados mediante el Editor de definición del catálogo de datos profesionales e importarla en Office SharePoint Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Deberá haber creado un archivo de definición de aplicación, como se describe en [paso 2: crear un archivo de definición de aplicación para operaciones de componente de negocio de Siebel](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).  
  
-   Debe ejecutar el servicio Microsoft Single Sign-on.  
  
## <a name="how-to-create-a-sharepoint-application"></a>Cómo crear una aplicación de SharePoint  
 Crear una aplicación de SharePoint implica los pasos siguientes:  
  
-   Crear una aplicación de inicio de sesión único (SSO) en SharePoint  
  
-   Crear un proveedor de servicios compartidos (SSP)  
  
-   Importe el archivo de definición de aplicación  
  
-   Crear una página de elementos Web y agregar elementos Web  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>Crear una aplicación de SSO en SharePoint  
 Para obtener acceso a los datos en un sistema Siebel desde una aplicación de SharePoint, debe configurar una aplicación de SSO que se asigna un usuario de SharePoint a un usuario de Siebel. Crear una aplicación de SSO en SharePoint implica los pasos siguientes:  
  
1.  **Administrar la configuración de servidor de inicio de sesión único**. En este paso, especifique una cuenta de usuario que puede administrar y configurar el servicio de inicio de sesión único. Puede hacerlo desde la página Administrar configuración de servidor. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información acerca de este paso, consulte la sección "Configurar inicio de sesión único para Office SharePoint Server 2007" en [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
2.  **Administrar la configuración de las definiciones de aplicaciones de empresa**. En este paso, configurará la configuración de la definición de aplicación empresarial. Puede hacerlo desde la página Administrar configuración de definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint.  
  
    1.  En Administración Central, en la barra de navegación superior, haga clic en **Operations**.  
  
    2.  En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.  
  
    3.  En la página Administrar configuración de inicio de sesión único, en el **configuración de definición de aplicaciones de empresa** sección, haga clic en **administrar la configuración de las definiciones de aplicaciones de empresa**.  
  
    4.  En la página Administrar las definiciones de aplicación de empresa, proporcione los valores de la **nombre para mostrar**, **nombre de la aplicación**y el **póngase en contacto con la dirección de correo electrónico** campos.  
  
        > [!IMPORTANT]
        >  Para el **nombre de la aplicación** campo, asegúrese de especificar el mismo nombre de aplicación de SSO que ha especificado para la **SecondarySsoApplicationId** variable al crear el archivo de definición de aplicación, como se describe en [paso 2: crear un archivo de definición de aplicación para operaciones de componente de negocio de Siebel](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).  
  
    5.  Deje el resto de campos como valor predeterminado y haga clic en **Aceptar**.  
  
3.  **Administrar la información de cuenta para definiciones de aplicación de empresa**. En este paso, se habilitan usuarios individuales o grupos para conectarse a una aplicación empresarial de SharePoint. Básicamente, en este paso se asigna un usuario individual o un grupo a un usuario en el sistema LOB. Especificar las credenciales para conectarse al sistema de LOB. Puede hacerlo de administrar la información de cuenta para la página de definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información acerca de este paso, consulte la sección "Administrar la información de cuenta para una definición de aplicación de empresa" en [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
## <a name="creating-a-shared-services-provider"></a>Crear un proveedor de servicios compartidos  
 Un SSP es una agrupación lógica de servicios compartidos y sus recursos de soporte. Puede crear un SSP mediante la consola de Administración Central de SharePoint.  
  
 Debe definir un sitio Web al crear un SSP. Recuerde que el número de puerto y la dirección del sitio que cree. Volverá a importar la definición de aplicación de catálogo de datos profesionales a este sitio.  
  
 Para obtener más información acerca de cómo crear un SSP, vea "información general de capítulo: crear y configurar los proveedores de servicios compartidos" en [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).  
  
## <a name="importing-the-application-definition-file"></a>Importar el archivo de definición de aplicación  
 Ahora debe importar el archivo de definición de aplicación en el SSP.  
  
#### <a name="to-import-the-application-definition-file"></a>Para importar el archivo de definición de aplicación  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3.  En el **catálogo de datos profesionales** sección, haga clic en **Importar definición de la aplicación**.  
  
4.  En la página de definición de la aplicación de importación que se abre, vaya a Siebel_Account.xml, seleccione el archivo y, a continuación, haga clic en **abiertos**.  
  
5.  Haga clic en **Importar**.  
  
6.  Haga clic en **Aceptar**.  
  
 Después de importar la aplicación, puede ver la aplicación, vaya a la **ver aplicaciones** vínculo. Haga clic en el nombre de la aplicación para ver las entidades en la aplicación.  
  
## <a name="creating-web-parts"></a>Crear elementos Web  
 Ahora debe crear elementos Web en el sitio de SharePoint para ver y administrar los datos empresariales que se van a extraer en el sistema Siebel. Elementos Web son componentes reutilizables que pueden contener cualquier tipo de información basada en Web, incluidos analíticos, colaboración y obtener información de la base de datos.  
  
 En este tutorial, se crean elementos Web para el método de instancia que se crearon en Business Data Catalog Definition Editor. Office SharePoint Server proporciona diferentes tipos de elementos Web para su uso específico. Para la instancia de método de buscador, usaremos el **lista de datos económicos** elemento Web. Este elemento Web le permite especificar una expresión de búsqueda para realizar una consulta en el componente de negocio de la cuenta. Para este tutorial, esto se llama el **consultar las cuentas** elemento Web.  
  
 Esta sección proporciona instrucciones para crear estos elementos Web. Para obtener más información acerca de cómo crear elementos Web, consulte el documento de Microsoft Office SharePoint Server 2007 ("Personalizar listas de datos de negocio, elementos Web y sitios") en [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).  
  
 Los elementos Web se agregará a una sola página de elemento Web. Debe crear una página de elementos Web antes de agregar los elementos Web. Para este tutorial, la página de elemento Web se denomina **cuenta de Siebel**.  
  
### <a name="creating-a-web-part-page"></a>Crear una página de elementos Web  
 Esta sección proporciona instrucciones para crear una página de elementos Web.  
  
##### <a name="to-create-a-web-part-page"></a>Para crear una página de elementos web  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3.  En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
     ![Menú para crear un elemento web](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  En la página Crear, en el **páginas Web** sección, haga clic en **página de elementos Web**.  
  
5.  En la página nuevo elemento Web, haga lo siguiente:  
  
    1.  En el **nombre** , a continuación, especifique un nombre para la página. Para este tutorial, especifique el nombre como `Siebel Account`.  
  
    2.  Seleccione el **sobrescribir si ya existe el archivo** casilla de verificación si desea sobrescribir páginas anteriores con el mismo nombre que la página que cree.  
  
    3.  En el **diseño** sección, desde el **elegir una plantilla de diseño** , seleccione un diseño para la página de elementos Web. Para este tutorial, seleccione **página completa, Vertical**.  
  
    4.  En **la ubicación de almacenamiento** sección, en la **biblioteca de documentos** lista, seleccione **plantillas de formulario**.  
  
    5.  Haga clic en **Crear**. La siguiente ilustración muestra una página de elementos Web después de se acaba de crear.  
  
         ![Página de elementos Web vacía](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")  
  
     Ahora debe agregar las distintas partes Web a esta página.  
  
### <a name="adding-a-business-data-list-web-part"></a>Agregar un elemento Web de lista de datos de negocio  
 Ahora debe agregar un elemento Web de lista de datos de negocio a la página de elementos Web. Con este elemento Web, consultará el componente de negocio de la cuenta con una expresión de búsqueda. Este elemento Web corresponde a la instancia de método de buscador (QueryAccount) que creó en el Editor de definición de catálogo de datos de Business.  
  
##### <a name="to-add-a-business-data-list-web-part"></a>Para agregar un elemento Web de lista de datos de negocio  
  
1.  En el **cuenta de Siebel** página, en la **encabezado** sección, haga clic en **agregar un elemento Web**.  
  
2.  En el **agregar elementos Web** cuadro de diálogo, en la **datos económicos** sección, seleccione la **lista de datos económicos** casilla de verificación y, a continuación, haga clic en **agregar**.  
  
     ![Opciones para crear un elemento Web de datos empresariales](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  En la parte de Web de recién agregado Business datos de lista, haga clic en el **abrir el panel de herramientas** vínculo.  
  
     ![Abra el panel de herramientas para el elemento Web](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  El panel de herramientas de la lista de datos económicos se abre en el panel derecho. En el **lista de datos económicos** sección, para la **tipo** , a continuación, haga clic en el **examinar** botón.  
  
     ![Panel de herramientas de lista de datos de negocio](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")  
  
5.  En el **selector de tipo de datos profesionales** cuadro de diálogo, seleccione la **Siebel_Account_Instance** aplicación y, a continuación, haga clic en **Aceptar**.  
  
     ![Seleccione la instancia de aplicación](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")  
  
6.  Expanda el **apariencia** nodo y en el **título** , especifique un título para el elemento Web. Para este elemento Web, especifique **lista de cuentas de**.  
  
7.  En el panel de herramientas de la lista de datos económicos, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**. El elemento Web de lista de datos de negocio ahora el siguiente aspecto:  
  
     ![Elemento Web de lista de datos económicos](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")  
  
    > [!NOTE]
    >  También puede cambiar el orden en que aparecen las columnas de parámetro. Puede hacerlo haciendo clic en el **Editar vista** vínculo hacia la esquina derecha del elemento Web.  
  
8.  Haga clic en **salir del modo de edición** desde la esquina superior derecha de la página.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Probar la aplicación de SharePoint mediante la recuperación de datos desde un sistema Siebel. Vea [paso 4: probar la aplicación de SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentar datos desde un sistema Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)