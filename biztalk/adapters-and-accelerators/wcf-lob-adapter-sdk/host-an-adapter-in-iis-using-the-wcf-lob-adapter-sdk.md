---
title: Hospedar un adaptador en IIS mediante el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90b6cd97-01b3-4c98-a190-c6e0ccf24d2b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 570c844b7e41c8fd4deb340e6a0ce1bf598ae24b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976141"
---
# <a name="host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk"></a>Hospedar un adaptador en IIS mediante el SDK de adaptador LOB de WCF
Esta sección contiene información sobre cómo hospedar un adaptador creado mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] en Internet Information Services (IIS). Para obtener más información sobre otras opciones de hospedaje, vea [servicios de hospedaje](https://msdn.microsoft.com/library/ms730158.aspx).

## <a name="use-iis-and-aspnet"></a>Usar IIS y ASP.NET
 Puede utilizar IIS con ASP.NET habilitado para publicar los adaptadores que se crea con el SDK de adaptador LOB de WCF. Para hospedar un adaptador creado por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], configure Internet Information Services (IIS) para publicar servicios WCF. A continuación, considere cómo usar su adapterwith ASP.NET de WCF.

 Al hospedar un servicio WCF en IIS, hay dos modos de hospedaje: **side-by-side** y**modo de compatibilidad SP.NET**. El modo de hospedaje predeterminado es en paralelo. Modo Side-by-side se comporta de forma coherente con otra soluciones de hospedaje de WCF. Por lo tanto, un servicio WCF hospedado en IIS comporta igual que una hospedada en una aplicación de consola. Sin embargo, esto puede no ser deseable porque los desarrolladores web podrían esperan un comportamiento similar a ASP.NET. Por ejemplo, en el modo en paralelo, WCF no se adhiere a ninguna regla de autorización basada en la dirección URL especificada en el `<system.web> <authorization>` elemento de configuración del archivo web.config.  

 Modo de compatibilidad ASP.NET permite que el servicio WCF para usar todas las características de ASP.NET y se comportan igual que una página. ASPX. Sin embargo, debe realizar pasos adicionales al crear el adaptador WCF para habilitar esta funcionalidad. Para obtener más información, vea: 

 [Servicios WCF y ASP.NET](https://msdn.microsoft.com/library/aa702682.aspx)

[Hospedaje en Internet Information Services](https://msdn.microsoft.com/library/ms734710.aspx)

[Servicios de hospedaje de WCF](https://msdn.microsoft.com/library/ms730158.aspx)

## <a name="use-the-wcf-adapter-service-development-wizard"></a>Utilice al Asistente para desarrollo de servicio de adaptador WCF

Use el [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)] para automatizar la creación de un proyecto Web para hospedar el adaptador dentro de Internet Information Services (IIS). El adaptador hospedado, a continuación, puede utilizarse en los clientes que usan Windows Communication Framework (WCF) o servicios Web.  

### <a name="publish-an-adapter-as-a-wcf-service-hosted-in-iis"></a>Publicar un adaptador como un servicio WCF hospedado en IIS  

1. Abra [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]. En el **archivo** menú, seleccione **New**y, a continuación, seleccione **sitio Web**.  

2. En **plantillas**, seleccione **Visual C#** y seleccione **servicio de adaptador de WCF**.  

3. Especifique la carpeta para guardar la solución y, a continuación, seleccione **Aceptar**. El **Asistente para desarrollo del servicio de adaptador de WCF** se inicia.  

4. En el **Introducción** página, haga clic en **siguiente**.  

5. En el **elija operaciones** , especifique el enlace, contrato y operaciones que se utilizará para este servicio hospedado.  

   1.  En el **selecciona un enlace** lista, seleccione el enlace del adaptador para usar y, a continuación, haga clic en **configurar**. Esto muestra la **configurar el adaptador** cuadro de diálogo. Proporcione los valores necesarios para invocar el adaptador y para recuperar los metadatos de la operación.  

   2.  En el **seguridad** ficha, seleccione el **tipo de credencial de cliente** debe utilizarse al pasar las credenciales del cliente para el adaptador.  

       |Tipo de credencial|Descripción|  
       |---------------------|-----------------|  
       |**Ninguno**|El cliente no necesita presentar credenciales.|  
       |**Windows**|El cliente usará las credenciales de Windows.|  
       |**Nombre de usuario**|El cliente proporcionará un nombre de usuario y una contraseña.|  
       |**Certificado**|El cliente se autenticará con un certificado X.509. Si se establece este valor, haga clic en **examinar** en el **certificado de cliente** área y, a continuación, seleccione el certificado que se usará.|  

   3.  En el **propiedades de URI** ficha, especifique los parámetros URI requeridos por el adaptador. Las entradas se muestran en esta ficha varían en función de las propiedades expuestas en la `ConnectionUri Properties` clase del adaptador.  

   4.  En el **propiedades de enlace** ficha, especifique valores para las propiedades de enlace necesarias para el adaptador. El **General** sección contiene las opciones comunes, como los valores de tiempo de espera. Propiedades adicionales se muestran en función de las propiedades personalizadas expuestas en su `AdapterBinding` clase.  

6. Una vez que ha especificado los valores de configuración, haga clic en **Connect**.  

   1.  Desde el **seleccione el tipo de contrato** lista, seleccione el contrato para utilizar. Esto rellena el **seleccionar una categoría** árbol de control con una lista de categorías y operaciones disponibles desde este adaptador. Si el adaptador implementa la funcionalidad de búsqueda a través de un `MetadataRetrievalClient` (clase), puede escribir un término de búsqueda en el **búsqueda en la categoría** campo para devolver sólo las categorías y las operaciones que contienen el término de búsqueda.  

       > [!NOTE]
       >  Solo las operaciones de salida están disponibles para la selección.  

   2.  Desde el **operaciones y categorías disponibles** , seleccione los elementos para agregar y, a continuación, haga clic en **agregar**. Cuando haya agregado los elementos deseados, haga clic en **siguiente**.  

7. En el **configurar el servicio y los comportamientos de extremo** , establezca el comportamiento deseado para este adaptador.  

   1.  El **configuración del comportamiento de servicio** sección contiene entradas que controlan el comportamiento del servicio. Después de ejecutar al asistente, puede modificar los comportamientos de servicio seleccionados, edite el archivo web.config.  

       |Property|Descripción|  
       |--------------|-----------------|  
       |**EnableMetadataExchange**|Establecer este valor en **True** permite la publicación de metadatos para las solicitudes de cliente de servicio. También puede establecerse mediante la modificación de \< **httpGetEnabled serviceMetadata = ""** \> en el archivo web.config. El valor predeterminado es **False**|  
       |**IncludeExceptionDetailsinFault**|Establecer este valor en **True** devuelven resultados en la información de excepción administrada al cliente en errores de SOAP. También puede establecerse mediante la modificación de \< **serviceDebug usingincludeExceptionDetailInFaults = ""** \> en el archivo web.config. El valor predeterminado es **False**.|  
       |**Nombre**|Nombre de la configuración de comportamiento de servicio.|  
       |**UseServiceCertificate**|Este valor determina si el servicio usará un certificado X.509 para autenticarse en el proceso del cliente. El valor predeterminado es **True**.|  
       |**FindValue**|Este valor se utiliza para buscar un certificado X.509 concreto en el almacén de certificados. También puede establecerse mediante la modificación de \< **serviceCredentials findValue = ""** \> en el archivo web.config **Nota:** especifica un valor para esta propiedad sólo si  **UseServiceCertificate** está establecido en **True**.|  
       |**StoreLocation**|Este valor especifica la ubicación del almacén del sistema para buscar el certificado especificado. También puede establecerse mediante la modificación de \< **serviceCredentials storeLocation = ""** \> en el archivo web.config. **Nota:** especifica un valor para esta propiedad sólo si **UseServiceCertificate** está establecido en **True**.|  
       |**StoreName**|Este valor especifica el almacén del sistema específicos para buscar el certificado especificado. También puede establecerse mediante la modificación de \< **serviceCredentials storeName = ""** \> en el archivo web.config **Nota:** especifica un valor para esta propiedad sólo si  **UseServiceCertificate** está establecido en **True**.|  
       |**X509FindType**|El tipo de búsqueda que se utiliza con FindValue especificado anteriormente con el fin de encontrar el certificado específico. También puede establecerse mediante la modificación de \< **serviceCredentials x509FindType = ""** \> en el archivo web.config **Nota:** especifica un valor para esta propiedad sólo si  **UseServiceCertificate** está establecido en **True**.|  

   2.  El **configuración del comportamiento de punto de conexión** sección controla el comportamiento del extremo.  

       |Property|Descripción|  
       |--------------|-----------------|  
       |**Nombre**|El nombre del comportamiento del extremo|  
       |**AuthenticationType**|Este valor indica que el adaptador a dónde obtener al cliente las credenciales del documento entrante. Para permitir que los clientes especificar un certificado de cliente para autenticarse en el servicio, establezca esta opción en **ClientCredentialUsernamePassword**. Para permitir que los clientes especificar el nombre de usuario y la contraseña como parte del encabezado HTTP, establezca esta opción en **HTTPUsernamePassword**. Para permitir que los clientes especificar las credenciales a través de la interfaz ClientCredential, establezca esta opción en **automática**. Si se produce un error, los clientes pueden pasar credenciales como parte del encabezado HTTP.<br /><br /> También se puede establecer este valor modificando \< **endpointBehavior adapterSecurityBridgeType** \> en el archivo web.config. El valor predeterminado es **automática**.|  
       |**UsernameHeader**|Especifica el nombre del encabezado que se usará para pasar el nombre de usuario al servicio. Para obtener más información acerca de los encabezados HTTP, vea "Compatibilidad con los encabezados HTTP personalizados y de SOAP" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> También se puede establecer este valor modificando \< **endpointBehavior usernameHttpHeader** \> en el archivo web.config. **Nota:** debe especificar un valor para esta propiedad si el **AuthenticationType** está establecido en **HTTPUserNamePassword**.  Si establece en **automática**, esta propiedad es opcional.|  
       |**PasswordHeader**|Especifica el nombre del encabezado que se usará para pasar la contraseña del usuario al servicio. Para obtener más información acerca de los encabezados HTTP, vea "Soporte técnico para Custom HTTP y SOAP Headers" en [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> También se puede establecer este valor modificando <**passwordHttpHeader endpointBehavior**< en el archivo web.config. **Nota:** debe especificar un valor para esta propiedad si el **AuthenticationType** está establecido en **HTTPUserNamePassword**. Si establece en **automática**, esta propiedad es opcional.|  

   3.  Después de establecer el comportamiento deseado, haga clic en **siguiente** para continuar.  

8. En el **configurar enlace de punto de conexión de servicio y dirección** página, puede configurar las propiedades de enlace y dirección para los contratos. Seleccione el contrato en el **seleccione un contrato para configurar** lista y, a continuación, escriba los valores deseados en el **configurar el enlace para el contrato y dirección** cuadro de diálogo.  

   1.  Seleccione el **BindingConfiguration** entrada en las propiedades de enlace. El Asistente solo admite enlace básico HTTP, por lo que el campo de la configuración de enlace se establece automáticamente en **System.ServiceModel.Configuration.BasicHttpBindingElement**. Para cambiar las propiedades de configuración para este enlace, haga clic en el botón de puntos suspensivos **...** . Para utilizar un canal de comunicación seguro, siempre se debe establecer el **modo** propiedad **transporte**. Este es el valor predeterminado.  

   2.  Seleccione el **EndpointName**y, a continuación, escriba el nombre deseado del punto de conexión.  

   3.  Para aplicar los cambios, haga clic en **aplicar**.  

9. Para continuar, haga clic en **Siguiente**. La página de resumen muestra una estructura de árbol de las operaciones del adaptador que se seleccionaron.  

10. Revise el resumen y, a continuación, haga clic en **finalizar**.  

11. El asistente crea un proyecto Web y agrega los siguientes archivos.  


    |    Archivo    |                                                Descripción                                                 |
    |------------|------------------------------------------------------------------------------------------------------------|
    |    .svc    |                               Archivo de servicio que hace referencia al proxy de WCF.                               |
    |    .cs     |                                         Implementa al proxy WCF.                                          |
    | web.config | Contiene \< **extremo** \, \< **enlaces**\>, y \< **comportamientos** \>elementos para \< **sistema. ServiceModel**\> |


12. Publique el proyecto de servicio WCF.  

    1.  Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **publicar**.  

    2.  En el **Publicar sitio Web** cuadro de diálogo, especifique la dirección URL de destino para el servicio WCF.  

    3.  Seleccione **permitir que este sitio precompilado se actualice**.  

    4.  Seleccione **uso se ha corregido la nomenclatura y solo ensamblados de página**.  

    5.  Seleccione **Habilitar nombre seguro en los ensamblados precompilados**y, a continuación, especifique la clave de firma para usar.  

13. Para publicar el sitio Web, haga clic en **Aceptar**.  

14. Compruebe que el servicio se ha publicado correctamente.  

    1.  Inicie la consola de administración de IIS.  Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services**.  

    2.  Desplácese hasta el nodo donde se publica el servicio.  Si el servicio se ha publicado como http://localhost/myservice, vaya a **Internet Information Services**> **nombre_equipo**> **sitios Web** >  **Sitio Web predeterminado**> **myservice**.  

    3.  En el panel derecho, haga clic en el archivo .svc y, a continuación, haga clic en **examinar**. Aparece la página Web con información sobre el servicio. Ahora puede consumir este servicio mediante el uso de llamadas de servicio WCF o Web desde aplicaciones cliente. 

## <a name="security"></a>Seguridad
Cuando el adaptador está alojado dentro de un servicio, llamadas desde aplicaciones cliente usar el puente de seguridad del adaptador para pasar las credenciales del cliente al adaptador.  

 Cuando un cliente WCF envía autenticación a un servicio WCF, normalmente el servicio utiliza la autenticación. Sin embargo, en el caso de un adaptador, la idea es capturar la información de autenticación para su uso con el sistema LOB subyacente. Esto se implementa a través del puente de seguridad del adaptador, que aparece como un comportamiento del extremo. Como programador de adaptadores, que no hay nada que debe implementarse para poder aprovechar esta funcionalidad; Sin embargo, al implementar el adaptador, debe considerar cómo el cliente va a proporcionar credenciales para el servicio.  

 Si usa seguridad de nivel de mensaje, el puente de seguridad del adaptador puede recuperar el ClientCredentials enviado por la aplicación cliente en cualquier enlace. Si está utilizando el enlace básico HTTP, en su lugar puede seleccionar usar un encabezado personalizado para pasar la información de nombre y la contraseña del usuario. Se recomienda utilizar la clase ClientCredential proporcionada por WCF para pasar las credenciales, pero muchas aplicaciones de cliente de servicio Web se deben utilizar un encabezado personalizado para pasar las credenciales.  

 El siguiente es un ejemplo de configuración donde el adaptador busca las credenciales en el objeto ClientCredentials que proporciona la aplicación cliente. Si se encuentra ninguno, el adaptador, a continuación, se busca en los encabezados de solicitud HTTP que se especifican.  

```  
<endpointBehaviors>  
   <behavior name="customEndpointBehavior">  
      <endpointBehavior usernameHttpHeader="UNHdr" passwordHttpHeader="PWHdr"  
         adapterSecurityBridgeType="Auto" />  
    </behavior>  
</endpointBehaviors>  
```      

## <a name="see-also"></a>Vea también  
 [Actividades de desarrollo](../../esb-toolkit/development-activities.md)