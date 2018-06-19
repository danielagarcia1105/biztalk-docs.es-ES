---
title: Ejemplo de enriquecimiento (ejemplo de BizTalk Server) del mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3413345c4e2d0a2ce4cd7ee1cb5ebda50b1dea7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265212"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a>Message Enrichment (ejemplo de BizTalk Server)
El ejemplo Message Enrichment muestra cómo anexar encabezados de intercambio a mensajes de conjunto de transacciones para documentos X12 y EDIFACT.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo anexar encabezados UNA, UNB y UNG para EDIFACT, así como encabezados ISA para X12 a conjuntos de transacciones. En concreto, este ejemplo realiza lo siguiente:  
  
1.  Al colocar el mensaje de prueba en la carpeta \Message Enrichment\In, el puerto de recepción lo selecciona, lo procesa y lo coloca en el Cuadro de mensajes.  
  
2.  MessageEnrichmentOrchestration toma el mensaje de prueba del Cuadro de mensajes porque se suscribe a mensajes basándose en una expresión de filtro establecida en su forma Recepción.  
  
3.  La orquestación lee los encabezados de intercambio a partir de las propiedades de contexto del mensaje.  
  
    > [!NOTE]
    >  Los encabezados UNA y UNG son opcionales en un mensaje EDIFACT de modo que pueden faltar en las propiedades de contexto de un mensaje.  
  
4.  La orquestación escribe tanto los encabezados de intercambio como el cuerpo del mensaje en un único mensaje nuevo.  
  
5.  La orquestación promociona más propiedades que se establecen en el tipo de correlación ReceivePortNameCorrelationType en el mensaje. Éstas permiten que los usuarios de la orquestación seleccionen una lista de las propiedades que necesitan para la suscripción. Estas propiedades se escriben en una forma Construir mensaje. No todas las propiedades de contexto escritas en el mensaje original se escriben en el mensaje nuevo.  
  
6.  La orquestación coloca el mensaje nuevo en el Cuadro de mensajes.  
  
7.  El puerto de envío selecciona el mensaje nuevo y lo envía a través del adaptador de Archivo a la carpeta \Message Enrichment\Out.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Este ejemplo se encuentra en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] carpeta de instalación: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message enriquecimiento.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Anula la implementación del escenario de ejemplo. Para que se realice correctamente, no debe haber instancias activas de la orquestación. De lo contrario, no se realizará correctamente.|  
|MessageEnrichment.sln|Contiene los proyectos MessageEnrichment y MessageEnrichmentLibrary.|  
|Setup.bat|Implementa un escenario de ejemplo que se compone de un puerto de recepción, un puerto de envío y una orquestación.|  
|EDIFACT_example.edi|Mensaje EDIFACT de entrada.|  
|X12_example.edi|Mensaje X12 de entrada.|  
|MessageEnrichment.btproj|Proyecto que contiene las orquestaciones y los esquemas de MessageEnrichment.|  
|MessageEnrichmentBindings.xml|Archivo que contiene enlaces para la orquestación, los puertos y las entidades.|  
|MessageEnrichmentOrchestration.odx|Orquestación que anexa los encabezados al mensaje.|  
|MessageEnrichmentOrchestration.odx.cs|Código de la orquestación que anexa los encabezados al mensaje.|  
|EFACT_D98B_APERAK.xsd|Esquema EDIFACT para el mensaje de entrada.|  
|Enriched_EFACT_D98B_APERAK.xsd|Esquema EDIFACT para el mensaje de salida.|  
|X12_00401_864.xsd|Esquema X12 para el mensaje de entrada.|  
|Enriched_X12_00401_864.xsd|Esquema X12 para el mensaje de salida.|  
|Headers.xsd|Esquemas para los encabezados agregados a los mensajes de entrada.|  
|MessageEnrichmentLibrary.csproj|Proyecto que contiene los archivos Headers.cs, OrchestrationUtilities.cs y ParseHeaders.cs.|  
|Headers.cs|Incluye las clases que representan los datos de los encabezados.|  
|OrchestrationUtilities.cs|Incluye métodos de utilidad empleados por la orquestación.|  
|ParseHeaders.cs|Incluye los valores predeterminados de UNA que se usan en los mensajes nuevos. Estos valores se toman del método SerializeEDIFACTHeaders en ParseHeaders.cs.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use este ejemplo como ejemplo de trabajo de las acciones necesarias para anexar encabezados de intercambio a mensajes de conjuntos de transacciones EDI.  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Para crear e inicializar el ejemplo Message Enrichment, deberá crear e implementar el proyecto de BizTalk para este ejemplo, configurar la ubicación y el puerto de recepción, así como configurar dos puertos de envío diferentes.  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>Para crear e implementar el proyecto de BizTalk para este ejemplo  
  
