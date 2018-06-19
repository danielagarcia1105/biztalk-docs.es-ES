---
title: La canalización del procesador de error ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a57752b1-8bca-4534-9e5b-7ce721a9490a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd9a6cecf5353ab72cea0d67b06f3402fc1716a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296172"
---
# <a name="the-esb-fault-processor-pipeline"></a>La canalización del procesador de error ESB
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] instala un puerto de envío denominado todos. Las excepciones que usa el ESBFaultProcessor la canalización de envío. La figura 1 muestra las propiedades de todos. Las excepciones de puerto de envío.  
  
 ![Puerto de envío de todas las excepciones](../esb-toolkit/media/ch4-allexceptionssendport.gif "Ch4-AllExceptionsSendPort")  
  
 **Figura 1**  
  
 **La configuración de todos. Excepciones de puerto de envío, incluido el uso de la canalización de ESBFaultProcessor**  
  
 La canalización de ESBFaultProcessor contiene los siguientes componentes de canalización: codificador de excepción de ESB, Rastreador de supervisión de actividad de negocio de ESB (BAM) y para transformarlos ESB.  
  
 ALL. Excepciones de envío puerto se suscribe a todos los mensajes de error ESB y a todos los mensajes generados por el mecanismo de enrutamiento de mensajes de error de BizTalk. Figura 2 muestra el filtro de configuración de las propiedades de todos. Las excepciones de puerto de envío.  
  
 ![Puerto de envío de filtro](../esb-toolkit/media/ch4-filtersendport.gif "Ch4-FilterSendPort")  
  
 **Figura 2**  
  
 **La propiedad filter del todas. Excepciones de puerto define la suscripción del puerto de envío**  
  
## <a name="the-fault-processor-pipeline-exception-encoder-component"></a>El componente de codificador de excepción de error procesador canalización  
 El componente de canalización de codificador de excepción de ESB normaliza los mensajes de error generados en el mecanismo de excepción enrutamiento de orquestación de error de ESB y el mecanismo de enrutamiento de mensajes de error de BizTalk en mensajes canónicos que cumplen con los informes de excepción de ESB esquema.  
  
 Para una excepción de error de enrutamiento de excepción de orquestación, el componente enriquece y serializa todas las propiedades de mensaje de error, mensajes XLANG, propiedades de contexto, y **System.Exception** información en un mensaje XML.  
  
 Para una excepción de error de enrutamiento de mensajes, el componente enriquece los datos agregando el nombre de la aplicación y otras propiedades de ambiente, y se aplica el espacio de nombres de esquema para el contenido del mensaje XML saliente.  
  
 Opcionalmente, el componente de canalización de codificador de excepción de ESB también puede aplicar las instrucciones para el mensaje saliente de procesamiento de Microsoft InfoPath. Puede modificar las instrucciones de InfoPath estableciendo las propiedades del componente de canalización en la vista Diseño. Las siguientes propiedades de tiempo de diseño de tres afectan al comportamiento de tiempo de ejecución del componente de canalización de codificador de ESB excepción:  
  
-   **EscapeCDATA.** Esta propiedad determina si el componente escaparán cualquiera **CDATA** secciones que se encuentra en conservan los mensajes para que InfoPath puede mostrarlos correctamente.  
  
-   **FaultDocumentNamespace.** Esta propiedad no tiene un valor predeterminado de **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**. Esto se puede modificar para utilizar un espacio de nombres de salida personalizado para los mensajes persistentes.  
  
