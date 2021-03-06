---
title: Cómo configurar los servicios WCF publicados con el Asistente para publicar el servicio de WCF de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Publishing Wizard
- WCF services, configuring
- configuring, WCF services
- WCF Service Publishing Wizard
ms.assetid: f51b86c0-8c19-453d-a66d-3f373e9f096e
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21009f82632140156957a831a40bcbf4c65982ee
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752932"
---
# <a name="how-to-configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard"></a>Cómo configurar los servicios WCF publicados con el Asistente para publicación de Servicio WCF de BizTalk
Una vez que ha publicado los servicios WCF con el Asistente para publicación de Servicio WCF de BizTalk, debe configurarlos adecuadamente. En este tema se describe cómo configurar los servicios WCF publicados.  

> [!NOTE]
>  Debe crear los proyectos de BizTalk y publicarlos mediante la ejecución del Asistente para publicación de Servicio WCF de BizTalk. Para obtener más información sobre cómo usar el Asistente para publicación de servicio WCF de BizTalk, consulte [cómo usar el Asistente de publicación para servicio de WCF de BizTalk para publicar orquestaciones como servicios WCF](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md) y [cómo usar el servicio de WCF de BizTalk Asistente para publicar esquemas como servicios WCF de publicación](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md).  

### <a name="to-configure-the-receive-locations-for-a-published-wcf-service"></a>Para configurar las ubicaciones de recepción un Servicio WCF publicado  

1. Publique el proyecto de BizTalk mediante la ejecución del Asistente para publicación de Servicio WCF de BizTalk.  

