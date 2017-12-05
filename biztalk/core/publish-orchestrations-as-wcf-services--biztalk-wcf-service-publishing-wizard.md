---
title: "Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar orquestaciones como servicios WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tools, WCF Service Publishing Wizard
- WCF services, WCF Service Publishing Wizard
- WCF services, orchestrations
- publishing, orchestrations [WCF services]
- orchestrations, WCF services
- WCF Service Publishing Wizard
ms.assetid: db352132-2fe8-4d53-b239-45e5c3525b6c
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e233cfdd0871b55776cdf7cbaa9ee5b2af2724
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-orchestrations-as-wcf-services"></a>Cómo utilizar el Asistente para publicación de Servicio WCF de BizTalk para publicar orquestaciones como servicios WCF
El Asistente para publicación de Servicio WCF de BizTalk se utiliza para publicar orquestaciones como servicios WCF.  
  
> [!NOTE]
>  Debe generar los proyectos de BizTalk antes de ejecutar el Asistente para publicación de Servicio WCF de BizTalk. Los proyectos de BizTalk deben incluir orquestaciones que tengan al menos un puerto de recepción cuyo modificador de tipo sea público. Este modificador de tipo existe en las propiedades de la orquestación cuando se crea el puerto.  
  
### <a name="to-publish-an-orchestration-as-a-wcf-service"></a>Para publicar una orquestación como un Servicio WCF  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, haga clic en **Asistente de publicación de servicio de WCF de BizTalk**.  
  
    > [!NOTE]
    >  Para crear y publicar orquestaciones y esquemas de BizTalk como servicios WCF con los adaptadores de WCF, use el Asistente para publicación de Servicio WCF de BizTalk. Para publicar orquestaciones y esquemas como servicios Web con el adaptador de SOAP, utilice el Asistente para publicar servicios Web de BizTalk.  
  
2.  En el **éste es el Asistente para publicación de servicio WCF de BizTalk** página, haga clic en **siguiente**.  
  
