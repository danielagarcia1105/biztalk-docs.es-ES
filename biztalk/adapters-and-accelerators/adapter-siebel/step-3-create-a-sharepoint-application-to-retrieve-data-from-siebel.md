---
title: 'Paso 3: Crear una aplicación de SharePoint para recuperar datos de Siebel | Microsoft Docs'
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
ms.openlocfilehash: df6c92b371291f4359c4bbce5e16529700bcc0c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971869"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a>Paso 3: Crear una aplicación de SharePoint para recuperar datos de Siebel
![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 15 minutos.  
  
 **Objetivo:** ahora debe tomar el archivo de definición de aplicación que ha creado mediante el Editor de definición del catálogo de datos profesionales e importarlo en Office SharePoint Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Que debería haber creado un archivo de definición de aplicación, como se describe en [paso 2: crear un archivo de definición de aplicación para operaciones de componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).  
  
-   Debe ejecutar el servicio Microsoft Single Sign-on.  
  
## <a name="how-to-create-a-sharepoint-application"></a>Cómo crear una aplicación de SharePoint  
 Creación de una aplicación de SharePoint implica los pasos siguientes:  
  
-   Crear una aplicación de inicio de sesión único (SSO) en SharePoint  
  
-   Crear un proveedor de servicios compartidos (SSP)  
  
-   Importe el archivo de definición de aplicación  
  
-   Crear una página de elementos Web y agregar elementos Web  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>Creación de una aplicación de inicio de sesión único en SharePoint  
 Para obtener acceso a los datos en un sistema Siebel desde una aplicación de SharePoint, debe configurar una aplicación de inicio de sesión único que asigna un usuario de SharePoint a un usuario de Siebel. Creación de una aplicación de inicio de sesión único en SharePoint implica los pasos siguientes:  
  
1.  **Administrar la configuración de servidor de inicio de sesión único**. En este paso, especifique una cuenta de usuario que puede administrar y configurar el servicio de inicio de sesión único. Puede hacerlo desde la página Administrar configuración del servidor. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información sobre este paso, consulte la sección "Configure Single Sign-On for Office SharePoint Server 2007" en [ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
2.  **Administrar la configuración de las definiciones de aplicaciones de empresa**. En este paso, configure la configuración de la definición de aplicación empresarial. Puede hacerlo desde la página Administrar configuración de definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint.  
  
    1.  En Administración Central, en la barra de navegación superior, haga clic en **operaciones**.  
  
    2.  En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.  
  
    3.  En la página Administrar configuración de inicio de sesión único, en el **definición de configuración de aplicaciones de empresa** sección, haga clic en **administrar la configuración de las definiciones de aplicaciones de empresa**.  
  
    4.  En la página Administrar definiciones de aplicaciones de empresa, proporcione los valores de la **nombre para mostrar**, **nombre de la aplicación**y el **dirección de correo electrónico de contacto** campos.  
  
        > [!IMPORTANT]
        >  Para el **nombre de la aplicación** campo, asegúrese de especificar el mismo nombre de aplicación de SSO que ha especificado para el **SecondarySsoApplicationId** variable al crear el archivo de definición de aplicación, como se describe en [paso 2: crear un archivo de definición de aplicación para operaciones de componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).  
  
    5.  Deje los demás campos como valor predeterminado y haga clic en **Aceptar**.  
  
3.  **Administrar la información de cuenta para definiciones de aplicación de empresa**. En este paso, se permiten usuarios individuales o grupos para conectarse a una aplicación empresarial de SharePoint. Básicamente, en este paso asignan un usuario individual o un grupo a un usuario en el sistema de LOB. También especifica las credenciales para conectarse al sistema de LOB. Puede hacerlo de administrar la información de cuenta para la página definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información sobre este paso, consulte la sección "Administrar la información de cuenta para una definición de aplicación empresarial" en [ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
## <a name="creating-a-shared-services-provider"></a>Creación de un proveedor de servicios compartidos  
 Un SSP es una agrupación lógica de servicios compartidos y sus recursos de apoyo. Puede crear un SSP mediante la consola de Administración Central de SharePoint.  
  
 Debe definir un sitio Web durante la creación de un SSP. Recuerde que el número de puerto y la dirección del sitio que cree. Importará la definición de aplicación de catálogo de datos profesionales a este sitio.  
  
 Para obtener más información sobre la creación de un SSP, consulte "información general del capítulo: crear y configurar los proveedores de servicios compartidos" en [ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119).  
  
## <a name="importing-the-application-definition-file"></a>Importar el archivo de definición de aplicación  
 Ahora, debe importar el archivo de definición de aplicación en el SSP.  
  
#### <a name="to-import-the-application-definition-file"></a>Para importar el archivo de definición de aplicación  
  
1. Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.  
  
2. En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3. En el **Business Data Catalog** sección, haga clic en **Importar definición de aplicación**.  
  
4. En la página de definición de aplicación de importación que se abre, vaya a Siebel_Account.xml, seleccione el archivo y, a continuación, haga clic en **abierto**.  
  
5. Haga clic en **Importar**.  
  
6. Haga clic en **Aceptar**.  
  
   Después de importar la aplicación, puede ver la aplicación, vaya a la **ver aplicaciones** vínculo. Haga clic en el nombre de la aplicación para ver las entidades de la aplicación.  
  
## <a name="creating-web-parts"></a>Crear elementos Web  
 Ahora debe crear elementos Web en el sitio de SharePoint para ver y administrar los datos empresariales que se va a extraer en el sistema Siebel. Elementos Web son componentes reutilizables que pueden contener cualquier tipo de información basada en Web, incluido el análisis, colaboración e información de la base de datos.  
  
 En este tutorial, se crean elementos Web para el método de instancia que se crearon en Business Data Catalog Definition Editor. Office SharePoint Server proporciona diferentes tipos de elementos Web para uso específico. Para la instancia de método de buscador, usaremos el **lista de datos económicos** elemento Web. Este elemento Web le permite especificar una expresión de búsqueda para realizar una consulta en el componente de negocio de la cuenta. Para este tutorial, llamamos a esto la **consultar cuentas** elemento Web.  
  
 Esta sección proporciona instrucciones para crear estos elementos Web. Para obtener más información acerca de cómo crear elementos Web, consulte el documento de Microsoft Office SharePoint Server 2007 ("Personalizar listas de datos de negocio, elementos Web y sitios") en [ http://go.microsoft.com/fwlink/?LinkId=104131 ](http://go.microsoft.com/fwlink/?LinkId=104131).  
  
 Los elementos Web se agregará a una sola página de elemento Web. Debe crear una página de elementos Web antes de agregar los elementos Web. Para este tutorial, se llama a la página de elementos Web **Siebel cuenta**.  
  
### <a name="creating-a-web-part-page"></a>Creación de una página de elementos Web  
 Esta sección proporciona instrucciones para crear una página de elementos Web.  
  
##### <a name="to-create-a-web-part-page"></a>Para crear una página de elementos web  
  
1. Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Office Server**y haga clic en **SharePoint 3.0 Central Administration**.  
  
2. En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3. En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
    ![Menú para crear un elemento web](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4. En la página Crear, en el **páginas Web** sección, haga clic en **página de elementos Web**.  
  
5. En la página nuevo elemento Web, haga lo siguiente:  
  
   1. En el **nombre** , especifique un nombre para la página. Para este tutorial, especifique el nombre como `Siebel Account`.  
  
   2. Seleccione el **sobrescribir si ya existe el archivo** casilla de verificación si desea sobrescribir páginas antiguas con el mismo nombre que la página que cree.  
  
   3. En el **diseño** sección, desde el **elegir una plantilla de diseño** , seleccione un diseño para la página de elementos Web. Para este tutorial, seleccione **página completa, Vertical**.  
  
   4. En **la ubicación de almacenamiento** sección la **biblioteca de documentos** lista, seleccione **las plantillas de formulario**.  
  
   5. Haga clic en **Crear**. La siguiente ilustración muestra una página de elementos Web después de se acaba de crear.  
  
       ![Página de elementos Web vacía](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")  
  
      Ahora debe agregar las distintas partes Web a esta página.  
  
### <a name="adding-a-business-data-list-web-part"></a>Agregar un elemento Web de lista de datos de negocio  
 Ahora debe agregar un elemento de Web de lista de datos de negocio a la página de elementos Web. Con este elemento Web, consultará el componente de negocio de la cuenta con una expresión de búsqueda. Este elemento Web corresponde a la instancia de método de buscador (QueryAccount) que creó en el Editor de definición de catálogo de datos de Business.  
  
##### <a name="to-add-a-business-data-list-web-part"></a>Para agregar un elemento Web de lista de datos de Business  
  
1.  En el **Siebel cuenta** página, en el **encabezado** sección, haga clic en **agregar un elemento Web**.  
  
2.  En el **agregar elementos Web** cuadro de diálogo el **datos empresariales** sección, seleccione el **lista de datos económicos** casilla de verificación y, a continuación, haga clic en **agregar**.  
  
     ![Opciones para crear un elemento Web de datos empresariales](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  En la recién agregada Business elemento lista de datos Web, haga clic en el **abrir el panel de herramientas** vínculo.  
  
     ![Abra el panel de herramientas para el elemento Web](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  Se abre el panel de herramientas de la lista de datos económicos en el panel derecho. En el **lista de datos económicos** sección, para el **tipo** , a continuación, haga clic en el **examinar** botón.  
  
     ![Panel de herramientas de lista de datos de negocio](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")  
  
5.  En el **selector de tipos de datos de negocio** cuadro de diálogo, seleccione el **Siebel_Account_Instance** aplicación y, a continuación, haga clic en **Aceptar**.  
  
     ![Seleccione la instancia de aplicación](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")  
  
6.  Expanda el **apariencia** nodo y en el **título** , especifique un título para el elemento Web. Para este elemento Web, especifique **Account List**.  
  
7.  En el panel de herramientas de la lista de datos económicos, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**. El elemento Web de lista de datos de negocio ahora el siguiente aspecto:  
  
     ![Elemento Web de lista de datos económicos](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")  
  
    > [!NOTE]
    >  También puede cambiar el orden en que aparecen las columnas de parámetro. Puede hacerlo haciendo clic en el **Editar vista** vínculo hacia la esquina derecha del elemento Web.  
  
8.  Haga clic en **salir del modo de edición** desde la esquina superior derecha de la página.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Probar la aplicación de SharePoint mediante la recuperación de datos desde un sistema Siebel. Consulte [paso 4: probar la aplicación SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentación de datos de un sistema de Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)