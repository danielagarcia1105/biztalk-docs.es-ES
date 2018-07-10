---
title: 'Paso 4: Crear una aplicación de Sharepoint para tener acceso al adaptador | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15da47a4171d6bdf4f3b53e2208851bd15ecb0d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986645"
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a>Paso 4: Crear una aplicación de Sharepoint para tener acceso al adaptador
![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 En este paso se tome el archivo de definición de aplicación creados mediante la herramienta Editor de definición de catálogo de datos profesionales e importarlo en Microsoft Office SharePoint Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Se debe haber creado un archivo de aplicación como se describe en [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).  
  
-   El servicio Microsoft Single Sign-On debe estar ejecutándose.  
  
## <a name="how-to-create-a-sharepoint-application"></a>Cómo crear una aplicación de SharePoint  
 Creación de una aplicación de SharePoint implica los pasos siguientes:  
  
- Cree una aplicación de inicio de sesión único (SSO) en SharePoint.  
  
- Crear un proveedor de servicios compartidos e importar el archivo de definición de aplicación.  
  
- Cree una página de elementos Web y agregar elementos Web.  
  
  En este tema se muestra cómo realizar estos pasos.  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>Creación de una aplicación de inicio de sesión único en SharePoint  
 Para pasar las credenciales de usuario para el adaptador de Echo desde una aplicación de SharePoint, debe configurar una aplicación de inicio de sesión único que se asigna a una cuenta de usuario o grupo.  
  
#### <a name="manage-server-settings-for-single-sign-on"></a>Administrar la configuración de servidor para el inicio de sesión único  
  
1.  Inicie Administración Central de SharePoint 3.0. En el **iniciar** menú, elija **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.  
  
2.  En la barra de navegación superior, haga clic en **operaciones**.  
  
3.  En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.  
  
4.  En la página Administrar configuración de inicio de sesión único, en el **configuración del servidor** sección, haga clic en **Administrar configuración del servidor**.  
  
5.  Asegúrese de que la información de esta página es correcta para la instalación de inicio de sesión único. Para obtener más información acerca de estas operaciones, vea "Configurar el inicio de sesión único (Office SharePoint Server)" en [ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a>Administrar la configuración de las definiciones de aplicaciones de empresa  
  
1.  En Administración Central de SharePoint, en la barra de navegación superior, haga clic en **operaciones**.  
  
2.  En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.  
  
3.  En la página Administrar configuración de inicio de sesión único, en el **definición de configuración de aplicaciones de empresa** sección, haga clic en **administrar la configuración de las definiciones de aplicaciones de empresa**.  
  
4.  En la página Administrar definiciones de aplicaciones de empresa, haga clic en **nuevo elemento**.  
  
5.  En la creación de Enterprise aplicación las definiciones de página, establezca el **nombre para mostrar** campo **EchoSSO**y, a continuación, establezca el **nombre de la aplicación** campo  **EchoSSO**. Este valor debe coincidir con el que especificó en SecondarySsoApplicationId [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).  
  
6.  En el **dirección de correo electrónico de contacto** campo, escriba su dirección de correo electrónico y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a>Administrar la información de cuenta para definiciones de aplicación de empresa  
  
1.  En Administración Central de SharePoint, en la barra de navegación superior, haga clic en **operaciones**.  
  
2.  En la página operaciones, en la **sección de configuración de seguridad**, haga clic en **administrar la configuración de inicio de sesión único**.  
  
3.  En la página Administrar configuración de inicio de sesión único, en el **definición de configuración de aplicaciones de empresa** sección, haga clic en **administrar información de cuenta para empresa las definiciones de aplicación**.  
  
4.  En la información de cuenta de administración para una definición de aplicación empresarial, seleccione **EchoSSO** desde el **definición de aplicación empresarial** lista.  
  
5.  En el **nombre de la cuenta de grupo** , escriba el grupo de Windows que se usará para proteger esta definición de aplicación. Por ejemplo, **decir a los usuarios**.  
  
6.  Haga clic en **Conjunto**.  
  
7.  En la página de información de la cuenta de EchoSSO proporcionan, en la **Username** tipo de campo **testuser**y, a continuación, en el **contraseña** tipo de campo **testpassword**.  
  
8.  Haga clic en **Aceptar**y, a continuación, haga clic en **realiza**.  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a>Crear un proveedor de servicios compartidos e importar el archivo de definición de aplicación  
 Un proveedor de servicios compartidos (SSP) es una agrupación lógica de servicios compartidos y sus recursos de apoyo. Puede crear un SSP mediante la consola de Administración Central de SharePoint. Este ejemplo funciona en cualquier SSP. Para obtener más información sobre la creación de un SSP, consulte "información general del capítulo: crear y configurar proveedores de servicios compartidos" en [ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119).  
  
### <a name="to-import-the-application-definition-file"></a>Para importar el archivo de definición de aplicación  
  
1.  Inicie Administración Central de SharePoint 3.0. En el **iniciar** menú, elija **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3.  En el **Business Data Catalog** sección, haga clic en **Importar definición de aplicación**.  
  
4.  En la página definición de aplicación de importación, haga clic en **examinar**y, a continuación, seleccione el archivo EchoWS.xml.  
  
5.  Haga clic en **importación**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="creating-web-parts"></a>Crear elementos Web  
 Ahora debe crear elementos Web en el sitio de SharePoint para usar la instancia de método creada en el Editor de definición de catálogo de datos de Business. Elementos Web son componentes reutilizables que pueden contener cualquier tipo de información basada en Web, incluido el análisis, colaboración e información de la base de datos.  
  
#### <a name="to-create-a-web-part-page"></a>Para crear una página de elementos Web  
  
1.  Inicie Administración Central de SharePoint 3.0. En el **iniciar** menú, elija **todos los programas**, apunte a **Microsoft Office Server**y, a continuación, haga clic en **SharePoint 3.0 Central Administration**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre de SSP en el que ha importado el archivo de definición de aplicación.  
  
3.  En la página de administración de servicios compartidos, en la esquina superior derecha, haga clic en **acciones del sitio**y, a continuación, haga clic en **crear**.  
  
     ![Crear acciones del sitio](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")  
  
4.  En el **crear** página, en el **páginas Web** sección, haga clic en **página de elementos Web**.  
  
5.  En la página nuevo elemento Web, en el **nombre** , escriba **EchoPart**y, a continuación, seleccione **página completa, Vertical** desde el **ha elegido una plantilla de diseño**lista.  
  
6.  Haga clic en **Crear**.  
  
#### <a name="to-add-a-business-data-web-part"></a>Para agregar un elemento Web de datos de empresa  
  
1.  Haga clic en **Agregar elemento web**.  
  
2.  En el **agregar elementos Web** cuadro de diálogo, seleccione **lista de datos económicos**y, a continuación, haga clic en **agregar**.  
  
     ![Lista de datos económicos](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")  
  
3.  Haga clic en **abrir el panel de herramientas**.  
  
4.  Se abre el panel de herramientas de la lista de datos económicos en el panel derecho. En el **lista de datos económicos** sección, para el **tipo** , a continuación, haga clic en el **examinar** botón.  
  
     ![Seleccione el tipo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")  
  
5.  En el **selector de tipos de datos de negocio** cuadro de diálogo, seleccione el **EchoWSLob_Instance** aplicación y, a continuación, haga clic en **Aceptar**.  
  
6.  En el panel de herramientas de la lista de datos económicos, haga clic en **Aceptar**.  
  
7.  Se presentan con un campo que le permite escribir un valor de saludo para pasar al método EchoGreetings. Escribir datos en el campo de saludo y haga clic en **recuperar datos**. Esto invoca el método EchoGreetings del adaptador de Echo alojado en IIS y devuelve una respuesta.  
  
     ![Lista EchoGreetings](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")  
  
    > [!NOTE]
    >  La columna de nombre no contiene la información de usuario, pero solo muestra BDC. Nombre. Esto ocurre porque el BDC espera sólo una estructura de registro simple y no muestra la estructura compleja representada por el campo de nombre.  
  
8.  Haga clic en **salir del modo de edición** desde la esquina superior de la página.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 Ha usado la Administración Central de SharePoint 3.0 para importar una definición de aplicación y crear elementos Web que utilizan esta definición para invocar la operación EchoGreetings del adaptador de Echo.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Este tutorial está completa. Para obtener más información con el catálogo de datos empresariales, vea "Catálogo de datos empresariales" en [ http://go.microsoft.com/fwlink/?LinkId=119921 ](http://go.microsoft.com/fwlink/?LinkId=119921).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Hospedar el adaptador de Echo en IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)