1.  Mediante Notepad.Exe, abra [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\  
    MessageEnrichment\properties\AssemblyInfo.cs y agregue la siguiente línea al final del archivo:  
  
    ```  
    [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
    ```  
  
2.  Guarde el archivo AssemblyInfo.cs modificado y, a continuación, cierre el Bloc de notas.  
  
3.  En una ventana de comandos, vaya a la siguiente carpeta:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment  
  
4.  Ejecutar **Setup.bat**, que realiza las siguientes acciones:  
  
    -   Crea la recepción (**en**) y enviar (**out**) para este ejemplo en la carpeta \MessageEnrichment.  
  
    -   Escribe un par de claves en MessageEnrichmentLibrary\testkey.snk  
  
    -   Crea e implementa el proyecto MessageEnrichmentLibrary.btproj.  
  
    -   Crea e implementa el proyecto MessageEnrichment.btproj.  
  
    -   Lee la información de enlaces de MessageEnrichmentBindings.xml.  
  
        > [!NOTE]
        >  El enlace para este proyecto requiere que el host de BizTalk está marcado como autenticación de confianza.  Para usar esta opción con un host que no sea de confianza, modifique el archivo MessageEnrichmentBindings.xml y cambie las entradas HostTrusted=”true” a HostTrusted=”false”.  
  
    -   Actualiza los enlaces de la orquestación.  
  
    -   Actualiza los puertos de envío, grupos de puertos de envío y puertos de recepción.  
  
    -   Actualiza entidades e inscripciones.  
  
    -   Inicia el puerto de envío.  
  
    -   Habilita la ubicación de recepción.  
  
    -   Da de alta e inicia la orquestación.  
  
 Ahora, el servidor BizTalk Server estará preparado para trabajar con este ejemplo.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo Message Enrichment.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Copie el archivo EDIFACT_examples.edi de la carpeta \MessageEnrichment\Instances en la carpeta \MessageEnrichment\In.  
  
2.  Verifique si los archivos EDIFACT_examples.edi desaparecen de la carpeta \MessageEnrichment\In y aparecen en la carpeta \MessageEnrichment\Out.  
  
3.  Abra el archivo de la carpeta \MessageEnrichment\Out. Verifique que se trata de una representación XML del archivo EDIFACT_examples.edi de la carpeta \MessageEnrichment\Instances, y que su contenido es idéntico al del archivo EDIFACT_examples.edi, excepto por el hecho de que el archivo de salida tiene encabezados UNA, UNB y UNG de EDIFACT.  
  
4.  Repita los pasos 1 y 2 con el archivo X12_examples.edi de la carpeta \MessageEnrichment\Instances.  
  
5.  Abra el archivo nuevo de la carpeta \MessageEnrichment\Out. Verifique que se trata de una representación XML del archivo X12_examples.edi de la carpeta \MessageEnrichment\Instances, y que su contenido es idéntico al del archivo X12_examples.edi, excepto por el hecho de que el archivo de salida tiene encabezados ISA de X12.  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 Ninguno  
  
## <a name="see-also"></a>Vea también  
 [EDI y AS2 (carpeta de ejemplos de BizTalk Server)](../core/edi-and-as2-biztalk-server-samples-folder.md)