---
title: 'Paso 1: Publicar las operaciones de componente de negocios de Siebel como un servicio WCF | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acfa0c36-50f1-45c1-9fc2-e5e5cedaa6a0
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe869b76a155acb326420c3d5c29850548d8b7ff
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-publish-the-siebel-business-component-operations-as-a-wcf-service"></a>Paso 1: Publicar las operaciones de componente de negocios de Siebel como un servicio WCF
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** puede usar el Asistente de desarrollo del servicio de adaptador de WCF para generar un servicio WCF que se puede hospedar en un entorno de hospedaje, como Internet Information Services (IIS) o servicio de activación de proceso de Windows (WAS). Este tema muestra cómo utilizar al Asistente para generar un archivo de servicio WCF.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar al asistente, instale lo siguiente:  
  
-   [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]con el **completar** opción o **personalizado** opción (y elegir **herramientas** dentro de esta opción). Esto instala la plantilla de Visual Studio para el Asistente de desarrollo del servicio de adaptador de WCF.  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]  
  
-   El cliente de Siebel requerido.  
  
 Para obtener más información sobre estos requisitos previos, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación. La Guía de instalación se instala normalmente en \<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
## <a name="publish-the-siebel-business-components-as-a-wcf-service"></a>Publicar los componentes de negocios de Siebel como un servicio WCF  
  
1.  Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y, a continuación, cree un proyecto.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
     Asimismo, desde el **tipos de proyecto** panel, expanda **Visual C#**y, a continuación, seleccione **Web**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
    > [!NOTE]
    >  Si ha instalado Visual Studio con el componente de desarrollo Web, el **servicio de adaptador de WCF** plantilla también está disponible en la **nuevo sitio Web** opción.  
  
3.  Especifique un nombre y ubicación de la solución y, a continuación, haga clic en **Aceptar**. Inicia el Asistente de desarrollo del servicio de adaptador de WCF.  
  
4.  En la página de bienvenida, haga clic en **siguiente**.  
  
