---
title: 'Paso 3: Crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaa16011-9284-4ccf-8132-9c1e14cc6aa7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe9d6fc34fa039bb4b3861deb35fb51524180ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217204"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-e-business-suite"></a>Paso 3: Crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite
![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** ahora debe importar el archivo de definición de aplicación de Microsoft Office SharePoint Server y configurar una aplicación para recuperar datos de Oracle E-Business Suite.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Deberá haber creado un archivo de definición de aplicación tal como se describe en [paso 2: crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).  
  
-   Debe ejecutar el servicio Microsoft Single Sign-on.  
  
 
  
##  <a name="SSO"></a>Crear una aplicación de SSO en SharePoint  
 Para obtener acceso a los datos de Oracle E-Business Suite desde una aplicación de SharePoint, debe configurar una aplicación de SSO que se asigna un usuario de SharePoint a un usuario de Oracle E-Business Suite. Crear una aplicación de SSO en SharePoint implica los pasos siguientes:  
  
1.  **Administrar la configuración de servidor de inicio de sesión único**. En este paso, especifique una cuenta de usuario que puede administrar y configurar el servicio de inicio de sesión único. Puede hacerlo en la página Administrar configuración de servidor. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información acerca de este paso, consulte la sección "Configurar inicio de sesión único para Office SharePoint Server 2007" en [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
2.  **Administrar la configuración de las definiciones de aplicaciones de empresa**. En este paso, configurará la configuración de la definición de aplicación empresarial. Puede hacerlo desde la página Administrar configuración de definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint.  
  
    1.  En Administración Central, en la barra de navegación superior, haga clic en **Operations**.  
  
    2.  En la página operaciones, en la **configuración de seguridad** sección, haga clic en **administrar la configuración de inicio de sesión único**.  
  
    3.  En la página Administrar configuración de inicio de sesión único, en el **configuración de definición de aplicaciones de empresa** sección, haga clic en **administrar la configuración de las definiciones de aplicaciones de empresa**.  
  
    4.  En la página Administrar las definiciones de aplicación de empresa, proporcione los valores de la **nombre para mostrar**, **nombre de la aplicación**y el **póngase en contacto con la dirección de correo electrónico** campos.  
  
        > [!IMPORTANT]
        >  Para el **nombre de la aplicación** campo, asegúrese de especificar el mismo nombre de aplicación de SSO que ha especificado para la **SecondarySsoApplicationId** variable al crear el archivo de definición de aplicación, como se describe en [paso 2: crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).  
  
    5.  Deje el resto de campos como valor predeterminado y haga clic en **Aceptar**.  
  
3.  **Administrar la información de cuenta para definiciones de aplicación de empresa**. En este paso, se habilitan usuarios individuales o grupos para conectarse a una aplicación empresarial de SharePoint. Básicamente, en este paso se asigna un usuario individual o un grupo a un usuario en el sistema LOB. Especificar las credenciales para conectarse al sistema de LOB. Puede hacerlo desde la cuenta de administrar la información para la página de definiciones de aplicación de empresa. Esta opción está disponible desde la consola de Administración Central de SharePoint. Para obtener más información acerca de este paso, consulte la sección "Administrar la información de cuenta para una definición de aplicación de empresa" en [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).  
  
##  <a name="SSP"></a>Crear un proveedor de servicios compartidos  
 Un proveedor de servicios compartidos es una agrupación lógica de servicios compartidos y sus recursos de soporte. Puede crear un SSP mediante la consola de Administración Central de SharePoint.  
  
 Debe definir un sitio Web al crear un SSP. Recuerde que el número de puerto y la dirección del sitio que cree. Volverá a importar la definición de aplicación de catálogo de datos profesionales a este sitio.  
  
 Para obtener más información acerca de cómo crear un SSP, vea "información general de capítulo: crear y configurar los proveedores de servicios compartidos" en [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).  
  
##  <a name="Import"></a>Importar el archivo de definición de aplicación  
 Ahora debe importar el archivo de definición de aplicación en el SSP.  
  
#### <a name="to-import-the-application-definition-file"></a>Para importar el archivo de definición de aplicación  
  
1.  Inicie Administración Central de SharePoint 3.0. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office Server**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
2.  En el panel de navegación izquierdo, haga clic en el nombre del SSP a la que van a importar la definición de aplicación.  
  
3.  En el **catálogo de datos profesionales** sección, haga clic en **Importar definición de la aplicación**.  
  
4.  En la página de definición de la aplicación de importación que se abre, vaya a empleado.XML, seleccione el archivo y, a continuación, haga clic en **abiertos**.  
  
5.  Haga clic en **Importar**.  
  
6.  Después de que el archivo de definición de aplicación se ha importado correctamente, haga clic en **Aceptar**.  
  
     La aplicación que se crean como resultado de importar el archivo de definición de aplicación, MS_SAMPLE_EMPLOYEE, se muestra.  
  
     ![La aplicación en SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora, está listo para crear elementos Web para crear un sitio de SharePoint para ver y buscar los datos empresariales que se van a extraer de Oracle E-Business Suite. Crearemos a:  
  
-   Business el elemento Web de datos lista para mostrar los registros de empleados de la tabla de interfaz MS_SAMPLE_EMPLOYEE. Vea [escenario 1: mostrar datos mediante el elemento Web de lista de datos de económicos](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).  
  
-   Elemento Web de cuadro de búsqueda para realizar una búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE. Vea [escenario 2: realizar búsquedas mediante el elemento Web de cuadro de búsqueda](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)