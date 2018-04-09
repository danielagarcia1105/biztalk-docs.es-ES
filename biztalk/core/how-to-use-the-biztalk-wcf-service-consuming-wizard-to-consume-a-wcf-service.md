---
title: Cómo usar el servicio de WCF de BizTalk consumiendo Asistente para consumir un servicio WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Consuming Wizard
- WCF Service Consuming Wizard
- tools, WCF Service Consuming Wizard
- consuming, WCF Service Consuming Wizard
ms.assetid: d5fad2ac-4d98-4720-8026-88ebab78b120
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fb3eca6db9ceafeeab9b0b276bfd6f3cb23b16
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service"></a>Cómo utilizar el Asistente para consumición del Servicio WCF de BizTalk para consumir un Servicio WCF
El marco de trabajo de adaptadores proporciona un medio para agregar esquemas de adaptador y tipos de BizTalk a proyectos de BizTalk. El Asistente para consumición del Servicio WCF de BizTalk le permite agregar adaptadores de envío WCF a un proyecto de BizTalk. Para los adaptadores de envío WCF, debe seleccionar un extremo de intercambio de metadatos (MEX) existente en los puertos de envío. A continuación tendrá que especificar la información que se ha utilizado para generar los tipos y los esquemas. Una vez que ha finalizado el asistente, los esquemas y los tipos necesarios para consumir servicios WCF se agregan al proyecto de BizTalk.  
  
### <a name="to-add-the-schemas-and-types-for-wcf-send-adapters-to-your-project"></a>Para agregar esquemas y tipos de adaptadores de envío WCF a su proyecto  
  
1.  En la Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el Explorador de soluciones, haga clic en el proyecto, haga clic en **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados - \< ***nombre del proyecto*** \>**  cuadro de diálogo, en la **plantillas** sección, seleccione **consumir WCF Servicio**y, a continuación, haga clic en **agregar**.  
  
3.  En el **éste es el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **siguiente**.  
  
4.  En el **origen de metadatos** página, seleccione el origen de los metadatos para importar y, a continuación, haga clic en **siguiente**.  
  
     ![Página origen de metadatos](../core/media/2478a788-23ff-4ba9-a183-82e533b57f46.gif "2478a788-23ff-4ba9-a183-82e533b57f46")  
  
     Para descargar documentos de metadatos desde el extremo de intercambio de metadatos de un servicio en ejecución, seleccione la **punto de conexión de intercambio de metadatos (MEX)** opción. Esto permite crear un puerto de envío que actúe como cliente del servicio WCF. Para usar esta opción, el extremo del servicio debe publicar los metadatos de servicio que va a recuperar por medio de una solicitud HTTP/GET o HTTPS/GET. Además, el extremo del servicio debe permitir el acceso a los metadatos con credenciales de usuario anónimo o credenciales de usuario compuestas por nombre de usuario y contraseña con el esquema de autenticación básico.  
  
    > [!NOTE]
    >  Con el esquema de autenticación básico, las credenciales se envían como texto simple, y podrían ser interceptadas con facilidad. Asimismo, el esquema no proporciona protección para la información que se devuelve desde el servicio. Debe utilizar una conexión de Secure Sockets Layer (SSL) para cifrar los datos.  
  
     Para que cualquier otro documento de metadatos importar, seleccione la **archivos de metadatos (WSDL y XSD)** opción para importar metadatos desde un sistema de archivos.  
  
    > [!NOTE]
    >  No todos los servicios deben publicar metadatos. Mantener deshabilitada la publicación de metadatos reduce la superficie de ataque del servicio y disminuye el riesgo de que se produzca una divulgación involuntaria de la información.  
  
5.  Si ha seleccionado la **punto de conexión de intercambio de metadatos (MEX)** opción el **origen de metadatos** página, el **extremo de metadatos** aparecerá la página. En el **extremo de metadatos** página, especifique la dirección URL para el servicio en ejecución que proporciona metadatos para su descarga mediante WS-Metadata Exchange o Http-Get. Para obtener el documento de metadatos de la dirección URL, haga clic en **obtener**. Si el servicio en ejecución requiere una credencial de usuario con el esquema de autenticación básica, haga clic en **editar** para abrir **el Asistente para consumición de servicio de BizTalk WCF** cuadro de diálogo en el que puede proporcionar el nombre de usuario y contraseña que se utilizará al obtener acceso a ejecutar el servicio.  
  
     ![Página extremo de metadatos](../core/media/2b17f85a-64d0-4719-99c4-ce61c706f10c.gif "2b17f85a-64d0-4719-99c4-ce61c706f10c")  
  
    > [!NOTE]
    >  Para descargar los metadatos de los servicios WCF publicados a través de HTTP o HTTPS, no puede usar el extremo MEX como http://localhost:8087/CalculatorService/mex para la **dirección de metadatos** cuadro de texto. Para los servicios WCF, debe usar los metadatos de WSDL para descargar los metadatos como sigue: http://localhost:8087/CalculatorService o http://localhost:8087/CalculatorService? wsdl  
  
