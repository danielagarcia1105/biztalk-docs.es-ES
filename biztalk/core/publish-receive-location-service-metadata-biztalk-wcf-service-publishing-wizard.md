---
title: Cómo usar el Asistente para publicar el servicio de WCF de BizTalk para publicar los metadatos del servicio de ubicación de recepción WCF enlazada con un puerto de orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, orchestration ports
- WCF services, metadata
- orchestrations, WCF services
ms.assetid: 04ccce9f-8d18-433a-8299-d06fa155db06
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53d290067b33d676f9c3052f93e61100252ad34f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996869"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-bound-to-an-orchestration-port"></a>Cómo utilizar el Asistente para publicación de Servicio WCF de BizTalk para publicar metadatos de servicio para un ubicación de recepción WCF enlazada con un puerto de orquestación
Utilice el Asistente para publicación de Servicio WCF de BizTalk para crear un Servicio WCF para publicar los metadatos del servicio para las ubicaciones de recepción WCF existentes enlazadas con puertos de orquestación.  

> [!NOTE]
>  Debe generar los proyectos de BizTalk antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk. Los proyectos de BizTalk deben incluir orquestaciones que tengan al menos un puerto de recepción cuyo modificador de tipo sea público. Antes de publicar los metadatos del servicio para los adaptadores de WCF, debe también crear las ubicaciones de recepción WCF mediante la consola de administración de BizTalk o la herramienta de línea de comandos BTSTask incluida con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre cómo crear un WCF, ubicación de recepción, vea el tema correspondiente para cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md).  

### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-bound-to-an-orchestration-port"></a>Para publicar metadatos de servicio en una ubicación de recepción WCF existente enlazada con un puerto de orquestación  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente de publicación de servicio de WCF de BizTalk**.  

   > [!NOTE]
   >  Para crear y publicar los metadatos del Servicio WCF para esquemas y orquestaciones de BizTalk, use el Asistente para publicación de Servicio WCF de BizTalk. Para publicar orquestaciones y esquemas como servicios Web con el adaptador de SOAP, utilice el Asistente para publicar servicios Web de BizTalk.  

2. En el **éste es el Asistente para publicación de servicio WCF de BizTalk** página, haga clic en **siguiente**.  

