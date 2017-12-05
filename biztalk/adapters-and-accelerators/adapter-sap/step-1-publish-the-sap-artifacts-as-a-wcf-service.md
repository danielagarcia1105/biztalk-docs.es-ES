---
title: 'Paso 1: Publicar los artefactos SAP como un servicio WCF | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service, generating a
- WCF Adapter Service Development Wizard , using the
- WCF Adapter Service Development Wizard
- SAP artifacts, publishing as a WCF service
ms.assetid: bd3087b0-e20f-4b75-beef-a913336d767b
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a83dd69e7c66c8ce8ff1af78662392dd0aa66ff2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-publish-the-sap-artifacts-as-a-wcf-service"></a>Paso 1: Publicar los artefactos SAP como un servicio WCF
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** puede usar el Asistente de desarrollo del servicio de adaptador de WCF para generar un servicio WCF que se puede hospedar en un entorno de hospedaje, como Internet Information Services (IIS) o servicio de activación de proceso de Windows (WAS). Este tema muestra cómo utilizar al Asistente para generar un archivo de servicio WCF.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar al asistente, instale lo siguiente:  
  
-   [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]con el **completar** opción o **personalizado** opción (y elegir **herramientas** dentro de esta opción). Esto instala los [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] plantilla para el Asistente de desarrollo del servicio de adaptador de WCF.  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]desde el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
-   Las bibliotecas de cliente SAP necesarias.  
  
 Para obtener más información sobre estos requisitos previos, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación. La Guía de instalación se instala normalmente en \<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
### <a name="to-publish-the-sap-artifacts-as-a-wcf-service"></a>Para publicar los artefactos SAP como un servicio WCF  
  
1.  Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y, a continuación, cree un proyecto.  
  
2.  En el **nuevo proyecto** cuadro de diálogo, desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
     Asimismo, desde el **tipos de proyecto** panel, expanda **Visual C#**y, a continuación, seleccione **Web**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
    > [!NOTE]
    >  Si instaló [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] con el componente de desarrollo Web, el **servicio de adaptador de WCF** plantilla también está disponible en la **nuevo sitio Web** opción.  
  
3.  Especifique un nombre y ubicación de la solución y, a continuación, haga clic en **Aceptar**. Inicia el Asistente de desarrollo del servicio de adaptador de WCF.  
  
4.  En la página de bienvenida, haga clic en **siguiente**.  
  
5.  En la página Elija operaciones, especifique una cadena de conexión para conectarse al sistema SAP. Para ello:  
  
    1.  En el **selecciona un enlace** lista, haga clic en **sapBinding**y, a continuación, haga clic en **configurar**.  
  
    2.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
    3.  En el **tipo de credencial de cliente** lista, seleccione **nombre de usuario**y, a continuación, especifique un nombre de usuario SAP válido y una contraseña para conectarse al sistema SAP.  
  
    4.  Haga clic en el **propiedades de URI** y a continuación, especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
        > [!NOTE]
        >  Si los parámetros de conexión contienen caracteres reservados (por ejemplo, los caracteres especiales XML), debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** cuadro y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
    5.  Haga clic en el **propiedades de enlace** ficha y, a continuación, especifique valores para las propiedades de enlace, si existe, necesarios para las operaciones que desee cambiar. En este tutorial, se invoca la RFC BAPI_SALESORDER_GETLIST para obtener la lista de pedidos de venta para un cliente específico. La información de pedido de ventas también puede contener columnas de fecha. Cuando se recuperan valores de la columna de fecha, se recomienda que establezca el **EnableSafeTyping** enlazar la propiedad a **True** al generar los metadatos. Si se establece esta propiedad, el tipo de datos de SAP DATS aparece como cadenas.  
  
         Para obtener más información sobre cómo se asignan los tipos de datos SAP en tipos equivalentes de. NET, vea [tipos de datos básicos de SAP](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).  
  
         Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
    6.  Haga clic en **Aceptar**y, a continuación, haga clic en **conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
6.  En la página Elija operaciones, en la **tipo de contrato Select** lista, haga clic en **Client (Outbound operations)**.  
  
7.  En el **seleccione una categoría** , expanda un tipo de artefacto SAP. Por ejemplo, expanda la **RFC** nodo para ver el grupo funcional que contiene la solicitud de cambio para el que desea generar un servicio WCF.  
  
