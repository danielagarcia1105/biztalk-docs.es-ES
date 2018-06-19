---
title: XSLT transformar el componente (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- XSLT, examples
- examples, XSLT
ms.assetid: 9152e897-4db9-4924-b37e-fd9e908dbef1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1879cb4d748e974454f929bde2018c24b5d276f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974930"
---
# <a name="xslt-transform-component-biztalk-server-sample"></a>Componente de transformación de XSLT (ejemplo de BizTalk Server)
El ejemplo de componente de transformación de XSLT muestra cómo escribir un componente de canalización personalizado que modifique un mensaje XML mediante XSLT.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo lleva a cabo la transformación mediante los siguientes pasos:  
  
1.  Se recupera un documento XML de una carpeta.  
  
2.  La canalización transforma el documento XML en el cuerpo de HTML de un mensaje de correo electrónico mediante Transform.xsl.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso\>* \Pipelines\XslTransformComponent\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs|Archivo de ensamblado C#.|  
|Cleanup.bat|Archivo de limpieza de ejemplo.|  
|Confirmation.xsd|Archivo de esquema de ejemplo.|  
|DocInstance.xml|Archivo .xml de ejemplo que se va a transformar.|  
|SendHtmlMessage.btproj|Proyecto de BizTalk.|  
|Setup.bat|Archivo de procesamiento por lotes de configuración.|  
|Xml2HtmlSendPipeline.btp|Archivo de canalización de BizTalk Server.|  
|XslTransform.csproj|Proyecto C#.|  
|XslTransformComponent.sln|Archivo de solución de ejemplo.|  
|XslTransformComponentBinding.XML|Archivo de enlace XML.|  
|XslTransformer.cs|Código de origen C#.|  
|Transform.xsl|Archivo XSLT utilizado para transformar DocInstance.xml.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo del componente de transformación de XSLT.  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, cambie el directorio (**cd)** a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso\>* \Pipelines\XslTransformComponent  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea las carpetas de entrada (\In) y salida (\Out) que se utilizan en el ejemplo.  
  
    -   Genera un archivo de clave nuevo.  
  
    -   Genera e implementa la canalización del componente de transformación de XSLT.  
  
    -   Copia el componente de canalización generado para el \<ruta de acceso de instalación\>carpeta \Pipeline Components.  
  
    -   Crea los puertos de envío y recepción.  
  
    > [!NOTE]
    >  Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por Setup.bat, debe detener y reiniciar, en primer lugar, la instancia de host de la consola MMC de administración de BizTalk Server. A continuación, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo del componente de transformación XSLT.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Copie el archivo DocInstance.xml en la carpeta \In.  
  
2.  Examine los resultados en la carpeta \Out (el nombre del archivo resultante es guid.htm).  
  
## <a name="configuring-this-sample-using-smtp"></a>Configurar este ejemplo mediante SMTP  
 Utilice el siguiente procedimiento para configurar el ejemplo del componente de transformación de XSLT para que funcione con un servidor SMTP.  
  
#### <a name="to-configure-this-sample-using-smtp"></a>Para configurar este ejemplo mediante SMTP  
  
1.  Vuelva a configurar el puerto de envío del componente de transformación de XSLT para utilizar un tipo de transporte SMTP.  
  
2.  Configure el valor SMTP cambiando los parámetros de dirección (URI) para que coincidan con su configuración SMTP.  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a>Ejecutar este ejemplo con salida a un puerto SMTP  
 Utilice el siguiente procedimiento para ejecutar el ejemplo del componente de transformación XSLT con salida a un puerto SMTP.  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a>Para ejecutar este ejemplo con salida a un puerto SMTP  
  
1.  Copie el archivo DocInstance.xml en la carpeta \In.  
  
2.  Examine los resultados en el cliente de correo del destinatario para el que SMTP está configurado para enviar.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)