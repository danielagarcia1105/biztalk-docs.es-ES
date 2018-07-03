---
title: 'Paso 1: Usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cd76f6f-600f-4eb5-8eee-8f3604d0fef4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75bbbb57b633475d9973d187d61d6e698f6cadb2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981029"
---
# <a name="step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service"></a>Paso 1: Usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** puede usar el [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)] para generar un servicio WCF a partir de los artefactos de Oracle E-Business Suite que se pueden hospedar en un entorno de hospedaje, como Internet Information Services (IIS) o servicio de activación de proceso de Windows (WAS). En este tema se muestra cómo usar al Asistente para generar un archivo de servicio WCF.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar al asistente, instale lo siguiente:  
  
- [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ya sea con la **completar** opción o el **personalizado** opción (y eligiendo **herramientas** dentro de esta opción). Esto instala el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] plantilla para el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] desde el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
  Para obtener más información sobre estos requisitos previos, consulte el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación. La Guía de instalación se instala normalmente en \<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
> [!NOTE]
>  También debe ejecutar el script de create_apps_artifacts.sql proporcionado con el ejemplo de Microsoft Office SharePoint Server para crear el **MS_SAMPLE_EMPLOYEE** tabla de interfaz en el **biblioteca de objetos de aplicación**aplicación. Esta tabla de interfaz se utiliza en este tutorial.  
  

  
##  <a name="Create_Service"></a> Crear un servicio WCF para la operación en Oracle E-Business artefacto  
 Esta sección proporciona los pasos para crear un servicio WCF para la operación Select en la tabla de interfaz MS_SAMPLE empleado.  
  
#### <a name="to-create-a-wcf-service-for-the-select-operation-on-the-mssample-employee-interface-table"></a>Para crear un servicio WCF para la operación Select en la tabla de interfaz MS_SAMPLE empleado  
  
1. Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y, a continuación, cree un proyecto.  
  
2. En el **nuevo proyecto** cuadro de diálogo desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
    Como alternativa, desde el **tipos de proyecto** panel, expanda **Visual C#** y, a continuación, seleccione **Web**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
    ![Cuadro de diálogo nuevo proyecto](../../adapters-and-accelerators/adapter-oracle-ebs/media/01-new-project.gif "01_New_Project")  
  
   > [!NOTE]
   >  Si instaló [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] con el componente de desarrollo Web, el **servicio de adaptador de WCF** plantilla también está disponible en el **nuevo sitio Web** opción (**archivo**  >  **Nueva** > **sitio Web**).  
   > 
   >  Sin embargo, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] solo es compatible con sitios Web que se crean en el sistema de archivos. Por lo tanto, al crear un sitio Web en el cuadro de diálogo nuevo sitio Web, debe hacer clic en sistema de archivos en la lista de ubicaciones.  
  
3. Especifique un nombre y ubicación de la solución y, a continuación, haga clic en **Aceptar**. WCF [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] se inicia.  
  
4. En la página de bienvenida, haga clic en **siguiente**.  
  
5. En la página Elija operaciones, especifique una cadena de conexión para conectarse a Oracle E-Business Suite. Para ello:  
  
   1. En el **selecciona un enlace** lista, haga clic en **oracleEBSBinding**y, a continuación, haga clic en **configurar**.  
  
   2. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **las propiedades de enlace** ficha.  
  
      1.  En el **General** categoría, para el **ClientCredentialType** enlaza la propiedad, seleccione **EBusiness**.  
  
      2.  En el **OracleEBS** categoría, especifique los valores adecuados para el **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. En este caso, deberá proporcionar las credenciales de la base de datos para el **OracleUserName** y **OraclePassword** propiedades de enlace.  
  
      3.  En el **metadatos** categoría, para el **EnableSafeTyping** enlaza la propiedad, seleccione **True**. Si va a recuperar los valores de la columna de fecha, se recomienda que establezca el **EnableSafeTyping** enlazar la propiedad a **True** al generar los metadatos.  
  
   3. Haga clic en el **propiedades de URI** pestaña y, a continuación, especifique valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).  
  
   4. Haga clic en el **seguridad** ficha y en el **tipo de credencial de cliente** lista, seleccione **Username**. Especifique un nombre de usuario de Oracle E-Business Suite válido y una contraseña para conectarse a Oracle E-Business Suite.  
  
   5. Haga clic en **Aceptar** para cerrar el cuadro de diálogo Configurar el adaptador y, a continuación, haga clic en **Connect**. Una vez que Visual Studio establece correctamente una conexión con Oracle E-Business Suite, se muestra el estado de conexión como **conectado**. También puede ver los metadatos de Oracle E-Business Suite que se muestra en la página Elija operaciones.  
  
