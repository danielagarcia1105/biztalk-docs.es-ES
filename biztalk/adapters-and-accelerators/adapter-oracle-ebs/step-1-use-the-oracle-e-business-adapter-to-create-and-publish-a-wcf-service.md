---
title: 'Paso 1: Usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cd76f6f-600f-4eb5-8eee-8f3604d0fef4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ac179adbc2e49b767ecae2a68676c5692dcd385
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service"></a>Paso 1: Usar el adaptador de Oracle E-Business para crear y publicar un servicio WCF
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 15 minutos  
  
 **Objetivo:** puede usar el [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)] para generar un servicio WCF de los artefactos de Oracle E-Business Suite pueden estar hospedados en un entorno de hospedaje, como Internet Information Services (IIS) o servicio de activación de proceso de Windows (WAS). Este tema muestra cómo utilizar al Asistente para generar un archivo de servicio WCF.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar al asistente, instale lo siguiente:  
  
-   [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]con el **completar** opción o **personalizado** opción (y elegir **herramientas** dentro de esta opción). Esto instala los [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] plantilla para el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]desde el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
 Para obtener más información sobre estos requisitos previos, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación. La Guía de instalación se instala normalmente en \<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
> [!NOTE]
>  También debe ejecutar la secuencia de comandos create_apps_artifacts.sql suministrado con el ejemplo de Microsoft Office SharePoint Server para crear la **MS_SAMPLE_EMPLOYEE** tabla de interfaz en el **biblioteca de objetos de aplicación**aplicación. Esta tabla de interfaz se utiliza en este tutorial.  
  

  
##  <a name="Create_Service"></a>Crear un servicio WCF para la operación en Oracle E-Business artefacto  
 Esta sección proporciona los pasos para crear un servicio WCF para la operación de selección en la tabla de interfaz MS_SAMPLE empleado.  
  
#### <a name="to-create-a-wcf-service-for-the-select-operation-on-the-mssample-employee-interface-table"></a>Para crear un servicio WCF para la operación de selección en la tabla de interfaz MS_SAMPLE empleado  
  
1.  Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y, a continuación, cree un proyecto.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
     Asimismo, desde el **tipos de proyecto** panel, expanda **Visual C#**y, a continuación, seleccione **Web**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
     ![Cuadro de diálogo nuevo proyecto](../../adapters-and-accelerators/adapter-oracle-ebs/media/01-new-project.gif "01_New_Project")  
  
    > [!NOTE]
    >  Si instaló [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] con el componente de desarrollo Web, el **servicio de adaptador de WCF** plantilla también está disponible en la **nuevo sitio Web** opción (**archivo**  >  **Nueva** > **sitio Web**).  
    >   
    >  Sin embargo, la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] solo es compatible con sitios Web que se crean en el sistema de archivos. Por lo tanto, al crear un sitio Web en el cuadro de diálogo nuevo sitio Web, debe hacer clic en sistema de archivos en la lista de ubicaciones.  
  
3.  Especifique un nombre y ubicación de la solución y, a continuación, haga clic en **Aceptar**. WCF [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] inicia.  
  
4.  En la página de bienvenida, haga clic en **siguiente**.  
  
5.  En la página Elija operaciones, especifique una cadena de conexión para conectarse a Oracle E-Business Suite. Para ello:  
  
    1.  En el **selecciona un enlace** lista, haga clic en **oracleEBSBinding**y, a continuación, haga clic en **configurar**.  
  
    2.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** ficha.  
  
        1.  En el **General** categoría, para el **ClientCredentialType** enlace de propiedad, seleccione **EBusiness**.  
  
        2.  En el **OracleEBS** categoría, especifique los valores adecuados para el **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. En este caso, debe proporcionar las credenciales de la base de datos para la **OracleUserName** y **OraclePassword** propiedades de enlace.  
  
        3.  En el **metadatos** categoría, para el **EnableSafeTyping** enlace de propiedad, seleccione **True**. Si va a recuperar valores de la columna de fecha, se recomienda que establezca el **EnableSafeTyping** enlazar la propiedad a **True** al generar los metadatos.  
  
    3.  Haga clic en el **propiedades de URI** y a continuación, especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).  
  
    4.  Haga clic en el **seguridad** ficha y en el **tipo de credencial de cliente** lista, seleccione **nombre de usuario**. Especifique un nombre de usuario de Oracle E-Business Suite válida y una contraseña para conectarse a Oracle E-Business Suite.  
  
    5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo Configurar el adaptador y, a continuación, haga clic en **conectar**. Una vez que Visual Studio establece correctamente una conexión con Oracle E-Business Suite, se muestra el estado de conexión como **conectado**. También puede ver los metadatos de Oracle E-Business Suite que se muestra en la página Elegir operaciones.  
  
