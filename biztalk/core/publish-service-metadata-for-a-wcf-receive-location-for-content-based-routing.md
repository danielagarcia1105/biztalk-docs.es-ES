---
title: Cómo usar el Asistente para publicar el servicio de WCF de BizTalk para publicar los metadatos del servicio de ubicación de recepción de WCF para enrutamiento por contenidos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, metadata
ms.assetid: e900b0a0-db17-4db9-a639-54891e02d6d7
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efcda402c231b990d7fefa239a8ff15798331184
ms.sourcegitcommit: 9b93ee2a019bef8d482626cf5525a6b95509b135
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2018
ms.locfileid: "42709859"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing"></a>Cómo utilizar el Asistente para publicación de Servicio WCF de BizTalk para publicar metadatos de servicio para un ubicación de recepción WCF para enrutamiento por contenidos
Utilice el Asistente para publicación de Servicio WCF de BizTalk para crear un Servicio WCF para publicar los metadatos del servicio para las ubicaciones de recepción WCF existentes para enrutamiento por contenidos.  

> [!NOTE]
>  Debe generar los proyectos de BizTalk antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk. Los proyectos de BizTalk deben incluir esquemas para publicar como servicios WCF. Antes de publicar los metadatos del servicio para los adaptadores de WCF, debe también crear las ubicaciones de recepción WCF mediante la consola de administración de BizTalk Server o la herramienta de línea de comandos BTSTask incluida con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre cómo crear un WCF, ubicación de recepción, vea el tema correspondiente para cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md).  

### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-for-content-based-routing"></a>Para publicar metadatos de servicio en una ubicación de recepción WCF existente para enrutamiento por contenidos  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** y, a continuación, haga clic en **Asistente de publicación de servicio de WCF de BizTalk**.  

   > [!NOTE]
   >  Para crear y publicar los metadatos del servicio WCF para las orquestaciones de BizTalk y esquemas, utilice al Asistente para publicación de servicio WCF de BizTalk. Para publicar orquestaciones y esquemas como servicios Web con el adaptador de SOAP, utilice el Asistente para publicar servicios Web de BizTalk.  

2. En el **éste es el Asistente para publicación de servicio WCF de BizTalk** página, haga clic en **siguiente**.  