5.  En la página Elija operaciones, especifique una cadena de conexión para conectarse al sistema Siebel. Para ello:  
  
    1.  En el **selecciona un enlace** lista, haga clic en **siebelBinding**y, a continuación, haga clic en **configurar**.  
  
    2.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
    3.  En el **tipo de credencial de cliente** lista, seleccione **nombre de usuario**y, a continuación, especifique el nombre de usuario y la contraseña para conectarse al sistema Siebel.  
  
    4.  Haga clic en el **propiedades de URI** y a continuación, especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [crear el URI de conexión del sistema Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  
  
        > [!NOTE]
        >  Si los parámetros de conexión contienen caracteres reservados (por ejemplo, los caracteres especiales XML), debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
    5.  Haga clic en el **propiedades de enlace** ficha y, a continuación, especifique valores para las propiedades de enlace, si existe, necesarios para las operaciones que desee cambiar.  
  
         Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
    6.  Haga clic en **Aceptar**y, a continuación, haga clic en **conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
6.  En la página Elija operaciones, en la **tipo de contrato Select** lista, haga clic en **Client (Outbound operations)**.  
  
7.  En el **seleccione una categoría de** , expanda el Siebel **objetos comerciales** nodo para ver la lista de objetos comerciales en el repositorio de Siebel. En este ejemplo, haga lo siguiente:  
  
    1.  Expanda el **cuenta** objeto comercial y, a continuación, haga clic en el **cuenta** componente empresarial.  
  
    2.  En el **categorías y operaciones disponibles** cuadro, seleccione la **consulta** operación y, a continuación, haga clic en **agregar**. La operación seleccionada aparece en el **agregar categorías y operaciones** cuadro.  
  
         ![Seleccionar operaciones del componente de negocio de Siebel](../../adapters-and-accelerators/adapter-siebel/media/ed0cb649-dc4d-49ce-9541-c491c9cc9ac9.gif "ed0cb649-dc4d-49ce-9541-c491c9cc9ac9")  
  
8.  En la página Elija operaciones, haga clic en **siguiente**.  
  
9. En la página Configurar el servicio y los comportamientos de extremo, especifique valores para configurar el comportamiento de servicio y de extremo.  
  
    1.  En el **configuración de comportamiento de servicio** , especifique los siguientes valores:  
  
        |Para la propiedad|Especifique el valor|  
        |----------------------|-----------------------|  
        |EnableMetadataExchange|Establezca esta propiedad en **True** para crear un extremo de intercambio de metadatos. Al establecer esto en **True**, disponer de los metadatos del servicio mediante protocolos estandarizados, como las solicitudes de WS-Metadata Exchange (MEX) y HTTP/GET.<br /><br /> Valor predeterminado es **False**.|  
        |IncludeExceptionDetailsinFault|Establezca esta propiedad en **True** para incluir la información de excepción administrada en detalle de errores SOAP devueltos al cliente para fines de depuración. Valor predeterminado es **False**.|  
        |Nombre|Nombre de la configuración de comportamiento de servicio.|  
        |UseServiceCertificate|Especifica si desea usar el modo de seguridad de nivel de mensaje de WCF. Valor predeterminado es **True**.<br /><br /> Para este tutorial, debe establecer esto en **False**.|  
        |FindValue|Una cadena que especifica el valor que se busca en el almacén de certificados X.509.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
        |StoreLocation|Un valor que especifica la ubicación del almacén de certificados que el servicio puede utilizar para validar el certificado del cliente.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
        |StoreName|Nombre del almacén de certificados X.509 para abrir.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
        |X509FindType|El tipo de búsqueda X.509 que se va a ejecutar.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
  
        > [!NOTE]
        >  Para obtener más información acerca de los certificados y las propiedades asociadas, consulte [X509ClientCertificateCredentialsElement propiedades](https://msdn.microsoft.com/library/system.servicemodel.configuration.x509clientcertificatecredentialselement_properties.aspx).
  
    2.  En el **configuración de comportamiento de punto de conexión** , especifique los siguientes valores:  
  
        |Para la propiedad|Especifique el valor|  
        |----------------------|-----------------------|  
        |Tipo de autenticación|: Establezca esta propiedad en **ClientCredentialUserNamePassword** para habilitar los clientes especificar el nombre de usuario y la contraseña al utilizar el servicio WCF.<br /><br /> : Establezca esta propiedad en **HTTPUserNamePassword** para permitir que los clientes especificar el nombre de usuario y una contraseña como parte del encabezado HTTP.<br /><br /> : Establezca esta propiedad en **automática** para habilitar los clientes especificar las credenciales a través de la **ClientCredential** interfaz. Si se produce un error, los clientes pueden pasar las credenciales como parte del encabezado HTTP.<br /><br /> Valor predeterminado es **automática**. Para que Microsoft Office SharePoint Server utilizar el servicio WCF, debe establecer como **HTTPUserNamePassword**.|  
        |Nombre|Especifique un nombre para la configuración de comportamiento de punto de conexión.|  
        |UsernameHeader|Nombre para el encabezado de nombre de usuario. En este ejemplo, especifique **MyUserHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
        |PasswordHeader|Nombre de encabezado de la contraseña. En este ejemplo, especifique **MyPassHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
  
     En la siguiente ilustración muestra la página Configurar el servicio y los comportamientos de punto de conexión con los valores especificados.  
  
     ![Página Configurar servicio y comportamientos de extremo](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
10. En la página Configurar el servicio y comportamientos de extremo, haga clic en **siguiente**.  
  
11. En la página Configurar el enlace de punto de conexión de servicio y la dirección, el **seleccionar un contrato para configurar** cuadro muestra los contratos para los componentes de negocios de Siebel para el que ha seleccionado las operaciones en la página Elegir operaciones. El **operaciones bajo el contrato seleccionado** cuadro muestra las operaciones que seleccionó para cada artefacto en la página Elegir operaciones.  
  
12. En el **configurar el enlace para el contrato y dirección** , especifique los siguientes valores:  
  
    |Para la propiedad|Especifique el valor|  
    |----------------------|-----------------------|  
    |Configuración de enlace|El Asistente solo admite el enlace HTTP básico. Por lo tanto, se rellena automáticamente el campo de configuración de enlace a *System.ServiceModel.Configuration.BasicHttpBindingElement*.<br /><br /> Haga clic en el botón de puntos suspensivos **(...)**  para cambiar las propiedades de enlace de HTTP. Para usar un canal de comunicaciones seguro, siempre se debe establecer el **modo** propiedad **transporte**. El asistente establece el valor predeterminado para la **modo** propiedad como **transporte**.<br /><br /> Para obtener más información acerca de los otros enlaces expuestos, consulte [BasicHttpBindingElement clase](https://msdn.microsoft.com/library/system.servicemodel.configuration.basichttpbindingelement.aspx).|  
    |Nombre de extremo|Especifique un nombre de extremo para el contrato.|  
  
     Los demás campos en esta página se rellenan automáticamente en función de los valores especificados en las páginas anteriores.  
  
     Haga clic en **Aplicar**. Realice este paso para todos los contratos que se muestra bajo la **seleccionar un contrato para configurar** cuadro.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en esta página, se aceptan los valores predeterminados para todos los contratos.  
  
     La siguiente ilustración muestra la página de dirección con los valores especificados y configurar el enlace de extremo de servicio.  
  
     ![Configurar el enlace del extremo de servicio y dirección](../../adapters-and-accelerators/adapter-siebel/media/467d3e18-027d-4218-9d72-0740c1f559e3.gif "467d3e18-027d-4218-9d72-0740c1f559e3")  
  
13. En la página Configurar el enlace de punto de conexión de servicio y dirección, haga clic en **siguiente**. La página Resumen muestra una estructura de árbol de los contratos para los componentes seleccionados de negocios de Siebel y, en el, de las operaciones seleccionadas para cada componente empresarial.  
  
14. Revise el resumen y, a continuación, haga clic en **finalizar**.  
  
15. El asistente crea un servicio WCF y agrega los siguientes archivos a la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto:  
  
    1.  archivo .svc. Este es el archivo de servicio WCF. El asistente genera un archivo para cada contrato.  
  
    2.  Archivo Web.config.  
  
    3.  Código de servicio (archivo. cs).  
  
16. Publicar el servicio WCF.  
  
    1.  Asegúrese de que se ha habilitado SSL para Internet Information Services (IIS). Vea [cómo configurar SSL](https://docs.microsoft.com/iis/manage/configuring-security/how-to-set-up-ssl-on-iis).
  
    2.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **publicar**.  
  
    3.  En el **Publicar Web** cuadro de diálogo, especifique una dirección URL para el servicio WCF. Por ejemplo:  
  
        ```  
        https://<computer_name>/Siebel_Account/  
        ```  
  
    4.  Desde el **copia** cuadro, haga clic en **todos los archivos del proyecto**.  
  
    5.  Haga clic en **Publicar**.  
  
17. Compruebe que el servicio WCF se publicó correctamente.  
  
    1.  Inicie la consola de administración de Microsoft IIS. Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services**.  
  
    2.  Desplácese hasta el nodo donde se publica el servicio. Para el **Siebel_Account** de servicio, vaya a **Internet Information Services** > **\<nombre_equipo\>**   >  **Sitios Web** > **sitio Web predeterminado** > **Siebel_Account**.  
  
    3.  En el panel derecho, haga clic en el archivo BusinessObjects_Account_Account_Operation.svc y, a continuación, haga clic en **examinar**.  
  
    4.  Muestra la página Web con la dirección URL para recuperar el WSDL. Puede que desee probar la recuperación de metadatos mediante el comando svcutil. Por ejemplo, el comando para recuperar metadatos para el servicio de Siebel_Account es:  
  
        ```  
        svcutil.exe https://localhost/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
        ```  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora tiene un servicio WCF para el componente de negocio de Siebel. Utilice el Editor de definición del catálogo de datos profesionales para crear un archivo de definición de aplicación para las operaciones de componente de negocio de Siebel. Vea [paso 2: crear un archivo de definición de aplicación para operaciones de componente de negocio de Siebel](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md) para obtener instrucciones. El archivo de definición de aplicación identifica donde se almacenan los datos LOB y el formato en el que se almacena.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentación de datos de un sistema de Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)