-   **ProcessingInstruction.** Esta propiedad puede contener cualquier instrucción de procesamiento de InfoPath que cumpla con el esquema de error Reporting de excepción de ESB. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye una plantilla de InfoPath que se ajusta a la siguiente instrucción de procesamiento.  
  
    ```  
    <?mso-infoPathSolution solutionVersion="1.0.0.346" productVersion="11.0.6565"  
    PIVersion="1.0.0.0"   
    href=file:///\\localhost\publish\Microsoft.Practices.ESB.ExceptionHandling.InfoPath.Reporting.xsn  
    name="urn:schemas-microsoft-com:office:infopath:  
    Microsoft-Practices-ESB-ExceptionHandling-InfoPath-Reporting:  
    http---schemas-microsoft-biztalk-practices-esb-com-exceptionhandling"  
    language="en-us" ?><?mso-application progid="InfoPath.Document"?>  
    ```  
  
## <a name="the-fault-processor-pipeline-bam-tracker-component"></a>El componente de seguimiento BAM de canalización de error procesador  
 El componente de canalización de la herramienta de seguimiento de BAM de ESB recibe el mensaje desde el componente de codificador de excepción de ESB y escribe datos del error seleccionado en las tablas de importación principal de BAM creadas durante la instalación del marco de administración de excepciones de ESB.  
  
 El componente de seguimiento de BAM de ESB usa el **GetEventStream** método del contexto de canalización para agregar los siguientes campos como un registro de actividad a la base de datos de importación principal de BAM:  
  
-   **Aplicación**  
  
-   **Description**  
  
-   **FaultSeverity**  
  
-   **ServiceName**  
  
-   **ErrorType**  
  
-   **FaultCode**  
  
-   **MachineName**  
  
-   **MessageID**  
  
-   **DateTime**  
  
-   **FaultDescription**  
  
-   **Ámbito**  
  
-   **FailureCategory**  
  
-   **FaultGenerator**  
  
-   **ServiceInstanceID**  
  
 El componente de seguimiento de BAM de ESB usa el identificador de mensaje (el **MessageID** propiedad) valor del mensaje de error ESB como el identificador de actividad BAM. El componente de seguimiento de BAM de ESB expone dos propiedades de tiempo de diseño que se pueden establecer para cambiar su comportamiento en tiempo de ejecución:  
  
-   **Habilitado.** Esta propiedad determina si el componente procesará el mensaje y escribir en la base de datos BAM. Cuando se establece en **False**, el componente solo envía el mensaje al siguiente componente de la canalización.  
  
-   **FaultDocumentNamespace.** Esta propiedad no tiene un valor predeterminado de **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**.  
  
## <a name="the-fault-processor-pipeline-transform-component"></a>La canalización del procesador error transformar el componente  
 La canalización del procesador de error de ESB utiliza el componente de canalización de transformación de ESB para ejecutar una asignación de BizTalk que convierte el mensaje de error ESB codificado en un formato que coincida con el esquema para el adaptador de SQL de BizTalk (ExceptionSql.xsd). El componente luego pasa el mensaje transformado al adaptador de SQL, que inserta el mensaje de error ESB en la base de datos del Portal de administración de ESB.  
  
 El componente de canalización de transformación de ESB expone tres propiedades de tiempo de diseño que se pueden modificar para cambiar su comportamiento en tiempo de ejecución:  
  
-   **Habilitado.** Esta propiedad habilita o deshabilita el componente.  
  
-   **Validar.** Esta propiedad especifica si es necesario validar un mensaje.  
  
-   **Nombredemapa.** Esta propiedad contiene el nombre del mapa que se debe ejecutar para traducir el mensaje para su almacenamiento en la base de datos del Portal de administración de ESB. Éste es el valor predeterminado.  
  
    ```  
    Microsoft.Practices.ESB.ExceptionHandling.Maps.FaultMessage_to_ExceptionSql,  
    Microsoft.Practices.ESB.ExceptionHandling.Maps,  
    Version=2.0.0.0,  
    Culture=neutral,  
    PublicKeyToken=c2c8b2b87f54180a  
    ```  
  
 Después de que todos los componentes de canalización finalizan su ejecución, el adaptador de la base de datos de SQL Server de BizTalk inserta el mensaje de error en la base de datos del Portal de administración de ESB.