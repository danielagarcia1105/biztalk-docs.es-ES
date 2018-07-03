---
title: 'Paso 2: Crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2665afde-0337-4795-ab4c-6223d39fdf9c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0bd73da129e978bfe2d4ad5af2b4f26fb9bcc16
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970757"
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a>Paso 2: Crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite
![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** la característica catálogo de datos empresariales en Microsoft SharePoint Server expone e incorpora datos desde aplicaciones de línea de negocio (LOB) en los portales. Para incorporar estos datos en el sitio del portal, debe crear un archivo de definición de aplicación que pueden usar Microsoft Office SharePoint Server.  
  
 La herramienta Editor de definición de catálogo de datos empresariales, disponible con el SDK de Microsoft Office SharePoint Server 2007, permite crear un archivo de definición de aplicación para el catálogo de datos profesionales. Esta herramienta genera automáticamente un archivo XML para el archivo de definición, por lo que no es necesario crear manualmente el archivo en un documento XML editor.  
  
 El propósito de la aplicación de Microsoft Office SharePoint Server que se va a crear es:  
  
- Consulta de un empleado en la tabla de interfaz MS_SAMPLE_EMPLOYEE mediante un elemento de Web de lista de datos de negocio se basa en un nombre de empleado.  
  
- Realizar una búsqueda de texto completo de Microsoft Office SharePoint Server en la tabla de interfaz MS_SAMPLE_EMPLOYEE.  
  
  Para cada uno de estos requisitos, debe completar un conjunto de tareas en la herramienta Editor de definición de catálogo de datos profesionales. Este tema proporciona instrucciones sobre cómo realizar estas tareas.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Asegúrese de que tiene el Editor de definición del catálogo de datos profesionales instalado como parte del SDK de Microsoft Office SharePoint Server 2007. Puede descargar el SDK desde [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130).  
  
-   Publicar el servicio WCF, como se describe en [paso 1: usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).  
  

  
##  <a name="Connect"></a> Conectar con el servicio WCF LOB y crear entidad  
 Debe conectarse al servicio WCF para extraer el lenguaje de descripción de servicios Web (WSDL) para el servicio. Desde el archivo WSDL, el Editor de definición del catálogo de datos profesionales extrae los métodos. Estos métodos se pueden usar para crear entidades. Para este tutorial, se crea una entidad.  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>Para conectarse al servicio WCF y crear entidades  
  
1.  Inicie el Editor de definición del catálogo de datos profesionales. En el **iniciar** menú, haga clic en **Editor de definición de catálogo de datos de Microsoft Business**.  
  
2.  En la barra de herramientas, haga clic en **Agregar sistema LOB**.  
  
3.  En la ventana Agregar sistema LOB, haga clic en **conectar al servicio Web**.  
  
4.  En el **URL** cuadro, escriba la dirección URL del servicio WCF. Para este tutorial, la dirección URL será:  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     La dirección URL está disponible cuando se prueba si se publica correctamente, como se describe en el servicio WCF [paso 1: usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).  
  
5.  Haga clic en **Conectar**.  
  
6.  Para ver las operaciones que seleccionó en el Asistente para desarrollo de servicio de adaptador de WCF, haga clic en el **Agregar método Web** ficha. Verá el siguiente método: **seleccione**.  
  
7.  Arrastre el **seleccione** métodos a la superficie de diseño. El método de arrastrar a la superficie de diseño, se crea una entidad y el método pasa a formar parte de la entidad.  
  
     ![Agregar método Select a la superficie de diseño](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")  
  
8.  Haga clic en **Aceptar**.  
  
9. En el **escriba el nombre para el sistema LOB** cuadro de diálogo, escriba un nombre en el **nombre del sistema de LOB** cuadro. En este ejemplo, llámelo **MS_SAMPLE_EMPLOYEE**y, a continuación, haga clic en **Aceptar**.  
  
10. En el Editor datos profesionales catálogo definición, la entidad recién creada aparece como **Entity0**. Cambiar el nombre de la entidad a **empleado**. Realice los pasos siguientes para cambiar el nombre de la entidad:  
  
    1.  Expanda el **MS_SAMPLE_EMPLOYEE** nodo y, a continuación, expanda el **entidades** nodo.  
  
    2.  Seleccione el **Entity0** nodo.  
  
    3.  En el panel Propiedades, escriba **empleado** en el **nombre** cuadro.  
  
         ![Cambiar el nombre de la entidad](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")  
  
##  <a name="Headers"></a> Especifique el nombre de usuario y contraseña encabezados para los métodos  
 Al crear un servicio WCF para la operación Select en la tabla de interfaz MS_SAMPLE_EMPLOYEE en Oracle E-Business Suite, especifica los encabezados de nombre y la contraseña del usuario como parte de la configuración de comportamiento de punto de conexión en [paso 1: usar Oracle Adaptador de comercio electrónico para crear y publicar un servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md). Debe especificar los mismos valores para la propiedad método de selección.  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a>Para especificar los encabezados de nombre y la contraseña de usuario para el método Select  
  
1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Haga clic en el **seleccione** nodo y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.  
  
3.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderUserName** para el **nombre** cuadro. Tipo **MyUserHeader** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
4.  En la ventana del Editor de colección PropertyView, haga clic en **agregar**y en el panel de propiedades, escriba **HttpHeaderPassword** para el **nombre** cuadro. De forma similar, escriba **MyPasswordHeader** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
     ![Agregar una propiedad](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")  
  
5.  Haga clic en **Aceptar**.  
  
##  <a name="Scenario1"></a> Escenario 1: Consulta de los empleados mediante un elemento Web de lista de datos de Business  
 Para crear un archivo de definición de aplicación que puede usarse para buscar los empleados de un elemento de Web de lista de datos de negocio y según el nombre de empleado, debe realizar el siguiente conjunto de tareas.  
  
1.  En el **seleccione** método, cree un filtro y asignarlo a la **filtro** parámetro.  
  
2.  Crear un **buscador** instancia de método para el **seleccione** método. Un **buscador** método recupera una lista de registros basada en un filtro.  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a>Para crear un filtro y asignarla al parámetro de filtro  
  
1.  Crear un filtro.  
  
    1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el **seleccione** método, haga clic en **filtros**y, a continuación, haga clic en **Agregar filtro**.  
  
         ![Agregar un filtro para el método SELECT](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")  
  
    3.  En el panel de propiedades para el **FilterType** propiedad, seleccione **es igual a**.  
  
    4.  En el panel Propiedades, escriba **EmployeeName** en el **nombre** cuadro.  
  
         ![Especificar propiedades de filtro](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")  
  
2.  Asignar el filtro para el **filtro** parámetro en el **seleccione** método.  
  
    1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el **seleccione** método y, a continuación, expanda el **parámetros** nodo.  
  
    3.  Expanda el **filtro** nodo y haga clic en el segundo **filtro** nodo.  
  
    4.  En el panel Propiedades, seleccione **EmployeeName** desde el **FilterDescriptor** lista.  
  
         ![Asignar el filtro al parámetro del método Select](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a>Para crear una instancia de método de buscador para el método Select  
  
1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **seleccione** nodo, haga clic en **instancias**y, a continuación, haga clic en **Agregar instancia del método**.  
  
     ![Agregar una instancia de método](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  En la ventana Crear instancia de método, haga clic en **buscador** para **tipo de método de instancia**. Seleccione **devolver** para **devolver TypeDescriptor**.  
  
     ![Crear una instancia de método de buscador](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")  
  
4.  Haga clic en **Aceptar**.  
  
5.  En el panel Propiedades, escriba **Finder_Instance** en el **nombre** cuadro.  
  
     ![Especifique un nombre para la instancia de método de buscador](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")  
  
##  <a name="Scenario2"></a> Escenario 2: Búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE desde Microsoft Office SharePoint Server  
 Para crear un archivo de definición de aplicación que puede usarse para realizar una búsqueda de texto completo en la tabla de interfaz MS_SAMPLE_EMPLOYEE desde Microsoft Office SharePoint Server, debe realizar el siguiente conjunto de tareas.  
  
-   En el **seleccione** método, crear un identificador y asignarlo a los parámetros de filtro y el valor devuelto que almacena el nombre del empleado.  
  
-   Crear un **buscador específico** instancia de método para el **seleccione**. El **buscador específico** método encontrará un registro específico en función del identificador, es decir, un nombre de empleado.  
  
-   Cree una instancia de método de enumerador de identificador.  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a>Para crear un identificador y asignarlo al valor de filtro empleado y de parámetro de nombre devuelto  
  
1.  Crear un identificador de la **empleado** entidad.  
  
    1.  En el panel de objetos de metadatos, expanda el **empleado** nodo.  
  
    2.  Haga clic en el **identificadores** nodo y, a continuación, seleccione **Agregar identificador**.  
  
         ![Crear un identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")  
  
    3.  En el panel Propiedades, escriba **EmployeeName** en el **nombre** cuadro.  
  
    4.  Seleccione **System.String** para el **tipo** cuadro.  
  
         ![Especificar propiedades del identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")  
  
2.  Asignar el identificador para el parámetro de filtro para el **seleccione** método.  
  
    1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el **seleccione** método y, a continuación, expanda el **parámetros** nodo.  
  
    3.  Expanda el **filtro** parámetro y, a continuación, haga clic en el segundo **filtro** nodo.  
  
    4.  En el panel Propiedades, seleccione **EmployeeName [Employee]** desde el **identificador** lista.  
  
         ![Configurar el identificador para el parámetro FILTER](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")  
  
3.  Asignar el identificador para el valor devuelto del nombre de empleado.  
  
    1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.  
  
    2.  Expanda el **seleccione** método y, a continuación, expanda el **parámetros** nodo.  
  
    3.  Expanda el **devolver** nodo y, a continuación, el segundo **devolver** nodo, el **elemento** nodo y, a continuación, haga clic en el **nombre** nodo.  
  
    4.  En el panel Propiedades, seleccione **EmployeeName [Employee]** desde el **identificador** lista.  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a>Para crear una instancia de método de buscador específico para el método Select  
  
1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, el **métodos** nodo.  
  
2.  Expanda el **seleccione** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.  
  
     ![Agregar una instancia de método](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  En la ventana Crear instancia de método, seleccione **buscador específico** para **tipo de método de instancia**. Seleccione **devolver** para **devolver TypeDescriptor**.  
  
     ![Agregar una instancia de método de buscador específico](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")  
  
4.  Haga clic en **Aceptar**.  
  
5.  En el panel Propiedades, escriba **SpeciFinder_Instance** para el **nombre** cuadro.  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a>Para crear una instancia de método de enumerador de identificador para el método Select  
  
1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, el **métodos** nodo.  
  
2.  Expanda el **seleccione** nodo, haga clic en **instancias**y, a continuación, seleccione **Agregar instancia del método** para abrir la ventana Crear instancia de método.  
  
     ![Agregar una instancia de método](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  En la ventana Crear instancia de método, seleccione **enumerador de identificador** para **tipo de método de instancia**. Seleccione **devolver** para **devolver TypeDescriptor**.  
  
     ![Cree una instancia de método de enumerador de identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")  
  
4.  Haga clic en **Aceptar**.  
  
5.  En el panel Propiedades, escriba **IDEnumerator_Instance** para el **nombre** cuadro.  
  
##  <a name="Defaults"></a> Establecer parámetros predeterminados para las instancias de método  
 El método Select requiere que especifique los nombres de columna. Por lo tanto, debe especificar un valor predeterminado para el **COLUMN_NAMES** parámetro para las instancias de método de buscador de buscador específico y enumerador de Id. se creó anteriormente. Además, también debe especificar un valor predeterminado para el **filtro** parámetro para la instancia de método de enumerador de identificador.  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a>Para establecer los parámetros predeterminados para las instancias de método  
  
1.  En el panel de objetos de metadatos, expanda el **empleado** nodo y, a continuación, expanda el **métodos** nodo.  
  
2.  Expanda el **seleccione** nodo y, a continuación, expanda el **parámetros** nodo.  
  
3.  Expanda el **COLUMN_NAMES** nodo y, a continuación, seleccione el **COLUMN_NAMES** parámetro.  
  
4.  En el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** cuadro.  
  
5.  En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **agregar**y haga clic en el panel de propiedades, **Finder_Instance** en el  **SelectMethodInstance** lista.  
  
     ![Especifica el valor predeterminado para la instancia de buscador](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")  
  
6.  Tipo `*` en el **valor** cuadro.  
  
7.  De forma similar, repita los pasos 5 y 6 para agregar los valores predeterminados para el **SpecificFinder_Instance** y **IDEnumerator_Instance** instancias de método.  
  
8.  En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. A continuación, agregue un valor predeterminado para el **filtro** parámetro para el **IDEnumerator_Instance** instancia de método. Expanda el **filtro** nodo y, a continuación, seleccione el **filtro** parámetro.  
  
10. En el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **DefaultValues** cuadro.  
  
11. En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **agregar**y haga clic en el panel de propiedades, **IDEnumerator_Instance** en el  **SelectMethodInstance** lista.  
  
12. Tipo `%` en el **valor** cuadro.  
  
     ![Valores predeterminados para la instancia de enumerador de identificador](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")  
  
13. En el **Editor de la colección DefaultValueView** cuadro de diálogo, haga clic en **Aceptar**.  
  
##  <a name="SSO"></a> Establecer la seguridad de Single Sign-On para conectarse a Oracle E-Business Suite  
 Cuando haya terminado de realizar todos los procedimientos de este tema, habrá creado un archivo de definición de aplicación que se puede importar a una aplicación de SharePoint. Desde la aplicación, invoca los métodos para recuperar los datos pertinentes de Oracle E-Business Suite. Para habilitar esta opción, debe crear una asignación entre un usuario de Oracle E-Business Suite y el usuario en la aplicación de SharePoint. Cree esta asignación en la consola de Administración Central de SharePoint después de importar el archivo de definición de aplicación.  
  
 Sin embargo, para crear la asignación, debe establecer una propiedad **SecondarySsoApplicationId** en el Editor de definición de catálogo de datos de Business.  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>Para establecer la propiedad SecondarySsoApplicationId  
  
1.  En el panel de objetos de metadatos, expanda el **MS_SAMPLE_EMPLOYEE** nodo y, a continuación, expanda el **instancias** nodo.  
  
2.  Haga clic en **MS_SAMPLE_EMPLOYEE_Instance**y en el panel Propiedades, haga clic en el botón de puntos suspensivos (...) en el **propiedades** cuadro.  
  
3.  En el **Editor de la colección PropertyView** cuadro de diálogo, haga clic en **agregar**y en el panel de propiedades, escriba **SecondarySsoApplicationId** para el **nombre** cuadro. De forma similar, escriba **OracleSSO** para el **PropertyValue** cuadro. Seleccione **System.String** para el **tipo** cuadro.  
  
     ![Agregue la propiedad SSO](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")  
  
4.  Haga clic en **Aceptar**.  
  
##  <a name="Export"></a> Exportar la definición de aplicación a un archivo  
 Ahora ha creado una definición de aplicación que contiene los metadatos de instancia de Oracle E-Business Suite. Esta definición se debe exportar a un archivo XML, que puede importarse en Microsoft Office SharePoint Server.  
  
#### <a name="to-export-the-application-definition-to-a-file"></a>Para exportar la definición de aplicación a un archivo  
  
1.  En el panel de objetos de metadatos, haga clic en el **MS_SAMPLE_EMPLOYEE** nodo y, a continuación, haga clic en **exportar**.  
  
2.  Guarde el archivo como empleado.Xml.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora debe crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite. Para obtener instrucciones, consulte [paso 3: crear una aplicación de SharePoint para recuperar datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)