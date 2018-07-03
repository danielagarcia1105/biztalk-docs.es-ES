---
title: 'Paso 1: Publicar los artefactos SAP como un servicio WCF | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service, generating a
- WCF Adapter Service Development Wizard , using the
- WCF Adapter Service Development Wizard
- SAP artifacts, publishing as a WCF service
ms.assetid: bd3087b0-e20f-4b75-beef-a913336d767b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af261acd7d61ae49aef53a9f7f206fb8a597fbd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989381"
---
# <a name="step-1-publish-the-sap-artifacts-as-a-wcf-service"></a>Paso 1: Publicar los artefactos SAP como un servicio WCF
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** puede usar el Asistente para desarrollo de servicio de adaptador de WCF para generar un servicio WCF que se puede hospedar en un entorno de hospedaje, como Internet Information Services (IIS) o servicio de activación de proceso de Windows (WAS). En este tema se muestra cómo usar al Asistente para generar un archivo de servicio WCF.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar al asistente, instale lo siguiente:  
  
- [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ya sea con la **completar** opción o el **personalizado** opción (y eligiendo **herramientas** dentro de esta opción). Esto instala el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] plantilla para el Asistente para desarrollo de servicio de adaptador de WCF.  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] desde el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
- Las bibliotecas de cliente SAP necesarias.  
  
  Para obtener más información sobre estos requisitos previos, consulte el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación. La Guía de instalación se instala normalmente en \<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
### <a name="to-publish-the-sap-artifacts-as-a-wcf-service"></a>Para publicar los artefactos SAP como un servicio WCF  
  
1. Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y, a continuación, cree un proyecto.  
  
2. En el **nuevo proyecto** cuadro de diálogo desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
    Como alternativa, desde el **tipos de proyecto** panel, expanda **Visual C#** y, a continuación, seleccione **Web**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
   > [!NOTE]
   >  Si instaló [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] con el componente de desarrollo Web, el **servicio de adaptador de WCF** plantilla también está disponible en el **nuevo sitio Web** opción.  
  
3. Especifique un nombre y ubicación de la solución y, a continuación, haga clic en **Aceptar**. Se inicia el Asistente para desarrollo de servicio de adaptador de WCF.  
  
4. En la página de bienvenida, haga clic en **siguiente**.  
  
5. En la página Elija operaciones, especifique una cadena de conexión para conectarse al sistema SAP. Para ello:  
  
   1. En el **selecciona un enlace** lista, haga clic en **sapBinding**y, a continuación, haga clic en **configurar**.  
  
   2. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
   3. En el **tipo de credencial de cliente** lista, seleccione **Username**y, a continuación, especifique un nombre de usuario válido de SAP y una contraseña para conectarse al sistema SAP.  
  
   4. Haga clic en el **propiedades de URI** pestaña y, a continuación, especifique valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
      > [!NOTE]
      >  Si los parámetros de conexión contienen caracteres reservados (por ejemplo, caracteres especiales XML), deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** cuadro y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  
  
   5. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, necesarios para las operaciones de destino. En este tutorial, se invoca la RFC BAPI_SALESORDER_GETLIST para obtener la lista de pedidos de venta para un cliente específico. La información de pedido de ventas también podría contener las columnas de fecha. Al recuperar los valores de la columna de fecha, se recomienda que establezca el **EnableSafeTyping** enlazar la propiedad a **True** al generar los metadatos. Si se establece esta propiedad, el tipo de datos de SAP DAT se expone como cadenas.  
  
       Para obtener más información sobre cómo se asignan los tipos de datos SAP para los tipos de .NET equivalente, vea [básica de los tipos de datos de SAP](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md).  
  
       Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
   6. Haga clic en **Aceptar**y, a continuación, haga clic en **Connect**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
6. En la página Elegir las operaciones, en la **tipo de contrato Select** lista, haga clic en **Client (Outbound operations)**.  
  
7. En el **seleccionar una categoría** , expanda un tipo de artefacto SAP. Por ejemplo, expanda el **RFC** nodo para ver el grupo funcional que contiene la solicitud de cambio para el que desea generar un servicio WCF.  
  