6.  En la página Elija operaciones, en la **tipo de contrato Select** lista, haga clic en **Client (Outbound operations)**.  
  
7.  En el **seleccione una categoría de** cuadro, vaya a la tabla de interfaz MS_SAMPLE_EMPLOYEE en aplicación de biblioteca de objeto de aplicación. Para obtener información acerca de cómo explorar a un artefacto en el adaptador, vea [exploración, búsqueda y recuperar metadatos para las operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
8.  En el **categorías y operaciones disponibles** cuadro, seleccione la **seleccione** operación y, a continuación, haga clic en **agregar**. La operación de selección se agrega a la **agregar categorías y operaciones** cuadro.  
  
     ![Agregar operación de selección](../../adapters-and-accelerators/adapter-oracle-ebs/media/02-msb-gui.gif "02_MSB_GUI")  
  
    > [!NOTE]
    >  Puede agregar más de una operación para cada artefacto. También puede agregar operaciones para distintos artefactos de Oracle E-Business Suite. Por ejemplo, puede agregar una operación de una tabla de interfaz y otro para un programa simultáneo. Además, puede buscar para operaciones específicas mediante la especificación de caracteres comodín en expresiones de búsqueda. Para obtener más información acerca de los caracteres especiales admitidos y los niveles de nodo en el que puede buscar las operaciones, vea [búsqueda para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md).  
  
9. En la página Elija operaciones, haga clic en **siguiente**.  
  
10. En la página Configurar el servicio y los comportamientos de extremo, especifique valores para configurar el comportamiento de servicio y de extremo.  
  
    1.  En el **configuración de comportamiento de servicio** , especifique los siguientes valores:  
  
        |Para la propiedad|Especifique el valor|  
        |----------------------|-----------------------|  
        |EnableMetadataExchange|Establezca esta propiedad en **True** para crear un extremo de intercambio de metadatos. Al establecer esto en **True**, disponer de los metadatos del servicio mediante protocolos estandarizados, como las solicitudes de WS-Metadata Exchange (MEX) y HTTP/GET. Valor predeterminado es **False**.|  
        |IncludeExceptionDetailsinFault|Establezca esta propiedad en **True** para incluir la información de excepción administrada en detalle de errores SOAP devueltos al cliente para fines de depuración. Valor predeterminado es **False**.|  
        |Nombre|Nombre de la configuración de comportamiento de servicio. Para este tutorial, escriba **customServiceBehavior**.|  
        |UseServiceCertificate|Especifica si desea usar el modo de seguridad de nivel de mensaje de WCF. Valor predeterminado es **True**. Para este tutorial, debe establecer esto en **False**.|  
  
        > [!NOTE]
        >  Dado que no estamos utilizando certificados de servicio para este tutorial, no es necesario proporcionar valores para la **FindValue**, **StoreLocation**, **StoreName**y **X509FindType** propiedades. Para obtener más información acerca de los certificados y las propiedades asociadas, vea "X509ClientCertificateCredentialsElement propiedades" en [http://go.microsoft.com/fwlink/?LinkId=103771](http://go.microsoft.com/fwlink/?LinkId=103771).  
  
    2.  En el **configuración de comportamiento de punto de conexión** , especifique los siguientes valores:  
  
        |Para la propiedad|Especifique el valor|  
        |----------------------|-----------------------|  
        |Tipo de autenticación|Para que Microsoft Office SharePoint Server utilizar el servicio WCF, debe establecer como **HTTPUserNamePassword**. Esto permite a los clientes especificar el nombre de usuario y una contraseña como parte del encabezado HTTP.|  
        |Nombre|Especifique un nombre para la configuración de comportamiento de punto de conexión. Para este tutorial, escriba **customEndpointBehavior**.|  
        |UsernameHeader|Nombre para el encabezado de nombre de usuario. En este ejemplo, especifique **MyUserHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692). **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
        |PasswordHeader|Nombre de encabezado de la contraseña. En este ejemplo, especifique **MyPassHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692). **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
  
     En la siguiente ilustración muestra la página Configurar el servicio y los comportamientos de punto de conexión con los valores especificados.  
  
     ![Página Configurar servicio y comportamientos de extremo](../../adapters-and-accelerators/adapter-oracle-ebs/media/03-service-and-endpoint-behavior.gif "03_Service_and_EndPoint_Behavior")  
  