6.  Si ha seleccionado la **archivos de metadatos (WSDL y XSD)** opción el **origen de metadatos** página, el **extremo de metadatos** aparecerá la página. En el **extremo de metadatos** página, especifique los archivos de metadatos para importar. Haga clic en **agregar** para agregar los archivos de metadatos para importar a la **archivos de metadatos** vista. Se abrirá la **agregar archivos de metadatos** cuadro de diálogo en el que puede buscar ubicaciones de disco para archivos de metadatos.  
  
     En el **agregar archivos de metadatos** cuadro de diálogo, seleccione los archivos de un conjunto completo de WSDL y XSD como metadatos. Estos archivos de metadatos pueden generarse especificando el comando siguiente en el símbolo del sistema:  
  
     **svcutil.exe /t:metadata http://localhost/service.svc/mex**  
  
     Haga clic en **quitar** para quitar los archivos de metadatos seleccionados en el **archivos de metadatos** vista.  
  
     ![Metadata Files page](../core/media/445bccd1-88b0-41ad-b91d-e899e7d5902d.gif "445bccd1-88b0-41ad-b91d-e899e7d5902d")  
  
    > [!NOTE]
    >  El archivo SvcUtil.exe está incluido en el kit de desarrollo de software (SDK) de Microsoft Windows de los componentes en tiempo de ejecución de .NET Framework y Windows Vista.  
  
    > [!NOTE]
    >  Los metadatos de servicio pueden alterarse o falsearse cuando se recuperan de una manera insegura. Unos metadatos alterados podrían redirigir el cliente hacia un servicio malicioso, contener configuraciones de seguridad comprometidas o estructuras XML maliciosas. Los documentos de metadatos pueden ser muy grandes y con frecuencia se guardan en el sistema de archivos. Debe asegurarse de que no se han alterado los archivos de metadatos.  
  
7.  En el **Importar resumen de metadatos de servicio de WCF** página, revise la configuración. Puede hacer clic en **volver** realizar ningún cambio. A continuación, haga clic en **importación** para crear los artefactos de BizTalk y los tipos que se usará para utilizar el servicio WCF.  
  
8.  En el **completar el Asistente para consumición de servicio de BizTalk WCF** página, haga clic en **finalizar**. Si desea volver a ejecutar este asistente, seleccione la **vuelva a ejecutar este asistente** opción y, a continuación, haga clic en **finalizar**.  
  
     El Asistente para consumición del Servicio WCF de BizTalk crea los tipos y esquemas de BizTalk necesarios para consumir servicios WCF en el proyecto de BizTalk. Los tipos de BizTalk, como los tipos de puerto y los tipos de mensaje de varias partes se crean en una orquestación. Se recomienda no modificar la orquestación que crea el asistente. En su lugar, puede agregar orquestaciones nuevas en el proyecto de BizTalk para cumplir sus fines. El Asistente de consumición de servicio WCF de BizTalk también crea dos archivos de enlace, **BizTalkServiceInstance.BindingInfo.xml** y **BizTalkServiceInstance_Custom.BindingInfo.xml**. **BizTalkServiceInstance.BindingInfo.xml** es un archivo de enlace de BizTalk que puede importarse por la herramienta de línea de comandos de desarrollo o el Asistente para configurar los puertos de envío con los adaptadores de WCF de enlace estándar, por ejemplo, el WCF-NetMsmq y WCF-WSHttp adaptadores. **BizTalkServiceInstance.BindingInfo.xml** es un archivo de enlace de BizTalk que puede importarse por la herramienta de línea de comandos de desarrollo o el Asistente para configurar los puertos de envío con el adaptador WCF-Custom.  
  
     Cuando se importa el archivo de enlace generado, rellena la **WCF. Acción** propiedad con el formato de asignación de acción. Para ver cómo se configura esta propiedad, busque en el **acción** cuadro de texto en el **General** ficha en el cuadro de diálogo WCF envío puerto transporte propiedades en la consola de administración de BizTalk.  
  
     Puede especificar el **WCF. Acción** propiedad de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única: por ejemplo, http://contoso.com/Svc/Op1 - la **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad. Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinado por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML y **BTS. Operación** propiedad está establecida en **Op1**, WCF adaptador de envío utiliza http://contoso.com/Svc/Op1 para los salientes **SOAPAction** encabezado.  
  
     `<BtsActionMapping>`  
  
     `<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" />`  
  
     `<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" />`  
  
     `</BtsActionMapping>`  
  
     Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente la **BTS. Operación** propiedad con el nombre de la operación del puerto. Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización. Los puertos generados por el Asistente para consumición de WCF de BizTalk tienen operaciones cuyos nombres coincidan con el **nombre** atributos en el **<BtsActionMapping>** elemento. No es necesario establecer explícitamente la **BTS. Operación** propiedad en orquestaciones cuando se envían mensajes a través de puertos generados por el asistente.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar orquestaciones como servicios WCF](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)   
 [Cómo usar el Asistente de publicación de servicios de WCF de BizTalk para publicar esquemas como servicios WCF](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)