3.  En el **tipo de servicio WCF** página, seleccione **punto de conexión de servicio** opción para publicar los servicios WCF en orquestaciones de BizTalk seleccionadas en un ensamblado de BizTalk.  
  
     ![Página tipo de servicio WCF](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
4.  En el **tipo de servicio WCF** página, seleccione **habilitar extremo de metadatos** casilla de verificación para indicar si la recepción WCF aislada ubicación hospedado por Internet Information Services (IIS) publica metadatos del servicio para la recuperación mediante una solicitud HTTP/GET. Al habilitar esta casilla de verificación, el asistente genera Web.config donde el **httpGetEnabled** atributo de la  **\<serviceMetadata\>**  elemento está establecido en **es true** . Puede usar una herramienta de importación de metadatos (como SvcUtil.exe) para generar el código de cliente necesario para llamar a este servicio en el entorno de desarrollo. La dirección en la que se publican los metadatos es la dirección del extremo más una **? wsdl** cadena de consulta.  
  
    > [!NOTE]
    >  Para evitar la posible revelación involuntaria de metadatos de servicio potencialmente confidenciales, se recomienda deshabilitar este comportamiento en el entorno de producción. Esto se puede hacer al establecer httpgetenabled en falso o si se elimina el directorio virtual MEX.  
  
5.  En el **tipo de servicio WCF** página, en la **nombre de adaptador (tipo de transporte)** lista desplegable, seleccione el adaptador WCF aislado con el que se publican los servicios WCF. Puede seleccionar cualquiera de los siguientes adaptadores:  
  
    -   **WCF-BasicHttp.** El adaptador WCF-BasicHttp se puede comunicar con los servicios Web compatibles con el Perfil básico de servicios Web WS-I, versión 1.1 como los servicios basados en ASMX.  
  
    -   **WCF-WSHttp.** Este adaptador puede comunicarse con un servicio mediante los estándares WS-* a través de HTTP y HTTPS.  
  
    -   **WCF-CustomIsolated.** El adaptador WCF-CustomIsolated habilita el uso de las características de extensibilidad de Windows Communication Foundation (WCF) mediante el transporte HTTP.  
  
6.  En el **tipo de servicio WCF** página, seleccione la **ubicaciones de recepción de BizTalk crea en la siguiente aplicación** casilla de verificación para crear los puertos de recepción y las ubicaciones correspondientes a cada archivo .svc generado para el adaptador WCF que seleccionó en el **nombre de adaptador** lista desplegable. Si ya existe una ubicación de recepción, no se sustituirá. Después de seleccionar esta opción, elija la aplicación donde se generarán los puertos de recepción y las ubicaciones en el **nombre de la aplicación de BizTalk** lista desplegable y, a continuación, haga clic en **siguiente**.  
  
7.  En el **crear servicio WCF** página, seleccione **publicar orquestaciones de BizTalk como servicio WCF**y, a continuación, haga clic en **siguiente**.  
  
     ![Página Crear servicio WCF](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")  
  
8.  En el **ensamblado de BizTalk** página, en la **archivo de ensamblado de BizTalk (\*.dll)** cuadro de texto, escriba el nombre del archivo de ensamblado de BizTalk o haga clic en **examinar** para ir a el ensamblado que contenga las orquestaciones para publicar y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Antes de elegir un archivo de ensamblado de BizTalk, copie todos los ensamblados dependientes en la misma carpeta con el ensamblado de BizTalk o instalar a los ensamblados dependientes en la caché global de ensamblados (GAC).  
  
    > [!NOTE]
    >  Si ha instalado el archivo de ensamblado de BizTalk en la GAC, asegúrese de que el ensamblado en la GAC se ha actualizado con el ensamblado que seleccionará en el **ensamblado de BizTalk** cuadro de diálogo. Si el ensamblado en la GAC tiene el mismo nombre completo, el Asistente para publicación de Servicio WCF de BizTalk utiliza el archivo de ensamblado en la GAC en lugar del que ha seleccionado.  
  
    > [!NOTE]
    >  Las rutas que contienen más de 260 caracteres pueden producir un mensaje de error que informa de que la ruta es demasiado larga.  
  
     ![Página de ensamblado de BizTalk](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")  
  
9. En el **orquestaciones y puertos** página, expanda los nodos de árbol para cada ensamblado y orquestación haciendo clic en el signo más (+). Seleccione las orquestaciones y puertos que se publicarán seleccionando las casillas de verificación de nodo de árbol correspondiente. Si desea crear un servicio WCF (archivos .svc) para todos los puertos de recepción seleccionados en lugar de un servicio WCF para cada puerto de recepción, seleccione el **combinar todos los puertos seleccionados en un único servicio WCF** opción y, a continuación, haga clic en  **Siguiente**.  
  
    > [!NOTE]
    >  Cuando combina todos los puertos seleccionados en un único Servicio WCF, todos los puertos seleccionados tienen el mismo tipo de puerto y los nombres de operación de los puertos son únicos.  
  
     ![Página de operaciones y puertos](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")  
  
10. En el **propiedades del servicio WCF** página, en la **Targetnamespace del servicio WCF** cuadro de texto, escriba un espacio de nombres de destino para los servicios WCF y, a continuación, haga clic en **siguiente**.  
  
     ![Página de propiedades del servicio WCF](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
11. En el **ubicación del servicio WCF** página, en la **ubicación** texto, escriba el nombre del directorio Web donde se generan los servicios WCF. Puede aceptar la ubicación predeterminada (http://localhost/ <*nombre de ensamblado de BizTalk*>), escriba una ubicación para los servicios WCF en el **ubicación** cuadro de texto o haga clic en **examinar**y seleccione un directorio Web. Seleccione cualquiera de las siguientes opciones:  
  
    -   **Sobrescribir proyecto existente.** Esta opción está disponible solo si el directorio Web ya existe. Podrá publicar en la misma ubicación solo si selecciona esta opción. De lo contrario, debe especificar una ubicación de proyecto diferente.  
  
    -   **Permitir acceso anónimo al servicio WCF.** Esta opción agrega acceso anónimo al directorio virtual creado. De forma predeterminada, el directorio virtual hereda los privilegios de acceso de su directorio virtual principal o del sitio Web (si existe un directorio virtual de nivel superior).  
  
     Cuando termine de esta página, haga clic en **siguiente**.  
  
     ![Página ubicación del servicio de WCF](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  La ubicación del proyecto puede producirse en un servidor distinto. Para publicar los servicios WCF en un servidor diferente, escriba el nombre del proyecto como http://<*servername*>/<*ubicación del servicio WCF*>.  
  
    > [!NOTE]
    >  La ubicación del proyecto puede producirse en un sitio Web que no sea predeterminado. Cuando se publique en un sitio Web que no sea predeterminado, incluya el número de puerto del sitio Web en la URL. Por ejemplo, http://<*servername*>: 8080 / <*ubicación del servicio WCF*>.  
  
    > [!NOTE]
    >  Al utilizar el asistente para crear ubicaciones de recepción, éstas se crean mediante los valores predeterminados. El valor predeterminado para la canalización de recepción es el **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** canalización. Si los mensajes recibidos a través de los servicios WCF publicados requieren algún procesamiento de canalización especial (por ejemplo, validación, promoción de propiedades/correlación o asignaciones de entrada/salida), debe establecer la canalización de recepción en  **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, o en una canalización personalizada, con la consola de administración de BizTalk Server.  
  
    > [!NOTE]
    >  Si decide no usar la **publicar orquestaciones como servicios WCF** opción después de llegar a esta página, en la **crear servicio WCF** página, es posible que vea que la **dedescripcióndeservicioWeb** muestra el servicio y el método nombres desde el ensamblado de BizTalk que seleccionó antes de cambia la opción de publicación. Esto es así porque la descripción del servicio Web en memoria no se borra cuando se cambia el método de publicación.  
  
12. En el **resumen de servicio WCF** página, revise la configuración para los servicios WCF.  
  
13. Haga clic en **crear** para crear los servicios WCF.  
  
14. Haga clic en **finalizar** para completar el Asistente para publicación de servicio WCF de BizTalk.  
  
15. Una vez que ha publicado los servicios WCF con el Asistente para publicación de Servicio WCF de BizTalk, debe configurarlos adecuadamente. Para obtener información sobre cómo configurar el WCF aislados, adaptador de recepción, vea [cómo configurar publicadas de servicios WCF con el Asistente para publicación de servicio WCF de BizTalk](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar los servicios WCF publicados con el Asistente de publicación de servicios de WCF de BizTalk](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)   
 [Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar esquemas como servicios WCF](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)