3. En el **tipo de servicio WCF** página, seleccione el **extremo de sólo metadatos (MEX)** opción para publicar los servicios WCF para proporcionar los metadatos del servicio de WCF ubicación de recepción que seleccionó en el paso siguiente.  

    ![Página tipo de servicio WCF](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")  

4. En el **tipo de servicio WCF** página, en el **Publicar metadatos para la ubicación de recepción** la lista desplegable, seleccione un WCF ubicación de recepción para publicar metadatos de servicio y, a continuación, haga clic en **siguiente**.  

5. En el **crear servicio WCF** página, seleccione **publicar esquemas como servicio WCF**y, a continuación, haga clic en **siguiente**.  

    ![Página Crear servicio WCF](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")  

6. En el **servicio WCF** , defina los contratos de servicio WCF para publicar los metadatos de servicio. Utilice el árbol en el **descripción del servicio Web** cuadro de diálogo para agregar, quitar, cambiar el nombre y editar los nodos de descripción del servicio Web para los servicios WCF publicar. El **información** cuadro de diálogo proporciona información acerca del nodo seleccionado y muestra los errores en el nodo actual o en cualquier subnodo:  

   -   El nodo raíz del árbol (Descripción del servicio Web) describe los contratos de Servicio WCF que se van a publicar. El nombre del directorio virtual usa el nodo raíz como nombre predeterminado. Puede modificar el nombre de descripción del servicio Web para los servicios WCF publicar seleccionando **cambiar el nombre de descripción del servicio web**.  

        ![Página de servicio WCF](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")  

   -   El nodo de método Web, **Operation1**, del nodo de servicio de forma predeterminada, **Service1**, como se muestra de forma predeterminada en el **descripción del servicio Web** se puede usar el cuadro de diálogo para un ubicación de recepción de solicitud-respuesta. Si ha seleccionado un WCF unidireccional ubicación de recepción para este contrato de servicio, haga clic en el nodo de método Web, haga clic en **Eliminar método web**y, a continuación, cree un método Web unidireccional como sigue: con el botón secundario en el punto del nodo de servicio predeterminado para **Agregar método web**y, a continuación, haga clic en **unidireccional**.  

   -   Para agregar un nuevo servicio WCF, haga clic en el nombre de descripción del servicio Web y, a continuación, haga clic en **Agregar servicio web**. Se creará un Servicio WCF nuevo sin ninguna operación de WCF. Para modificar el nombre del servicio WCF, haga clic en el nodo de servicio WCF, haga clic en **cambiar servicio web**, y, a continuación, presione ENTRAR para aceptar el nuevo nombre.  

   -   Para agregar una nueva operación de WCF, haga clic en el nodo de servicio WCF, seleccione **Agregar método Web**y, a continuación, haga clic en **unidireccional** (para una solicitud de operación de WCF) o **solicitud-respuesta** (para un operación de WCF de solicitud-respuesta).  

   -   Para establecer los tipos de esquema de la solicitud y respuesta, haga clic en el **solicitud** o **respuesta** nodo y, a continuación, haga clic en **Seleccionar tipo de esquema**. En el **tipo de mensaje de solicitud** cuadro de diálogo, escriba el nombre del ensamblado que contiene el esquema de documento en el **archivo de ensamblado de BizTalk** cuadro de texto o haga clic en **examinar** para buscar para el ensamblado. El **tipos de esquemas disponibles** vista de lista muestra cada elemento raíz del esquema. Seleccione un nodo raíz para agregar como el tipo de esquema de solicitud o de respuesta.  

       > [!NOTE]
       >  Si ha instalado el archivo de ensamblado de BizTalk en la caché global de ensamblados (GAC), asegúrese de que el ensamblado en la GAC se ha actualizado con el ensamblado que seleccionará en el **tipo de mensaje de solicitud** cuadro de diálogo. Si la GAC tiene el mismo nombre completo, el Asistente para publicación de Servicio WCF de BizTalk utiliza el archivo de ensamblado en la GAC en lugar del que ha seleccionado.  

        ![Página tipo de mensaje de solicitud](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")  

   -   Puede cambiar el nombre del **solicitar** y **respuesta** nodos sin afectar al código generado. Después de definir los esquemas, puede cambiar el nombre a los elementos de parte, lo que modifica el nombre de parámetro de la operación de WCF. Los cambios se pueden ver al consultar los metadatos de servicio para los servicios WCF que se van a publicar.  

   > [!NOTE]
   >  No se pueden usar espacios cuando se cambia el nombre de alguno de los nodos de descripción del servicio Web.  

7. Haga clic en **siguiente** para continuar con el asistente.  

8. En el **propiedades del servicio WCF** página, en el **Targetnamespace del servicio WCF** cuadro de texto, escriba un espacio de nombres de destino para los servicios WCF y, a continuación, haga clic en **siguiente**.  

    ![Página de propiedades del servicio WCF](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  

9. En el **ubicación del servicio WCF** página, en el **ubicación** texto, escriba el nombre del directorio Web donde se generan los servicios WCF. Puede aceptar la ubicación predeterminada (`http://localhost/<Web service description name>`), escriba una ubicación para los servicios WCF en el **ubicación** cuadro de texto o haga clic en **examinar** y seleccione un directorio Web. Seleccione cualquiera de las siguientes opciones:  

   - **Sobrescribir proyecto existente.** Esta opción está disponible solo si ya existe el directorio Web. Podrá publicar en la misma ubicación solo si selecciona esta opción. De lo contrario, debe especificar una ubicación de proyecto diferente.  

   - **Permitir acceso anónimo al servicio WCF.** Esta opción agrega acceso anónimo al directorio virtual creado. De forma predeterminada, el directorio virtual hereda los privilegios de acceso de su directorio virtual principal o del sitio Web (si existe un directorio virtual de nivel superior).  

     Cuando termine de esta página, haga clic en **siguiente**.  

     ![Página ubicación del servicio WCF](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  

     > [!NOTE]
     >  La ubicación del proyecto puede producirse en un servidor distinto. Para publicar los servicios WCF en un servidor diferente, escriba el nombre del proyecto como `http://<servername>/<WCF service location>`.  

     > [!NOTE]
     >  La ubicación del proyecto puede producirse en un sitio Web que no sea predeterminado. Cuando se publique en un sitio Web que no sea predeterminado, incluya el número de puerto del sitio Web en la URL. Por ejemplo, `http://<servername>:8080/<WCF service location>`.  

     > [!NOTE]
     >  El archivo BindingInfo.xml que crea el asistente en la carpeta \App_Data\Temp de la aplicación Web utiliza los valores predeterminados para las canalizaciones. El valor predeterminado para la canalización de recepción es el **Microsoft.BizTalk.DefaultPipelines.XMLReceive** canalización y el valor predeterminado para la canalización de envío es el  **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit** canalización.  

10. En el **resumen del servicio WCF** página, revise la configuración para los servicios WCF.  

11. Haga clic en **crear** para crear los servicios WCF.  

12. Haga clic en **finalizar** para completar el Asistente para publicación de servicio WCF de BizTalk.  

### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a>Para configurar la aplicación web para la publicación de metadatos de servicio  

1. Habilite ASP.NET para la aplicación web que ha creado el Asistente para publicación de Servicio WCF de BizTalk. Para obtener más información, consulte [habilitar los servicios Web](../core/enabling-web-services.md).  

   > [!NOTE]
   >  Si usa otra versión del sistema operativo Windows, debe agregar la cuenta de identidad del grupo de aplicaciones al grupo de administradores de BizTalk Server. Después de agregar la cuenta apropiada al grupo Administradores de servidor BizTalk Server, necesitará reiniciar el servicio IIS para que se aplique la configuración.  

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

   2.  En el Bloc de notas, establezca el el **httpGetEnabled** atributo en el **\<serviceMetadata\>** elemento falso tal y como la línea siguiente:  

       ```  
       <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
       ```  

## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente para publicar el servicio de WCF de BizTalk para publicar esquemas como servicios WCF](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)   
 [Tutorial: Publicación de servicios WCF con el adaptador WCF-NetMsmq](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)