8.  En el **categorías y operaciones disponibles** , seleccione las operaciones que desea generar un servicio WCF y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas se muestran en la **agregar categorías y operaciones** cuadro.  
  
    > [!NOTE]
    >  Puede agregar más de una operación para cada artefacto. También puede agregar operaciones para distintos artefactos SAP. Por ejemplo, puede agregar una operación de RFC y otro para IDOC. Además, puede buscar para operaciones específicas mediante la especificación de caracteres comodín en expresiones de búsqueda. Para obtener más información acerca de los caracteres especiales admitidos y los niveles de nodo en el que puede buscar las operaciones, vea [conectarse a SAP en Visual Studio utilizando este asistente](../../adapters-and-accelerators/adapter-sap/connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard.md)  
  
     En este ejemplo, se agregan los SD_RFC_CUSTOMER_GET y RFC BAPI_SALESORDER_GETLIST.  
  
    > [!NOTE]
    >  Algunas versiones del sistema SAP exponen una solicitud de cambio de RFC_CUSTOMER_GET en lugar de SD_RFC_CUSTOMER_GET.  
  
     ![Seleccionar artefactos SAP](../../adapters-and-accelerators/adapter-sap/media/f944f9a0-7387-46cb-8eb6-337344d01d29.gif "f944f9a0-7387-46cb-8eb6-337344d01d29")  
  
9. En la página Elija operaciones, haga clic en **siguiente**.  
  
