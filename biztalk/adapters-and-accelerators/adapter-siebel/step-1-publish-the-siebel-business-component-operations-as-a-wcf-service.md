---
title: 'Paso 1: Publicar las operaciones de componentes empresariales de Siebel como un servicio WCF | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acfa0c36-50f1-45c1-9fc2-e5e5cedaa6a0
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 800e9789eca1121abd37de4df92e9d5e735802f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983021"
---
# <a name="step-1-publish-the-siebel-business-component-operations-as-a-wcf-service"></a>Paso 1: Publicar las operaciones de componentes empresariales de Siebel como un servicio WCF
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** puede usar el Asistente para desarrollo de servicio de adaptador de WCF para generar un servicio WCF que se puede hospedar en un entorno de hospedaje, como Internet Information Services (IIS) o servicio de activación de proceso de Windows (WAS). En este tema se muestra cómo usar al Asistente para generar un archivo de servicio WCF.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar al asistente, instale lo siguiente:  
  
- [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ya sea con la **completar** opción o el **personalizado** opción (y eligiendo **herramientas** dentro de esta opción). Esto instala la plantilla de Visual Studio para el Asistente para desarrollo de servicio de adaptador de WCF.  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]  
  
- El cliente de Siebel.  
  
  Para obtener más información sobre estos requisitos previos, consulte el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación. La Guía de instalación se instala normalmente en \<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
## <a name="publish-the-siebel-business-components-as-a-wcf-service"></a>Publicar los componentes empresariales de Siebel como un servicio WCF  
  
1. Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y, a continuación, cree un proyecto.  
  
2. En el **nuevo proyecto** cuadro de diálogo desde el **tipos de proyecto** panel, seleccione **Visual C#**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
    Como alternativa, desde el **tipos de proyecto** panel, expanda **Visual C#** y, a continuación, seleccione **Web**. Desde el **plantillas** panel, seleccione **servicio de adaptador de WCF**.  
  
   > [!NOTE]
   >  Si ha instalado Visual Studio con el componente de desarrollo Web, el **servicio de adaptador de WCF** plantilla también está disponible en el **nuevo sitio Web** opción.  
  
3. Especifique un nombre y ubicación de la solución y, a continuación, haga clic en **Aceptar**. Se inicia el Asistente para desarrollo de servicio de adaptador de WCF.  
  
4. En la página de bienvenida, haga clic en **siguiente**.  
  
