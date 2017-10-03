---
title: "Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar esquemas como servicios WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, WCF services
- tools, WCF Service Publishing Wizard
- publishing, schemas [WCF services]
- WCF services, schemas
- WCF Service Publishing Wizard
ms.assetid: 3b770fd5-5b7b-493f-9016-d7d58854c5ff
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e1acb31455bfcf81ab9d4cb3e983f2614fce1c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-schemas-as-wcf-services"></a>Cómo utilizar el Asistente para publicación de Servicio WCF de BizTalk para publicar esquemas como servicios WCF
Use el Asistente para publicación de Servicio WCF de BizTalk para publicar esquemas como servicios WCF.  
  
> [!NOTE]
>  Debe generar los proyectos de BizTalk antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk. Los proyectos de BizTalk deben incluir esquemas para publicar como servicios WCF.  
  
### <a name="to-publish-schemas-as-wcf-servicees"></a>Para publicar esquemas como servicios WCF  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente de publicación de servicio de WCF de BizTalk**.  
  
    > [!NOTE]
    >  Para crear y publicar orquestaciones y esquemas de BizTalk como servicios WCF con los adaptadores de WCF, use el Asistente para publicación de Servicio WCF de BizTalk. Para publicar orquestaciones y esquemas como servicios Web con el adaptador de SOAP, utilice el Asistente para publicar servicios Web de BizTalk.  
  
2.  En el **éste es el Asistente para publicación de servicio WCF de BizTalk** página, haga clic en **siguiente**.  
  