11. En la página Configurar el servicio y comportamientos de extremo, haga clic en **siguiente**.  
  
12. En la página Configurar el enlace de punto de conexión de servicio y la dirección, el **seleccionar un contrato para configurar** muestra el artefacto (MS_SAMPLE_EMPLOYEE) que ha configurado. El **operaciones bajo el contrato seleccionado** cuadro muestra la **seleccione** operación que ha seleccionado para el artefacto en la página Elegir operaciones.  
  
13. En el **configurar el enlace para el contrato y dirección** , especifique los siguientes valores:  
  
    |Para la propiedad|Especifique el valor|  
    |----------------------|-----------------------|  
    |Configuración de enlace|El Asistente solo admite el enlace HTTP básico. Por lo tanto, se rellena automáticamente el campo de configuración de enlace a *System.ServiceModel.Configuration.BasicHttpBindingElement*.<br /><br /> Haga clic en el botón de puntos suspensivos **(...)**  para cambiar las propiedades de enlace de HTTP. Para usar un canal de comunicaciones seguro, siempre se debe establecer el **modo** propiedad **transporte**. El asistente establece el valor predeterminado para la **modo** propiedad como **transporte**.<br /><br /> Para obtener más información acerca de los otros enlaces expuestos, vea "BasicHttpBindingElement miembros" en [http://go.microsoft.com/fwlink/?LinkId=103773](http://go.microsoft.com/fwlink/?LinkId=103773).|  
    |Nombre de extremo|Especifique un nombre de extremo para el contrato.|  
  
     Los demás campos en esta página se rellenan automáticamente en función de los valores especificados en las páginas anteriores.  
  
     Haga clic en **Aplicar**.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en esta página, se aceptan los valores predeterminados para todos los contratos.  
  
     La siguiente ilustración muestra la página de dirección con los valores especificados y configurar el enlace de extremo de servicio.  
  
     ![Configurar el enlace del extremo de servicio y dirección](../../adapters-and-accelerators/adapter-oracle-ebs/media/04-service-endpoint-binding.gif "04_Service_Endpoint_Binding")  
  
14. En la página Configurar el enlace de punto de conexión de servicio y dirección, haga clic en **siguiente**.  La página Resumen muestra una estructura de árbol de los artefactos de Oracle E-Business Suite y la operación seleccionada del artefacto.  
  
15. Revise el resumen y, a continuación, haga clic en **finalizar**.  
  
16. El asistente crea un servicio WCF y agrega los siguientes archivos a la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto:  
  
    1.  archivo .svc. Este es el archivo de servicio WCF. El asistente genera un archivo para cada contrato.  
  
    2.  Archivo Web.config.  
  
    3.  Código de servicio (archivo. cs)  
  
##  <a name="cs"></a>Modificar el archivo. cs  
 Cuando se crea un servicio fuera de un artefacto de Oracle E-Business Suite utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y desea utilizar desde el elemento Web de lista de datos económicos de Microsoft Office SharePoint Server, debe proporcionar la cláusula de filtro completa a partir de la cláusula WHERE . Por ejemplo, si desea buscar un empleado cuyo nombre es "John", debe proporcionar la siguiente cláusula de filtro en el elemento Web de lista de datos de negocio:  
  
```  
where NAME like ‘JOHN’  
```  
  
 Sin embargo, si desea que el usuario para proporcionar solo el nombre como entrada para la cláusula de filtro no se menciona realmente la cláusula de filtro completa, puede agregar un código en el archivo .cs que modifique la cláusula de filtro que proceden del elemento Web de lista de datos económicos de Microsoft Office  Servidor de SharePoint para pasarlo a Oracle E-Business en el formato de cláusula WHERE.  
  
 Por ejemplo, en el caso de este tutorial, si desea que el usuario escriba un nombre de empleado en el elemento de Web de lista de datos de negocio de Microsoft Office SharePoint Server y recuperar el registro para ese empleado, puede agregar el código siguiente en el archivo. cs:  
  
```  
SelectResponse InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.Select(SelectRequest request)   
{  
     request.FILTER = "where NAME like '" + request.FILTER + "'"; // The code to avoid the users from specifying the WHERE clause in the filter from Business Data List Web Part.  
     return base.Channel.Select(request);  
}  
```  
  
##  <a name="Publish"></a>Publicar el servicio WCF  
 Asegúrese de que se ha habilitado SSL para IIS. Para obtener instrucciones sobre cómo habilitar SSL para IIS, consulte [http://go.microsoft.com/fwlink/?LinkId=197170](http://go.microsoft.com/fwlink/?LinkId=197170).  
  
 Para publicar el servicio WCF:  
  
1.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **publicar**.  
  
2.  En el **Publicar Web** cuadro de diálogo, especifique una dirección URL para el servicio WCF. Por ejemplo:  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/  
    ```  
  
    > [!NOTE]
    >  Debe publicar el servicio WCF a una ubicación compatible con SSL. En otras palabras, el valor de la **ubicación de destino** cuadro debe comenzar por "https://". Dado que las credenciales de usuario se pasan en el encabezado HTTP, el Asistente para configura automáticamente un comportamiento de enlaces del adaptador para usar "Transporte" como el modo de seguridad, lo que implica el cifrado SSL. Por supuesto puede volver atrás y editar el archivo web.config para cambiar el valor de la  **\<modo de seguridad\>**  parámetro, pero el uso de SSL siempre es una mejor opción cuando tenga información confidencial que se transportan como texto sin cifrar texto en el encabezado HTTP.  
  
3.  Desde el **copia** cuadro, haga clic en **todos los archivos del proyecto**.  
  
4.  Haga clic en **Publicar**.  
  
5.  Compruebe que el servicio WCF se publicó correctamente.  
  
    1.  Inicie la consola de administración de Microsoft IIS. Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  Desplácese hasta el nodo donde se publica el servicio. Para el **MS_SAMPLE_EMPLOYEE** de servicio, vaya a **Internet Information Services** > **\<nombre_equipo\>**   >  **Sitios Web** > **sitio Web predeterminado** > **MS_SAMPLE_EMPLOYEE**.  
  
    3.  En el panel derecho, haga clic en el archivo InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc y, a continuación, haga clic en **examinar**.  
  
    4.  Muestra la página Web con la dirección URL para recuperar el WSDL. Puede que desee probar la recuperación de metadatos mediante el **svcutil** comando. Por ejemplo, el comando para recuperar metadatos para el servicio MS_SAMPLE_EMPLOYEE es:  
  
        ```  
        svcutil.exe https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>Paso siguiente  
 Para crear un archivo de definición de aplicación del artefacto de Oracle E-Business Suite, use el Editor de definición del catálogo de datos profesionales. Para obtener instrucciones, consulte [paso 2: crear un archivo de definición de aplicación para los artefactos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md). El archivo de definición de aplicación identifica donde se almacenan los datos LOB y el formato en el que se almacena.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Presentar los datos de Oracle E-Business Suite en un sitio de SharePoint](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)