8. En el **operaciones y categorías disponibles** , seleccione las operaciones para el que desea generar un servicio WCF y, a continuación, haga clic en **agregar**. Las operaciones seleccionadas aparecen en la **agregar categorías y operaciones** cuadro.  
  
   > [!NOTE]
   >  Puede agregar más de una operación para cada artefacto. También puede agregar operaciones para distintos artefactos SAP. Por ejemplo, puede agregar una operación de RFC y otro para el IDOC. Además, puede buscar para operaciones específicas mediante la especificación de caracteres comodín en las expresiones de búsqueda. Para obtener más información acerca de los caracteres especiales admitidos y los niveles de nodos en el que puede buscar las operaciones, consulte [conectarse a SAP en Visual Studio utilizando metadatos Asistente para agregar adaptador](../../adapters-and-accelerators/adapter-sap/connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard.md)  
  
    En este ejemplo, se agregan los SD_RFC_CUSTOMER_GET y RFC BAPI_SALESORDER_GETLIST.  
  
   > [!NOTE]
   >  Algunas versiones del sistema SAP exponen una RFC RFC_CUSTOMER_GET en lugar de SD_RFC_CUSTOMER_GET.  
  
    ![Seleccionar artefactos SAP](../../adapters-and-accelerators/adapter-sap/media/f944f9a0-7387-46cb-8eb6-337344d01d29.gif "f944f9a0-7387-46cb-8eb6-337344d01d29")  
  
9. En la página Elija operaciones, haga clic en **siguiente**.  
  