3.  En el **tipo de servicio WCF** página, seleccione la **punto de conexión de servicio** opción para publicar los servicios WCF en orquestaciones de BizTalk seleccionadas en un ensamblado de BizTalk.  
  
     ![Página tipo de servicio WCF](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
4.  En el **tipo de servicio WCF** página, active o desactive el **habilitar extremo de metadatos** publicará la casilla de verificación para indicar si la recepción WCF aislada ubicación hospedado por Internet Information Services (IIS) metadatos del servicio para la recuperación mediante una solicitud HTTP/GET.  
  
     Cuando se selecciona esta casilla de verificación, el asistente genera un archivo Web.config en el que el **httpGetEnabled** atributo de la  **\<serviceMetadata >** elemento está establecido en **es true** . Puede usar una herramienta de importación de metadatos (como SvcUtil.exe) para generar el código de cliente necesario para llamar a este servicio en el entorno de desarrollo. La dirección en la que se publican los metadatos es la dirección del extremo más una **? wsdl** cadena de consulta.  
  
    > [!NOTE]
    >  Para evitar la posible revelación de metadatos de servicio potencialmente confidenciales, se recomienda deshabilitar este comportamiento en el entorno de producción. Esto se puede hacer al establecer httpgetenabled en falso o si se elimina el directorio virtual MEX.  
  
5.  En el **tipo de servicio WCF** página, en la **nombre de adaptador (tipo de transporte)** lista desplegable, seleccione el adaptador WCF aislado con el que se publican los servicios WCF. Puede seleccionar cualquiera de los siguientes adaptadores:  
  
    -   **WCF-BasicHttp.** El adaptador WCF-BasicHttp se puede comunicar con los servicios Web compatibles con el Perfil básico de servicios Web WS-I, versión 1.1 como los servicios basados en ASMX.  
  
    -   **WCF-WSHttp.** Este adaptador puede comunicarse con un servicio mediante los estándares WS-* a través de HTTP y HTTPS.  
  
    -   **WCF-CustomIsolated.** El adaptador WCF-CustomIsolated habilita el uso de las características de extensibilidad de Windows Communication Foundation (WCF) mediante el transporte HTTP.  
  
6.  En el **tipo de servicio WCF** página, seleccione la **ubicaciones de recepción de BizTalk crea en la siguiente aplicación** casilla de verificación para crear los puertos de recepción y las ubicaciones correspondientes a cada archivo .svc generado para el adaptador de WCF que seleccionó en el **nombre de adaptador** lista desplegable. Si ya existe una ubicación de recepción, no se sustituirá. Después de seleccionar esta opción, elija la aplicación donde se generarán los puertos de recepción y las ubicaciones en el **nombre de la aplicación de BizTalk** lista desplegable y, a continuación, haga clic en **siguiente**.  
  
7.  En el **crear servicio WCF** página, seleccione **publicar esquemas como servicio WCF**y, a continuación, haga clic en **siguiente**.  
  
     ![Página Crear servicio WCF](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")  
  
8.  En el **servicio WCF** , defina los servicios de WCF que se van a publicar. Utilice el árbol en el **descripción de servicio Web** cuadro de diálogo para agregar, quitar, cambiar el nombre y editar los nodos de descripción del servicio Web para los servicios WCF que se va a publicar. El **información** cuadro de diálogo proporciona información sobre el nodo seleccionado y muestra todos los errores en el nodo actual o en los subnodos:  
  
    -   El nodo raíz del árbol (Descripción del servicio Web) describe los servicios WCF que se van a publicar. El nombre del directorio virtual usa el nodo raíz como nombre predeterminado. Puede modificar el nombre de descripción del servicio Web para los servicios WCF publicar seleccionando **cambiar el nombre de descripción del servicio web**.  
  
         ![Página de servicio WCF](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")  
  
    -   El nodo de método Web, **Operation1**, del nodo de servicio predeterminado, **Service1**, como se muestra de forma predeterminada en el **descripción de servicio Web** cuadro de diálogo puede usarse para un ubicación de recepción de solicitud-respuesta. Si tiene previsto publicar ubicación de recepción para esta descripción del servicio, haga clic en el nodo de método Web unidireccional WCF, haga clic en **Eliminar método web**y, a continuación, cree un método Web unidireccional como sigue: haga clic en el servicio predeterminado nodo, seleccione **Agregar método web**y, a continuación, haga clic en **unidireccional**.  
  
    -   Para agregar un nuevo servicio WCF, haga clic en el nombre de descripción del servicio Web y, a continuación, haga clic en **Agregar servicio web**. Se creará un Servicio WCF nuevo sin ninguna operación de WCF. Para modificar el nombre del servicio WCF, haga clic en el nodo de servicio WCF, haga clic en **cambiar servicio web**, y, a continuación, presione ENTRAR para aceptar el nuevo nombre.  
  
    -   Para agregar una nueva operación de WCF, haga clic en el nodo de servicio WCF, seleccione **Agregar método Web**y, a continuación, haga clic en **unidireccional** (para una solicitud de operación de WCF) o **solicitud-respuesta** (para un operación de WCF de solicitud-respuesta).  
  
    -   Para establecer tipos de esquemas de solicitud y respuesta, haga clic en el **solicitud** o **respuesta** nodo y, a continuación, haga clic en **Seleccionar tipo de esquema**. En el **tipo de mensaje de solicitud** cuadro de diálogo, escriba el nombre del ensamblado que contiene el esquema de documento en el **archivo de ensamblado de BizTalk**cuadro de texto o haga clic en **examinar** para buscar para el ensamblado. El **tipos de esquemas disponibles** vista de lista muestra cada elemento raíz del esquema. Seleccione un nodo raíz para agregar como el tipo de esquema de solicitud o de respuesta.  
  
        > [!NOTE]
        >  Si ha instalado el archivo de ensamblado de BizTalk en la caché de ensamblados global (GAC), asegúrese de que el ensamblado en la GAC se ha actualizado con el ensamblado que seleccionará en el **tipo de mensaje de solicitud** cuadro de diálogo. Si la GAC tiene el mismo nombre completo, el Asistente para publicación de Servicio WCF de BizTalk utiliza el archivo de ensamblado en la GAC en lugar del que ha seleccionado.  
  
         ![Página tipo de mensaje de solicitud](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")  
  
    -   Puede cambiar el nombre de la **solicitar** y **respuesta** nodos sin afectar al código generado. Después de definir los esquemas, puede cambiar el nombre a los elementos de parte, lo que modifica el nombre de parámetro de la operación de WCF. Los cambios se pueden ver al consultar los metadatos de servicio para los servicios WCF que se van a publicar.  
  
        > [!NOTE]
        >  No se pueden usar espacios cuando se cambia el nombre de alguno de los nodos de descripción del servicio Web.  
  
9. Haga clic en **siguiente** para continuar con el asistente.  
  
10. En el **propiedades del servicio WCF** página, en la **Targetnamespace del servicio WCF** cuadro de texto, escriba un espacio de nombres de destino para los servicios WCF y, a continuación, haga clic en **siguiente**.  
  
     ![Página de propiedades del servicio WCF](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
11. En el **ubicación del servicio WCF** página, en la **ubicación** texto, escriba el nombre del directorio Web donde se generan los servicios WCF. Puede aceptar la ubicación predeterminada (http://localhost/\<*nombre de descripción del servicio Web*>), escriba una ubicación para los servicios WCF en el **ubicación** cuadro de texto o haga clic en  **Examinar** y seleccione un directorio Web. Seleccione cualquiera de las siguientes opciones:  
  
    -   **Sobrescribir proyecto existente.** Esta opción está disponible sólo si el directorio Web ya existe. Podrá publicar en la misma ubicación solo si selecciona esta opción. De lo contrario, debe especificar una ubicación de proyecto diferente.  
  
    -   **Permitir acceso anónimo al servicio WCF.** Esta opción agrega acceso anónimo al directorio virtual creado. De forma predeterminada, el directorio virtual hereda los privilegios de acceso de su directorio virtual principal o del sitio Web (si existe un directorio virtual de nivel superior).  
  
     Cuando termine de esta página, haga clic en **siguiente**.  
  
     ![Página ubicación del servicio de WCF](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  La ubicación del proyecto puede producirse en un servidor distinto. Para publicar los servicios WCF en un servidor diferente, escriba el nombre del proyecto como http://\<*servername*>/\<*ubicación del servicio WCF*>.  
  
    > [!NOTE]
    >  La ubicación del proyecto puede producirse en un sitio Web que no sea predeterminado. Cuando se publique en un sitio Web que no sea predeterminado, incluya el número de puerto del sitio Web en la URL. Por ejemplo, http://\<*servername*>: 8080 /\<*ubicación del servicio WCF*>.  
  
    > [!NOTE]
    >  Al utilizar el asistente para crear ubicaciones de recepción, éstas se crean mediante los valores predeterminados. El valor predeterminado para la canalización de recepción es el **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** canalización. Si los mensajes recibidos a través de los servicios WCF publicados requieren algún procesamiento de canalización especial (por ejemplo, validación, promoción de propiedades/correlación o asignaciones de entrada/salida), debe establecer la canalización de recepción en  **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, o en una canalización personalizada mediante la consola de administración de BizTalk.  
  
12. En el **resumen de servicio WCF** página, revise la configuración para los servicios WCF.  
  
13. Haga clic en **crear** para crear los servicios WCF.  
  
14. Haga clic en **finalizar** para completar el Asistente para publicación de servicio WCF de BizTalk.  
  
15. Una vez que ha publicado los servicios WCF con el Asistente para publicación de Servicio WCF de BizTalk, debe configurarlos adecuadamente. Para obtener información sobre cómo configurar el WCF aislados, adaptador de recepción, vea [cómo configurar publicadas de servicios WCF con el Asistente para publicación de servicio WCF de BizTalk](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar los servicios WCF publicados con el Asistente de publicación de servicios de WCF de BizTalk](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)   
 [Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar orquestaciones como servicios WCF](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)