2. Si no ha seleccionado la **ubicaciones de recepción de BizTalk cree** en la siguiente ilustración al crear el servicio WCF, cree un nuevo puerto de recepción y ubicación de recepción para el servicio WCF publicado y, a continuación, seleccione el adaptador WCF para el tipo de transporte que va a usar la ubicación de recepción. Debe seleccionar el mismo adaptador WCF que se ha seleccionado en el **tipo de servicio WCF** página que se muestra en la ilustración siguiente. Para obtener más información acerca de cómo crear una ubicación de recepción, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  

   > [!NOTE]
   >  El Asistente para publicación de Servicio WCF de BizTalk crea un archivo de enlace, BindingInfo.xml, en la carpeta \App_Data\Temp del directorio Web del Servicio WCF publicado (archivo .svc). Si selecciona el **ubicaciones de recepción de BizTalk cree** opción, el asistente usa el archivo de enlace para crear la ubicación de recepción. En la consola de administración de BizTalk Server, puede importar este archivo de enlace para crear la ubicación de recepción de forma manual. Para obtener más información sobre cómo importar un archivo de enlace, consulte [importar enlaces](../core/importing-bindings2.md).  

    ![Página tipo de servicio WCF](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  

3. Si es necesario, abra la consola de administración de BizTalk Server como sigue: haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk Server**y, a continuación, haga clic en  **Administración de BizTalk Server**.  

4. En el árbol de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda la aplicación donde el servicio WCF generado debe estar colocado, expanda **ubicaciones de recepción**y, a continuación, haga doble clic en la ubicación de recepción para el servicio WCF.  

5. En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **configurar**.  

6. Si la ubicación de recepción aloja el adaptador WCF-BasicHttp o de WCF-WSHttp, en el **propiedades de transporte** cuadro de diálogo, haga clic en el **seguridad** pestaña y, a continuación, configure las propiedades de seguridad en la pestaña. Si la ubicación de recepción aloja el adaptador WCF-CustomIsolated, en el **propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** pestaña y, a continuación, configure la información de enlace en la pestaña.  

    ![La ficha seguridad de WCF&#45;adaptador BasicHttp](../core/media/585ecdad-bdee-40c0-b2f1-7ace74d503e5.gif "585ecdad-bdee-40c0-b2f1-7ace74d503e5")  

   > [!NOTE]
   >  La propiedad de tipo de credenciales de cliente de transporte correspondiente al adaptador de WCF aislado debe coincidir con el esquema de autenticación del directorio virtual de Servicios de Internet Information Server (IIS) que aloja esta ubicación de recepción. Por ejemplo, si la propiedad está establecida en **Windows**, también deberá habilitar **autenticación de Windows integrada** para el directorio virtual que aloja esta ubicación de recepción. De forma parecida, si la propiedad está establecida como **Ninguna**, debe permitir el acceso anónimo al directorio virtual que aloja esta ubicación de recepción. Para obtener más información sobre cómo configurar las propiedades de seguridad para los adaptadores de WCF-BasicHttp y WCF-WSHttp, consulte [cómo configurar una ubicación de recepción WCF-BasicHttp](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd), y [cómo configurar una recepción de WCF-WSHttp Ubicación](../core/how-to-configure-a-wcf-wshttp-receive-location.md). Para obtener más información sobre cómo configurar la información de enlace, consulte [cómo configurar una ubicación de recepción WCF-CustomIsolated](../core/how-to-configure-a-wcf-customisolated-receive-location.md).  

7. Si no ha seleccionado la **ubicaciones de recepción de BizTalk cree** opción al crear el WCF services, en el **propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha. En el **General** pestaña, escriba el URI para esta ubicación de recepción en el **dirección** cuadro de texto. Indique el directorio virtual, así como el nombre del archivo .svc que el Asistente para publicación de Servicio WCF de BizTalk ha generado en el procedimiento anterior; por ejemplo /path/service.svc.  

   > [!NOTE]
   >  El **dirección** propiedad debe empezar por una barra diagonal ("/") y terminan en ".svc". El **dirección** propiedad no debe contener un esquema de protocolo, el nombre del equipo o el número de puerto como http://host:port. Sólo se puede usar la ruta de acceso del directorio virtual. La extensión del archivo de marcado del Servicio WCF debe ser .svc.  

    ![La pestaña General de WCF&#45;adaptador BasicHttp](../core/media/1126fa6a-e3e9-44ad-aeb0-90c78226aeeb.gif "1126fa6a-e3e9-44ad-aeb0-90c78226aeeb")  

8. Si seleccionó **transporte** o **TransportWithMessageCredential** en el **modo de seguridad** lista desplegable en el **seguridad** pestaña los adaptadores de WCF-BasicHttp y WCF-WSHttp, debe establecer la seguridad de capa de Sockets seguros (SSL) en IIS. Si establece la **transporte** o **TransportWithMessageCredential** modo de seguridad de la información de enlace para el adaptador de WCF-CustomIsolated, debe también configurar SSL en IIS.  

9. Si la ubicación de recepción aloja el adaptador WCF-BasicHttp o de WCF-WSHttp, en el **propiedades de transporte** diálogo cuadro, configure el **General**, **enlace**y **Mensajes** pestañas si es necesario. Si la ubicación de recepción aloja el adaptador de WCF-CustomIsolated, configure el **General**, **comportamiento**, **otros**, y **mensajes** pestañas para un fin determinado. Para el adaptador WCF-CustomIsolated, puede importar el **dirección (URI)** y **identidad de extremo** propiedades en el **General** ficha, enlace información sobre la **Enlace** ficha y los comportamientos de la **comportamiento** ficha para esta ubicación de recepción de un archivo de configuración.  

10. Habilite la ubicación de recepción para el Servicio WCF publicado mediante la consola de administración de BizTalk Server. Para obtener más información sobre cómo habilitar la ubicación de recepción, vea [cómo habilitar una ubicación de recepción](../core/how-to-enable-a-receive-location.md).  

    > [!NOTE]
    >  Las ubicaciones de recepción están deshabilitadas cuando se crean. Después de crear ubicaciones de recepción con el asistente de Servicio WCF de BizTalk Server, debe habilitar las ubicaciones de recepción.  

11. Configure, mediante la consola de administración de IIS, el grupo de aplicaciones IIS para alojar la ubicación de recepción para el Servicio WCF publicado. Para obtener más información sobre cómo configurar el grupo de aplicaciones para los adaptadores WCF aislados, consulte [configurar IIS para los adaptadores de recepción WCF aislados](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).  

12. Abra un símbolo del sistema, vaya a la carpeta donde el Asistente publicación del servicio de WCF de BizTalk Server crea el servicio de WCF en %SystemDrive%\InetPub\\y, a continuación, abra el archivo Web.config mediante el Bloc de notas.  

13. En el Bloc de notas, agregue la siguiente línea dentro de la **\<system.web\>** elemento:  

    ```  
    <trust level="Full" originUrl="" />  
    ```  

    > [!NOTE]
    >  Esta configuración es opcional y concede a la aplicación ASP.NET que aloja el Servicio WCF publicado acceso a cualquier recurso que dependa de la seguridad del sistema operativo. Este es el nivel de confianza que WCF requiere cuando tiene Windows SharePoint Services instalado y ejecutándose en el mismo equipo con los servicios WCF publicados.  

14. En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para el servicio WCF con el formato http://<em>host [: puerto]</em>/*apppath* / *wcfservicename.svc* para probar el servicio WCF publicado. Los parámetros se describen en la siguiente tabla.  


    |      Parámetro       |                                                            Valor                                                            |
    |----------------------|-----------------------------------------------------------------------------------------------------------------------------|
    |    *host [: puerto]*     | El nombre del equipo en el que ha implementado el Servicio WCF. Este nombre de servidor puede ir seguido de dos puntos y el número de puerto. |
    |      *AppPath*       |                              El nombre del directorio virtual y la ruta de aplicación Web.                               |
    | *wcfservicename.svc* |                                           El nombre del archivo .svc de Servicio WCF.                                            |


15. Para evitar la revelación de metadatos de servicio potencialmente confidenciales, se recomienda deshabilitar este comportamiento en el entorno de producción mediante la realización de las siguientes tareas:  

    1.  En el Bloc de notas, abra el archivo Web.config en la carpeta donde el Asistente publicación del servicio de WCF de BizTalk Server crea el servicio de WCF en %SystemDrive%\InetPub\\.  

    2.  En el Bloc de notas, establezca el **httpGetEnabled** atributo en el **\<serviceMetadata\>** elemento falso tal y como la línea siguiente:  

        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  

## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de WCF-BasicHttp](http://msdn.microsoft.com/library/5929a338-46e0-4fc4-8837-792d7f7ae0fe)   
 [Configuración del adaptador de WCF-WSHttp](../core/configuring-the-wcf-wshttp-adapter.md)   
 [Configuración del adaptador de WCF-CustomIsolated](../core/configuring-the-wcf-customisolated-adapter.md)   
 [Cómo configurar la autenticación de sitio Web IIS en Windows Server 2003](http://go.microsoft.com/fwlink/?LinkID=75699)