5. En la página Elija operaciones, especifique una cadena de conexión para conectarse al sistema Siebel. Para ello:  
  
   1. En el **selecciona un enlace** lista, haga clic en **siebelBinding**y, a continuación, haga clic en **configurar**.  
  
   2. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
   3. En el **tipo de credencial de cliente** lista, seleccione **Username**y, a continuación, especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.  
  
   4. Haga clic en el **propiedades de URI** pestaña y, a continuación, especifique valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [crear el URI de conexión del sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  
  
      > [!NOTE]
      >  Si los parámetros de conexión contienen caracteres reservados (por ejemplo, caracteres especiales XML), deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  
  
   5. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, necesarios para las operaciones de destino.  
  
       Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
   6. Haga clic en **Aceptar**y, a continuación, haga clic en **Connect**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
6. En la página Elegir las operaciones, en la **tipo de contrato Select** lista, haga clic en **Client (Outbound operations)**.  
  
7. En el **seleccionar una categoría** , expanda el Siebel **objetos de negocios** nodo para ver la lista de objetos comerciales en el repositorio de Siebel. En este ejemplo, realice lo siguiente:  
  
   1.  Expanda el **cuenta** objeto comercial y, a continuación, haga clic en el **cuenta** componente empresarial.  
  
   2.  En el **operaciones y categorías disponibles** cuadro, seleccione el **consulta** operación y, a continuación, haga clic en **agregar**. La operación seleccionada aparece en el **agregar categorías y operaciones** cuadro.  
  
        ![Seleccione las operaciones de componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/media/ed0cb649-dc4d-49ce-9541-c491c9cc9ac9.gif "ed0cb649-dc4d-49ce-9541-c491c9cc9ac9")  
  
8. En la página Elija operaciones, haga clic en **siguiente**.  
  
9. En la página Configurar el servicio y los comportamientos de extremo, especifique valores para configurar el comportamiento de servicio y el punto de conexión.  
  
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
      >  Para obtener más información acerca de los certificados y las propiedades asociadas, consulte [X509ClientCertificateCredentialsElement propiedades](https://msdn.microsoft.com/library/system.servicemodel.configuration.x509clientcertificatecredentialselement_properties.aspx).
  
   2. En el **configuración del comportamiento de punto de conexión** , especifique los siguientes valores:  
  
      |Para la propiedad|Especifique el valor|  
      |----------------------|-----------------------|  
      |Tipo de autenticación|: Establezca esta opción en **ClientCredentialUserNamePassword** para permitir que los clientes especificar el nombre de usuario y la contraseña al utilizar el servicio WCF.<br /><br /> : Establezca esta opción en **HTTPUserNamePassword** para permitir que los clientes especificar el nombre de usuario y contraseña como parte del encabezado HTTP.<br /><br /> : Establezca esta opción en **automática** primero habilite los clientes especificar credenciales a través de la **ClientCredential** interfaz. Si se produce un error, los clientes pueden pasar credenciales como parte del encabezado HTTP.<br /><br /> El valor predeterminado es **automática**. Para que Microsoft Office SharePoint Server consumir el servicio WCF, debe establecer esto como **HTTPUserNamePassword**.|  
      |Nombre|Especifique un nombre para la configuración de comportamiento de punto de conexión.|  
      |UsernameHeader|Nombre para el encabezado de nombre de usuario. En este ejemplo, especificar **MyUserHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
      |PasswordHeader|Nombre de encabezado de la contraseña. En este ejemplo, especificar **MyPassHeader**. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692).<br /><br /> **Nota:** debe especificar un valor para esta propiedad si el **tipo de autenticación** está establecido en **HTTPUserNamePassword**. Si **tipo de autenticación** está establecido en **automática**, esta propiedad es opcional.|  
  
      En la siguiente ilustración muestra la página Configurar el servicio y los comportamientos de punto de conexión con los valores especificados.  
  
      ![Configurar la página de servicio y los comportamientos de extremo](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
10. En la página Configurar el servicio y los comportamientos de extremo, haga clic en **siguiente**.  
  
11. En la página Configurar el enlace de punto de conexión de servicio y la dirección, el **seleccione un contrato para configurar** cuadro muestran los contratos para los componentes empresariales de Siebel para el que ha seleccionado las operaciones en la página Elija operaciones. El **operaciones en el contrato seleccionado** cuadro muestra las operaciones que seleccionó para cada artefacto en la página Elija operaciones.  
  
12. En el **configurar el enlace para el contrato y dirección** , especifique los siguientes valores:  
  
    |Para la propiedad|Especifique el valor|  
    |----------------------|-----------------------|  
    |Configuración de enlace|El Asistente solo admite el enlace HTTP básico. Por lo tanto, se rellena automáticamente el campo de la configuración de enlace a *System.ServiceModel.Configuration.BasicHttpBindingElement*.<br /><br /> Haga clic en el botón de puntos suspensivos **(...)**  para cambiar las propiedades para el enlace HTTP. Para utilizar un canal de comunicación seguro, siempre se debe establecer el **modo** propiedad **transporte**. El asistente establece el valor predeterminado para el **modo** propiedad como **transporte**.<br /><br /> Para obtener más información acerca de los otros enlaces expone, consulte [BasicHttpBindingElement clase](https://msdn.microsoft.com/library/system.servicemodel.configuration.basichttpbindingelement.aspx).|  
    |Nombre de extremo|Especifique un nombre de punto de conexión para el contrato.|  
  
     Los demás campos de esta página se rellenan automáticamente según los valores especificados en las páginas anteriores.  
  
     Haga clic en **Aplicar**. Realice este paso para todos los contratos que se muestra bajo la **seleccione un contrato para configurar** cuadro.  
  
    > [!NOTE]
    >  Si no especifica ningún valor en esta página, se aceptan los valores predeterminados para todos los contratos.  
  
     La siguiente ilustración muestra la página de dirección con los valores especificados y configurar el enlace de punto de conexión de servicio.  
  
     ![Configurar el enlace del punto de conexión de servicio y dirección](../../adapters-and-accelerators/adapter-siebel/media/467d3e18-027d-4218-9d72-0740c1f559e3.gif "467d3e18-027d-4218-9d72-0740c1f559e3")  
  
13. En la página Configurar el enlace de punto de conexión de servicio y la dirección, haga clic en **siguiente**. La página de resumen muestra una estructura de árbol de los contratos para los componentes empresariales de Siebel seleccionados y, debajo de eso, las operaciones seleccionadas para cada componente empresarial.  
  
14. Revise el resumen y, a continuación, haga clic en **finalizar**.  
  
15. El asistente crea un servicio WCF y agrega los archivos siguientes en el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto:  
  
    1.  archivo .svc. Este es el archivo de servicio WCF. El asistente genera un archivo para cada contrato.  
  
    2.  Archivo Web.config.  
  
    3.  Código de servicio (archivo. cs).  
  
16. Publicar el servicio WCF.  
  
    1.  Asegúrese de que SSL está habilitado para Internet Information Services (IIS). Consulte [cómo configurar SSL](https://docs.microsoft.com/iis/manage/configuring-security/how-to-set-up-ssl-on-iis).
  
    2.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **publicar**.  
  
    3.  En el **publicación Web** cuadro de diálogo, especifique una dirección URL para el servicio WCF. Por ejemplo:  
  
        ```  
        https://<computer_name>/Siebel_Account/  
        ```  
  
    4.  Desde el **copia** cuadro, haga clic en **todos los archivos de proyecto**.  
  
    5.  Haga clic en **Publicar**.  
  
17. Compruebe que el servicio de WCF se publicó correctamente.  
  
    1.  Inicie la consola de administración de Microsoft IIS. Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services**.  
  
    2.  Desplácese hasta el nodo donde se publica el servicio. Para el **Siebel_Account** de servicio, vaya a **Internet Information Services** > **\<nombre_equipo\>**   >  **Sitios Web** > **sitio Web predeterminado** > **Siebel_Account**.  
  
    3.  En el panel derecho, haga clic en el archivo BusinessObjects_Account_Account_Operation.svc y, a continuación, haga clic en **examinar**.  
  
    4.  Aparece la página Web con la dirección URL para recuperar el WSDL. Desea probar la recuperación de metadatos mediante el comando svcutil. Por ejemplo, el comando para recuperar los metadatos del servicio Siebel_Account es:  
  
        ```  
        svcutil.exe https://localhost/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
        ```  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora tiene un servicio WCF para el componente de negocio de Siebel. Utilice el Editor de definición del catálogo de datos profesionales para crear un archivo de definición de aplicación para las operaciones de componentes empresariales de Siebel. Consulte [paso 2: crear un archivo de definición de aplicación para operaciones de componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md) para obtener instrucciones. El archivo de definición de la aplicación identifica dónde se almacenan los datos LOB y el formato en el que se almacena.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Presentación de datos de un sistema de Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)