3. En el **tipo de servicio WCF** página, seleccione el **extremo de sólo metadatos (MEX)** opción para publicar los servicios WCF para proporcionar los metadatos del servicio de WCF ubicación de recepción que seleccionó en el paso siguiente.  

    ![Página tipo de servicio WCF](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")  

4. En el **tipo de servicio WCF** página, en el **Publicar metadatos para la ubicación de recepción** la lista desplegable, seleccione un WCF ubicación de recepción para publicar metadatos de servicio y, a continuación, haga clic en **siguiente**.  

5. En el **crear servicio WCF** página, seleccione **publicar orquestaciones de BizTalk como servicio WCF**y, a continuación, haga clic en **siguiente**.  

    ![Página Crear servicio WCF](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")  

6. En el **ensamblado de BizTalk** página, en el **archivo de ensamblado de BizTalk (\*.dll)** cuadro de texto, escriba el nombre del archivo de ensamblado de BizTalk o haga clic en **examinar** para ir a el ensamblado que contenga las orquestaciones para publicar los metadatos de servicio y, a continuación, haga clic en **siguiente**.  

   > [!NOTE]
   >  Antes de seleccionar un archivo de ensamblado de BizTalk, copie todos los ensamblados dependientes en la misma carpeta con el ensamblado de BizTalk o instalar a los ensamblados dependientes en la caché global de ensamblados (GAC).  

   > [!NOTE]
   >  Si ha instalado el archivo de ensamblado de BizTalk en la GAC, asegúrese de que el ensamblado en la GAC se ha actualizado con el ensamblado que seleccionará en el **ensamblado de BizTalk** cuadro de diálogo. Si el ensamblado en la GAC tiene el mismo nombre completo, el Asistente para publicación de Servicio WCF de BizTalk utiliza el archivo de ensamblado en la GAC en lugar del que ha seleccionado.  

   > [!NOTE]
   >  Las rutas que contienen más de 260 caracteres pueden producir un mensaje de error que informa de que la ruta es demasiado larga.  

    ![Página ensamblado de BizTalk](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")  

7. En el **orquestaciones y puertos** , expanda los nodos de árbol para cada ensamblado y orquestación haciendo clic en el signo más (+). Seleccione las orquestaciones y los puertos para los que publica metadatos seleccionando las casillas de verificación de nodo de árbol correspondientes. Si desea crear un servicio WCF (archivos .svc) para todos los puertos de recepción seleccionados en lugar de un servicio WCF para cada puerto de recepción, seleccione el **combinar todos los puertos seleccionados en un solo servicio WCF** opción y, a continuación, haga clic en  **Siguiente**.  

   > [!NOTE]
   >  Cuando combina todos los puertos seleccionados en un único Servicio WCF, todos los puertos seleccionados tienen el mismo tipo de puerto y los nombres de operación de los puertos son únicos.  

    ![Página de operaciones y puertos](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")  

8. En el **propiedades del servicio WCF** página, en el **Targetnamespace del servicio WCF** cuadro de texto, escriba un espacio de nombres de destino para los servicios WCF y, a continuación, haga clic en **siguiente**.  

    ![Página de propiedades del servicio WCF](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  

9. En el **ubicación del servicio WCF** página, en el **ubicación** texto, escriba el nombre del directorio Web donde se generan los servicios WCF. Puede aceptar la ubicación predeterminada (http://localhost/<*nombre de ensamblado de BizTalk*>), escriba una ubicación para los servicios WCF en el **ubicación** cuadro de texto o haga clic en **examinar** y seleccione un directorio Web. Seleccione cualquiera de las siguientes opciones:  

   - **Sobrescribir proyecto existente.** Esta opción está disponible solo si ya existe el directorio Web. Podrá publicar en la misma ubicación solo si selecciona esta opción. De lo contrario, debe especificar una ubicación de proyecto diferente.  

   - **Permitir acceso anónimo al servicio WCF.** Esta opción agrega acceso anónimo al directorio virtual creado. De forma predeterminada, el directorio virtual hereda los privilegios de acceso de su directorio virtual principal o del sitio Web (si existe un directorio virtual de nivel superior).  

     Cuando termine de esta página, haga clic en **siguiente**.  

     ![Página ubicación del servicio WCF](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  

     > [!NOTE]
     >  La ubicación del proyecto puede producirse en un servidor distinto. Para publicar los servicios WCF en un servidor diferente, escriba el nombre del proyecto como http://&lt*servername*>/<*ubicación del servicio WCF*>.  

     > [!NOTE]
     >  La ubicación del proyecto puede producirse en un sitio Web que no sea predeterminado. Cuando se publique en un sitio Web que no sea predeterminado, incluya el número de puerto del sitio Web en la URL. Por ejemplo, http://&lt*servername*>: 8080 / <*ubicación del servicio WCF*>.  

     > [!NOTE]
     >  El archivo BindingInfo.xml que crea el Asistente en la carpeta App_DataTemp de la aplicación Web utiliza los valores predeterminados para las canalizaciones. El valor predeterminado para la canalización de recepción es el **Microsoft.BizTalk.DefaultPipelines.XMLReceive** canalización y el valor predeterminado para la canalización de envío es el  **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit** canalización.  

10. En el **resumen del servicio WCF** página, revise la configuración para los servicios WCF.  

11. Haga clic en **crear** para crear los servicios WCF.  

12. Haga clic en **finalizar** para completar el Asistente para publicación de servicio WCF de BizTalk.  

### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a>Para configurar la aplicación web para la publicación de metadatos de servicio  

1. Habilite ASP.NET para la aplicación web que ha creado el Asistente para publicación de Servicio WCF de BizTalk. Para obtener más información, consulte [habilitar los servicios Web](../core/enabling-web-services.md).  

   > [!NOTE]
   >  Si usa Windows 2008 o Windows Vista, debe agregar la cuenta de identidad del grupo de aplicaciones al grupo de administradores de BizTalk Server. Después de agregar la cuenta apropiada al grupo de administradores de servidor BizTalk Server, necesita reiniciar el servicio IIS para que se aplique la configuración.  

2. Abra un símbolo del sistema, vaya a la carpeta donde el Asistente para publicación de servicio WCF de BizTalk creó los servicios WCF en %SystemDrive%\InetPub\\y, a continuación, abra el archivo Web.config mediante el Bloc de notas.  

3. En el Bloc de notas, agregue la siguiente línea dentro de la **\<system.web\>** elemento:  

   ```  
   <trust level="Full" originUrl="" />  
   ```  

   > [!NOTE]
   >  Esta configuración es opcional y concede a la aplicación ASP.NET que aloja el Servicio WCF publicado acceso a cualquier recurso que dependa de la seguridad del sistema operativo. Este es el nivel de confianza que WCF requiere cuando tiene Windows SharePoint Services instalado y ejecutándose en el mismo equipo con los servicios WCF publicados.  

4. En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para el servicio WCF con el formato http://<em>host [: puerto]</em>/*apppath* / *wcfservicename.svc* para probar el servicio WCF publicado. Los parámetros se describen en la siguiente tabla.  


   |      Parámetro       |                                                            Valor                                                            |
   |----------------------|-----------------------------------------------------------------------------------------------------------------------------|
   |    *host [: puerto]*     | El nombre del equipo en el que ha implementado el Servicio WCF. Este nombre de servidor puede ir seguido de dos puntos y el número de puerto. |
   |      *AppPath*       |                              El nombre del directorio virtual y la ruta de aplicación Web.                               |
   | *wcfservicename.svc* |                                           El nombre del archivo .svc de Servicio WCF.                                            |


5. Para evitar la divulgación involuntaria de metadatos de servicio potencialmente confidenciales, se recomienda deshabilitar este comportamiento en el entorno de producción mediante la realización de las siguientes tareas:  

   1.  En el Bloc de notas, abra el archivo Web.config en la carpeta donde el Asistente para publicación de servicio WCF de BizTalk creó el servicio WCF en %SystemDrive%\InetPub\\.  

   2.  En el Bloc de notas, establezca el el **httpGetEnabled** atributo en el **\<serviceMetadata\>** elemento en false como se muestra en la siguiente línea:  

       ```  
       <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
       ```  

## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente para publicar el servicio de WCF de BizTalk para publicar los metadatos del servicio de ubicación de recepción de WCF para enrutamiento por contenidos](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)   
 [Tutorial: Publicación de servicios WCF con el adaptador WCF-NetMsmq](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)