10. En la página Configurar el servicio y los comportamientos de extremo, especifique valores para configurar el comportamiento de servicio y de extremo.  
  
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
        >  Para obtener más información acerca de los certificados y las propiedades asociadas, vea "X509ClientCertificateCredentialsElement propiedades" en [http://go.microsoft.com/fwlink/?LinkId=103771](http://go.microsoft.com/fwlink/?LinkId=103771).  
  
    2.  En el **configuración de comportamiento de punto de conexión** , especifique los siguientes valores:  
  
        |Para la propiedad|Especifique el valor|  
        |----------------------|-----------------------|  
        |Tipo de autenticación|: Establezca esta propiedad en **ClientCredentialUserNamePassword** para habilitar los clientes especificar el nombre de usuario y la contraseña al utilizar el servicio WCF.<br /><br /> : Establezca esta propiedad en **HTTPUserNamePassword** para permitir que los clientes especificar el nombre de usuario y una contraseña como parte del encabezado HTTP.<br /><br /> : Establezca esta propiedad en **automática** para habilitar los clientes especificar las credenciales a través de la **ClientCredential** interfaz. Si se produce un error, los clientes pueden pasar las credenciales como parte del encabezado HTTP.<br /><br /> Valor predeterminado es **automática**. Para que Microsoft Office SharePoint Server utilizar el servicio WCF, debe establecer como **HTTPUserNamePassword**.|  
        |Nombre|Especifique un nombre para la configuración de comportamiento de punto de conexión.|  
        |UsernameHeader|Nombre para el encabezado de nombre de usuario. En este ejemplo, especifique **MyUserHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
        |PasswordHeader|Nombre de encabezado de la contraseña. En este ejemplo, especifique **MyPassHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
  
     En la siguiente ilustración muestra la página Configurar el servicio y los comportamientos de punto de conexión con los valores especificados.  
  
     ![Página Configurar servicio y comportamientos de extremo](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
11. En la página Configurar el servicio y comportamientos de extremo, haga clic en **siguiente**.  
  
12. En la página Configurar el enlace de punto de conexión de servicio y la dirección, el **seleccionar un contrato para configurar** cuadro muestra los artefactos SAP para el que ha seleccionado las operaciones en la página Elegir operaciones.  
  
     Por ejemplo, si seleccionó artefactos en RFC e IDOC, el **seleccionar un contrato para configurar** enumera RFC e IDOC. Si selecciona solo una solicitud de cambio, el cuadro mostrará solo RFC.  
  
13. El **operaciones bajo el contrato seleccionado** cuadro muestra las operaciones que seleccionó para cada artefacto en la página Elegir operaciones.  
  
14. En el **configurar el enlace para el contrato y dirección** , especifique los siguientes valores:  
  
    |Para la propiedad|Especifique el valor|  
    |----------------------|-----------------------|  
    |Configuración de enlace|El Asistente solo admite el enlace HTTP básico. Por lo tanto, se rellena automáticamente el campo de configuración de enlace a *System.ServiceModel.Configuration.BasicHttpBindingElement*.<br /><br /> Haga clic en el botón de puntos suspensivos **(...)**  para cambiar las propiedades de enlace de HTTP. Para usar un canal de comunicaciones seguro, siempre se debe establecer el **modo** propiedad **transporte**. El asistente establece el valor predeterminado para la **modo** propiedad como **transporte**.<br /><br /> Para obtener más información acerca de los otros enlaces expuestos, vea "BasicHttpBindingElement miembros" en [http://go.microsoft.com/fwlink/?LinkId=103773](http://go.microsoft.com/fwlink/?LinkId=103773).|  
    |Nombre de extremo|Especifique un nombre de extremo para el contrato.|  
  
     Los demás campos en esta página se rellenan automáticamente en función de los valores especificados en las páginas anteriores.  
  
     Haga clic en **Aplicar**. Realice este paso para todos los contratos que se muestra bajo la **seleccionar un contrato para configurar** cuadro.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en esta página, se aceptan los valores predeterminados para todos los contratos.  
  
     La siguiente ilustración muestra la página de dirección con los valores especificados y configurar el enlace de extremo de servicio.  
  
     ![Configurar el enlace del extremo de servicio y dirección](../../adapters-and-accelerators/adapter-sap/media/356e297c-9893-494c-a834-9d0b8b42da2e.gif "356e297c-9893-494c-a834-9d0b8b42da2e")  
  
15. En la página Configurar el enlace de punto de conexión de servicio y dirección, haga clic en **siguiente**.  La página Resumen muestra una estructura de árbol de los artefactos SAP y, bajo éste, las operaciones seleccionadas durante cada artefacto.  
  
16. Revise el resumen y, a continuación, haga clic en **finalizar**.  
  
17. El asistente crea un servicio WCF y agrega los siguientes archivos a la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto:  
  
    1.  archivo .svc. Este es el archivo de servicio WCF. El asistente genera un archivo para cada contrato.  
  
    2.  Archivo Web.config.  
  
    3.  Código de servicio (archivo. cs)  
  
18. Publicar el servicio WCF.  
  
    1.  Asegúrese de que se ha habilitado SSL para Internet Information Services (IIS). Para obtener instrucciones sobre cómo habilitar SSL para IIS, consulte [http://go.microsoft.com/fwlink/?LinkId=197170](http://go.microsoft.com/fwlink/?LinkId=197170).  
  
    2.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **publicar**.  
  
    3.  En el **Publicar Web** cuadro de diálogo, especifique una dirección URL para el servicio WCF. Por ejemplo:  
  
        ```  
        https://<computer_name>/Customer_Order/  
        ```  
  
    4.  Desde el **copia** cuadro, haga clic en **todos los archivos del proyecto**.  
  
    5.  Haga clic en **Publicar**.  
  
19. Compruebe que el servicio WCF se publicó correctamente.  
  
    1.  Inicie la consola de administración de Microsoft IIS. Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  Desplácese hasta el nodo donde se publica el servicio. Para el **Customer_Order** de servicio, vaya a **Internet Information Services** > **\<nombre_equipo\>**   >  **Sitios Web** > **sitio Web predeterminado** > **Customer_Order**.  
  
    3.  En el panel derecho, haga clic en el archivo Rfc.svc y, a continuación, haga clic en **examinar**.  
  
    4.  Muestra la página Web con la dirección URL para recuperar el WSDL. Puede que desee probar la recuperación de metadatos mediante el **svcutil** comando. Por ejemplo, el comando para recuperar metadatos para el servicio de Customer_Order es:  
  
        ```  
        svcutil.exe https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>Paso siguiente  
 Para crear un archivo de definición de aplicación para los artefactos SAP, use el Editor de definición del catálogo de datos profesionales. Vea [paso 2: crear un archivo de definición de aplicación para los artefactos de SAP](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) para obtener instrucciones. El archivo de definición de aplicación identifica donde se almacenan los datos LOB y el formato en el que se almacena.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentación de datos de un sistema de SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)