6. En la página Elegir las operaciones, en la **tipo de contrato Select** lista, haga clic en **Client (Outbound operations)**.  
  
7. En el **seleccionar una categoría** cuadro, vaya a la tabla de interfaz MS_SAMPLE_EMPLOYEE en aplicación de la biblioteca de objetos de aplicación. Para obtener información acerca de la exploración a un artefacto en el adaptador, vea [examinar, buscar y recuperar metadatos para operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
8. En el **operaciones y categorías disponibles** cuadro, seleccione el **seleccione** operación y, a continuación, haga clic en **agregar**. La operación de selección se agrega a la **agregar categorías y operaciones** cuadro.  
  
    ![Adición de la operación de selección](../../adapters-and-accelerators/adapter-oracle-ebs/media/02-msb-gui.gif "02_MSB_GUI")  
  
   > [!NOTE]
   >  Puede agregar más de una operación para cada artefacto. También puede agregar operaciones para distintos artefactos de Oracle E-Business Suite. Por ejemplo, puede agregar una operación para una tabla de interfaz y otro para un programa simultáneo. Además, puede buscar para operaciones específicas mediante la especificación de caracteres comodín en las expresiones de búsqueda. Para obtener más información acerca de los caracteres especiales admitidos y los niveles de nodos en el que puede buscar las operaciones, consulte [búsqueda para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md).  
  
9. En la página Elija operaciones, haga clic en **siguiente**.  
  
10. En la página Configurar el servicio y los comportamientos de extremo, especifique valores para configurar el comportamiento de servicio y el punto de conexión.  
  
    1. En el **configuración del comportamiento de servicio** , especifique los siguientes valores:  
  
       |Para la propiedad|Especifique el valor|  
       |----------------------|-----------------------|  
       |EnableMetadataExchange|Establezca esta opción en **True** para crear un extremo de intercambio de metadatos. Si establece esta configuración **True**, disponer de los metadatos del servicio mediante protocolos estandarizados, como las solicitudes de WS-Metadata Exchange (MEX) y HTTP/GET. El valor predeterminado es **False**.|  
       |IncludeExceptionDetailsinFault|Establezca esta opción en **True** para incluir la información de excepción administrada en detalle de errores SOAP devueltos al cliente con fines de depuración. El valor predeterminado es **False**.|  
       |Nombre|Nombre de la configuración de comportamiento de servicio. Para este tutorial, escriba **customServiceBehavior**.|  
       |UseServiceCertificate|Especifica si desea usar el modo de seguridad de nivel de mensaje de WCF. El valor predeterminado es **True**. Para este tutorial, debe establecer esto en **False**.|  
  
       > [!NOTE]
       >  Como no estamos usando certificados de servicio para este tutorial, no es necesario proporcionar valores para el **FindValue**, **StoreLocation**, **StoreName**y **X509FindType** propiedades. Para obtener más información acerca de los certificados y las propiedades asociadas, vea "X509ClientCertificateCredentialsElement propiedades" en [ http://go.microsoft.com/fwlink/?LinkId=103771 ](http://go.microsoft.com/fwlink/?LinkId=103771).  
  
    2. En el **configuración del comportamiento de punto de conexión** , especifique los siguientes valores:  
  
       |Para la propiedad|Especifique el valor|  
       |----------------------|-----------------------|  
       |Tipo de autenticación|Para que Microsoft Office SharePoint Server consumir el servicio WCF, debe establecer esto como **HTTPUserNamePassword**. Esto permite a los clientes especificar el nombre de usuario y contraseña como parte del encabezado HTTP.|  
       |Nombre|Especifique un nombre para la configuración de comportamiento de punto de conexión. Para este tutorial, escriba **customEndpointBehavior**.|  
       |UsernameHeader|Nombre para el encabezado de nombre de usuario. En este ejemplo, especificar **MyUserHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692). **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
       |PasswordHeader|Nombre de encabezado de la contraseña. En este ejemplo, especificar **MyPassHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692). **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
  
       En la siguiente ilustración muestra la página Configurar el servicio y los comportamientos de punto de conexión con los valores especificados.  
  
       ![Configurar la página de servicio y los comportamientos de extremo](../../adapters-and-accelerators/adapter-oracle-ebs/media/03-service-and-endpoint-behavior.gif "03_Service_and_EndPoint_Behavior")  
  
