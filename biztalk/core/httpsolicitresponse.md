---
title: HTTPSolicitResponse | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: b149544e-3279-4ac9-b31f-fff3e41ec8e7
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a68e24cee95b25596ad5162223c34a75139c13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981301"
---
# <a name="httpsolicitresponse"></a>HTTPSolicitResponse
El ejemplo HTTPSolicitResponse muestra cómo crear una orquestación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que aproveche una aplicación ASP.NET para ayudar a procesar los datos de la orquestación. En este ejemplo, la orquestación hace uso de un puerto de solicitud y respuesta para enviar un mensaje a la aplicación ASP.NET y para recuperar la respuesta. La integración entre la orquestación de BizTalk Server y la aplicación ASP.NET se consigue mediante el adaptador de HTTP. Para obtener más información, consulte [adaptador de HTTP](../core/http-adapter.md).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo se compone de una orquestación de BizTalk Server que recibe una solicitud con dos números que se van a multiplicar, y satisface la solicitud mediante la secuencia de pasos siguiente:  
  
1.  La orquestación de BizTalk Server recupera un archivo de entrada .xml de una carpeta concreta.  
  
2.  La orquestación usa una solicitud HTTP para reenviar el XML desde el archivo a una aplicación ASP.NET de multiplicador.  
  
3.  La aplicación ASP.NET de multiplicador responde a la solicitud HTTP realizando la multiplicación y devolviendo el resultado como XML en la respuesta HTTP.  
  
4.  La orquestación recibe el resultado como XML en una respuesta HTTP y escribe dicho resultado en un archivo .xml en una carpeta concreta.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HTTPSolicitResponse  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|Cleanup.bat|Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.|  
|HttpSolicitResponse.btproj, HttpSolicitResponse.sln|Proporciona archivos del proyecto y de origen para el proyecto de BizTalk que contiene la orquestación que usa la aplicación ASP.NET de multiplicador, los esquemas asociados, etc.|  
|HttpSolicitResponseBinding.xml|Se proporciona para la instalación automatizada, como el enlace de puerto.|  
|MultiplyRequest.xsd, MultiplyResponse.xsd|Proporciona esquemas para la solicitud de multiplicación y los mensajes XML de respuesta, respectivamente.|  
|MultiplyTwoIntegers.odx|Proporciona una orquestación de BizTalk Server que recibe un archivo .xml que solicita una operación de multiplicación, reenvía la solicitud a la aplicación ASP.NET de multiplicador y escribe su respuesta en un archivo.|  
|request_in.xml|Archivo de entrada de ejemplo.|  
|Setup.bat|Crea e inicializa este ejemplo.|  
|En la carpeta \Multiplier:<br /><br /> Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln|Contiene archivos que forman la aplicación ASP.NET que implementa el servicio de multiplicador, incluidos los archivos del proyecto y de la solución, archivos ASPX, archivos de origen de Microsoft Visual C# .NET, etc.|  
  
## <a name="building-and-initializing-the-sample"></a>Crear e inicializar el ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo HTTPSolicitResponse.  
  
> [!NOTE]
>  Si el nombre de la ubicación de recepción contiene caracteres en mayúscula, el ejemplo no funcionará.  
  
#### <a name="to-build-and-initialize-the-sample"></a>Para crear e iniciar el ejemplo  
  
1. En una ventana de comandos, desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HTTPSolicitResponse  
  
2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
   - Crea las carpetas de entrada y de salida para este ejemplo:  
  
      \<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput  
  
      \<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput  
  
   - Compila y configura la aplicación ASP.NET de multiplicador que usa este ejemplo.  
  
     > [!NOTE]
     >  Al crear el grupo de aplicaciones en el Administrador de IIS, establezca el **DefaultAppPool** versión de .NET Framework para **.Net Framework v4.0**.  
  
   - Compila e implementa la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se usa en este ejemplo.  
  
   - Crea y enlaza la ubicación y los puertos de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesarios.  
  
     > [!NOTE]
     >  Este ejemplo muestra las siguientes advertencias al crear y enlazar los puertos:  
  
     > [!NOTE]
     >  `Warning: Receive handler not specified for receive location "HttpSolicitResponseReceiveLocation"; updating with first receive handler with matching transport type.`  
  
     > [!NOTE]
     >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.HttpSolicitResponse.MultiplyTwoIntegers"; updating with first available host.`  
  
   - Habilita la ubicación de recepción e inicia el puerto de envío.  
  
     > [!NOTE]
     >  La orquestación de este ejemplo usa un puerto bidireccional para la interacción HTTP con la aplicación ASP.NET.  
  
     > [!NOTE]
     >  Debe confirmar que BizTalk no ha informado de ningún error durante el proceso de generación e inicialización antes de intentar ejecutar este ejemplo.  
  
     > [!NOTE]
     >  Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados resultantes.  
  
     > [!NOTE]
     >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-the-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo HTTPSolicitResponse.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Pegue una copia del archivo request_in.xml en la carpeta HttpSolicitResponseInput.  
  
2.  Observe el archivo .xml creado en la carpeta HttpSolicitResponseOutput. El nombre de este archivo .xml se basa en el GUID de Id. del mensaje. Este archivo contiene el resultado de la operación de multiplicación con formato XML.  
  
    > [!NOTE]
    >  Para realizar una operación de multiplicación diferente, puede cambiar los valores de los operandos en el archivo de entrada.  
  
## <a name="comments"></a>Comentarios  
 Puede adaptar este ejemplo para comunicarse con un sistema externo diferente que muestre una interfaz HTTP.  
  
 Los archivos MultiplyRequest.xsd y MultiplyResponse.xsd son los esquemas XML que definen el formato de los datos de entrada y salida para la aplicación ASP.NET de multiplicador. La orquestación usa estos archivos para definir los tipos de mensajes de solicitud y respuesta.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores de HTTP](../core/http-adapter-samples.md)