10. En la página Configurar el servicio y los comportamientos de extremo, especifique valores para configurar el comportamiento de servicio y el punto de conexión.  
  
    1. En el **configuración del comportamiento de servicio** , especifique los siguientes valores:  
  
       |Para la propiedad|Especifique el valor|  
       |----------------------|-----------------------|  
       |EnableMetadataExchange|Establezca esta opción en **True** para crear un extremo de intercambio de metadatos. Si establece esta configuración **True**, disponer de los metadatos del servicio mediante protocolos estandarizados, como las solicitudes de WS-Metadata Exchange (MEX) y HTTP/GET.<br /><br /> El valor predeterminado es **False**.|  
       |IncludeExceptionDetailsinFault|Establezca esta opción en **True** para incluir la información de excepción administrada en detalle de errores SOAP devueltos al cliente con fines de depuración. El valor predeterminado es **False**.|  
       |Nombre|Nombre de la configuración de comportamiento de servicio.|  
       |UseServiceCertificate|Especifica si desea usar el modo de seguridad de nivel de mensaje de WCF. El valor predeterminado es **True**.<br /><br /> Para este tutorial, debe establecer esto en **False**.|  
       |FindValue|Una cadena que especifica el valor que se busca en el almacén de certificados X.509.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
       |StoreLocation|Un valor que especifica la ubicación del almacén de certificados que el servicio puede utilizar para validar el certificado del cliente.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
       |StoreName|Nombre del almacén de certificados X.509 para abrir.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
       |X509FindType|El tipo de búsqueda X.509 que se ejecutará.<br /><br /> **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
  
       > [!NOTE]
       >  Para obtener más información acerca de los certificados y las propiedades asociadas, vea "X509ClientCertificateCredentialsElement propiedades" en [ http://go.microsoft.com/fwlink/?LinkId=103771 ](http://go.microsoft.com/fwlink/?LinkId=103771).  
  
    2. En el **configuración del comportamiento de punto de conexión** , especifique los siguientes valores:  
  
       |Para la propiedad|Especifique el valor|  
       |----------------------|-----------------------|  
       |Tipo de autenticación|: Establezca esta opción en **ClientCredentialUserNamePassword** para permitir que los clientes especificar el nombre de usuario y la contraseña al utilizar el servicio WCF.<br /><br /> : Establezca esta opción en **HTTPUserNamePassword** para permitir que los clientes especificar el nombre de usuario y contraseña como parte del encabezado HTTP.<br /><br /> : Establezca esta opción en **automática** primero habilite los clientes especificar credenciales a través de la **ClientCredential** interfaz. Si se produce un error, los clientes pueden pasar credenciales como parte del encabezado HTTP.<br /><br /> El valor predeterminado es **automática**. Para que Microsoft Office SharePoint Server consumir el servicio WCF, debe establecer esto como **HTTPUserNamePassword**.|  
       |Nombre|Especifique un nombre para la configuración de comportamiento de punto de conexión.|  
       |UsernameHeader|Nombre para el encabezado de nombre de usuario. En este ejemplo, especificar **MyUserHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
       |PasswordHeader|Nombre de encabezado de la contraseña. En este ejemplo, especificar **MyPassHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
  
       En la siguiente ilustración muestra la página Configurar el servicio y los comportamientos de punto de conexión con los valores especificados.  
  
       ![Configurar la página de servicio y los comportamientos de extremo](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
11. En la página Configurar el servicio y los comportamientos de extremo, haga clic en **siguiente**.  
  
12. En la página Configurar el enlace de punto de conexión de servicio y la dirección, el **seleccione un contrato para configurar** cuadro muestran los artefactos SAP para el que ha seleccionado las operaciones en la página Elija operaciones.  
  
     Por ejemplo, si ha seleccionado los artefactos en RFC e IDOC, el **seleccione un contrato para configurar** enumera RFC e IDOC. Si ha seleccionado solamente una solicitud de cambio, el cuadro mostrará solo RFC.  
  
13. El **operaciones en el contrato seleccionado** cuadro muestra las operaciones que seleccionó para cada artefacto en la página Elija operaciones.  
  
14. En el **configurar el enlace para el contrato y dirección** , especifique los siguientes valores:  
  
    |Para la propiedad|Especifique el valor|  
    |----------------------|-----------------------|  
    |Configuración de enlace|El Asistente solo admite el enlace HTTP básico. Por lo tanto, se rellena automáticamente el campo de la configuración de enlace a *System.ServiceModel.Configuration.BasicHttpBindingElement*.<br /><br /> Haga clic en el botón de puntos suspensivos **(...)**  para cambiar las propiedades para el enlace HTTP. Para utilizar un canal de comunicación seguro, siempre se debe establecer el **modo** propiedad **transporte**. El asistente establece el valor predeterminado para el **modo** propiedad como **transporte**.<br /><br /> Para obtener más información acerca de los otros enlaces expone, consulte "BasicHttpBindingElement miembros" en [ http://go.microsoft.com/fwlink/?LinkId=103773 ](http://go.microsoft.com/fwlink/?LinkId=103773).|  
    |Nombre de extremo|Especifique un nombre de punto de conexión para el contrato.|  
  
     Los demás campos de esta página se rellenan automáticamente según los valores especificados en las páginas anteriores.  
  
     Haga clic en **Aplicar**. Realice este paso para todos los contratos que se muestra bajo la **seleccione un contrato para configurar** cuadro.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en esta página, se aceptan los valores predeterminados para todos los contratos.  
  
     La siguiente ilustración muestra la página de dirección con los valores especificados y configurar el enlace de punto de conexión de servicio.  
  
     ![Configurar el enlace del punto de conexión de servicio y dirección](../../adapters-and-accelerators/adapter-sap/media/356e297c-9893-494c-a834-9d0b8b42da2e.gif "356e297c-9893-494c-a834-9d0b8b42da2e")  
  
15. En la página Configurar el enlace de punto de conexión de servicio y la dirección, haga clic en **siguiente**.  La página de resumen muestra una estructura de árbol de los artefactos SAP y, debajo de eso, las operaciones seleccionadas para cada artefacto.  
  
16. Revise el resumen y, a continuación, haga clic en **finalizar**.  
  
17. El asistente crea un servicio WCF y agrega los archivos siguientes en el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto:  
  
    1.  archivo .svc. Este es el archivo de servicio WCF. El asistente genera un archivo para cada contrato.  
  
    2.  Archivo Web.config.  
  
    3.  Código de servicio (archivo. cs)  
  
18. Publicar el servicio WCF.  
  
    1.  Asegúrese de que SSL está habilitado para Internet Information Services (IIS). Para obtener instrucciones sobre cómo habilitar SSL para IIS, consulte [ http://go.microsoft.com/fwlink/?LinkId=197170 ](http://go.microsoft.com/fwlink/?LinkId=197170).  
  
    2.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **publicar**.  
  
    3.  En el **publicación Web** cuadro de diálogo, especifique una dirección URL para el servicio WCF. Por ejemplo:  
  
        ```  
        https://<computer_name>/Customer_Order/  
        ```  
  
    4.  Desde el **copia** cuadro, haga clic en **todos los archivos de proyecto**.  
  
    5.  Haga clic en **Publicar**.  
  
19. Compruebe que el servicio de WCF se publicó correctamente.  
  
    1.  Inicie la consola de administración de Microsoft IIS. Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
    2.  Desplácese hasta el nodo donde se publica el servicio. Para el **Customer_Order** de servicio, vaya a **Internet Information Services** > **\<nombre_equipo\>**   >  **Sitios Web** > **sitio Web predeterminado** > **Customer_Order**.  
  
    3.  En el panel derecho, haga clic en el archivo Rfc.svc y, a continuación, haga clic en **examinar**.  
  
    4.  Aparece la página Web con la dirección URL para recuperar el WSDL. Desea probar la recuperación de metadatos mediante el **svcutil** comando. Por ejemplo, el comando para recuperar los metadatos del servicio Customer_Order es:  
  
        ```  
        svcutil.exe https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>Paso siguiente  
 Para crear un archivo de definición de aplicación para los artefactos SAP, use el Editor de definición del catálogo de datos profesionales. Consulte [paso 2: crear un archivo de definición de aplicación para los artefactos de SAP](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) para obtener instrucciones. El archivo de definición de la aplicación identifica dónde se almacenan los datos LOB y el formato en el que se almacena.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentación de datos de un sistema de SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)