11. En la página Configurar el servicio y los comportamientos de extremo, haga clic en **siguiente**.  
  
12. En la página Configurar el enlace de punto de conexión de servicio y la dirección, el **seleccione un contrato para configurar** muestra el artefacto (MS_SAMPLE_EMPLOYEE) que ha configurado. El **operaciones en el contrato seleccionado** cuadro muestra la **seleccione** operación que ha seleccionado para el artefacto en la página Elija operaciones.  
  
13. En el **configurar el enlace para el contrato y dirección** , especifique los siguientes valores:  
  
    |Para la propiedad|Especifique el valor|  
    |----------------------|-----------------------|  
    |Configuración de enlace|El Asistente solo admite el enlace HTTP básico. Por lo tanto, se rellena automáticamente el campo de la configuración de enlace a *System.ServiceModel.Configuration.BasicHttpBindingElement*.<br /><br /> Haga clic en el botón de puntos suspensivos **(...)**  para cambiar las propiedades para el enlace HTTP. Para utilizar un canal de comunicación seguro, siempre se debe establecer el **modo** propiedad **transporte**. El asistente establece el valor predeterminado para el **modo** propiedad como **transporte**.<br /><br /> Para obtener más información acerca de los otros enlaces expone, consulte "BasicHttpBindingElement miembros" en [ http://go.microsoft.com/fwlink/?LinkId=103773 ](http://go.microsoft.com/fwlink/?LinkId=103773).|  
    |Nombre de extremo|Especifique un nombre de punto de conexión para el contrato.|  
  
     Los demás campos de esta página se rellenan automáticamente según los valores especificados en las páginas anteriores.  
  
     Haga clic en **Aplicar**.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en esta página, se aceptan los valores predeterminados para todos los contratos.  
  
     La siguiente ilustración muestra la página de dirección con los valores especificados y configurar el enlace de punto de conexión de servicio.  
  
     ![Configurar el enlace del punto de conexión de servicio y dirección](../../adapters-and-accelerators/adapter-oracle-ebs/media/04-service-endpoint-binding.gif "04_Service_Endpoint_Binding")  
  
14. En la página Configurar el enlace de punto de conexión de servicio y la dirección, haga clic en **siguiente**.  La página de resumen muestra una estructura de árbol de los artefactos de Oracle E-Business Suite y la operación seleccionada para el artefacto.  
  
15. Revise el resumen y, a continuación, haga clic en **finalizar**.  
  
16. El asistente crea un servicio WCF y agrega los archivos siguientes en el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto:  
  
    1.  archivo .svc. Este es el archivo de servicio WCF. El asistente genera un archivo para cada contrato.  
  
    2.  Archivo Web.config.  
  
    3.  Código de servicio (archivo. cs)  
  
##  <a name="cs"></a> Modifique el archivo .cs  
 Cuando se crea un servicio fuera de un artefacto de Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y desea usarlo desde el elemento Web de lista de datos empresariales en Microsoft Office SharePoint Server, se espera que proporcione la cláusula de filtro completa a partir de la cláusula WHERE . Por ejemplo, si desea buscar un empleado cuyo nombre es "John", deberá proporcionar la siguiente cláusula de filtro en el elemento Web de lista de datos de negocio:  
  
```  
where NAME like ‘JOHN’  
```  
  
 Sin embargo, si desea que el usuario solo proporcionar el nombre como entrada para la cláusula de filtro sin mencionar realmente la cláusula de filtro completa, puede agregar un código en el archivo .cs que modifique la cláusula de filtro procedentes del elemento Web de lista de datos empresariales en Microsoft Office  Servidor de SharePoint para pasar a Oracle E-Business en el formato de la cláusula WHERE.  
  
 Por ejemplo, en el caso de este tutorial, si desea que el usuario escriba un nombre de empleado en el elemento de Web de lista de datos de negocio en Microsoft Office SharePoint Server y recuperar el registro para ese empleado, puede agregar el código siguiente en el archivo. cs:  
  
```  
SelectResponse InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.Select(SelectRequest request)   
{  
     request.FILTER = "where NAME like '" + request.FILTER + "'"; // The code to avoid the users from specifying the WHERE clause in the filter from Business Data List Web Part.  
     return base.Channel.Select(request);  
}  
```  
  
##  <a name="Publish"></a> Publicar el servicio WCF  
 Asegúrese de que se ha habilitado SSL para IIS. Para obtener instrucciones sobre cómo habilitar SSL para IIS, consulte [ http://go.microsoft.com/fwlink/?LinkId=197170 ](http://go.microsoft.com/fwlink/?LinkId=197170).  
  
 Para publicar el servicio de WCF:  
  
1.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **publicar**.  
  
2.  En el **publicación Web** cuadro de diálogo, especifique una dirección URL para el servicio WCF. Por ejemplo:  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/  
    ```  
  
    > [!NOTE]
    >  Debe publicar el servicio WCF a una ubicación con SSL habilitado. En otras palabras, el valor de la **ubicación de destino** cuadro debe comenzar por "https://". Porque las credenciales de usuario se pasan en el encabezado HTTP, el asistente configura automáticamente el comportamiento de enlace del adaptador para usar "Transport" como el modo de seguridad, lo que implica el cifrado SSL. Por supuesto puede volver atrás y edite el archivo web.config para cambiar el valor de la **\<modo de seguridad\>** parámetro, pero el uso de SSL siempre es una mejor opción cuando tenga información confidencial que se transportan en claro texto en el encabezado HTTP.  
  
3.  Desde el **copia** cuadro, haga clic en **todos los archivos de proyecto**.  
  
4.  Haga clic en **Publicar**.  
  
5.  Compruebe que el servicio de WCF se publicó correctamente.  
  
    1.  Inicie la consola de administración de Microsoft IIS. Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  Desplácese hasta el nodo donde se publica el servicio. Para el **MS_SAMPLE_EMPLOYEE** de servicio, vaya a **Internet Information Services** > **\<nombre_equipo\>**   >  **Sitios Web** > **sitio Web predeterminado** > **MS_SAMPLE_EMPLOYEE**.  
  
    3.  En el panel derecho, haga clic en el archivo InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc y, a continuación, haga clic en **examinar**.  
  
    4.  Aparece la página Web con la dirección URL para recuperar el WSDL. Desea probar la recuperación de metadatos mediante el **svcutil** comando. Por ejemplo, el comando para recuperar los metadatos del servicio MS_SAMPLE_EMPLOYEE es:  
  
        ```  
        svcutil.exe https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>Paso siguiente  
 Para crear un archivo de definición de aplicación para el artefacto de Oracle E-Business Suite, use el Editor de definición del catálogo de datos profesionales. Para obtener instrucciones, consulte [paso 2: crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md). El archivo de definición de la aplicación identifica dónde se almacenan los datos LOB y el formato en el que se almacena.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)