---
title: AS2 a través de archivo (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fed2344-8181-4c85-a2ef-a421fc40dce1
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d4c077cce861e94f6c2cdc0bfc6f4a14669340
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="as2-over-file-biztalk-server-sample"></a>AS2 a través de archivo (ejemplo de BizTalk Server)
El ejemplo AS2 a través de archivo muestra cómo recibir mensajes AS2 a través de una ubicación de recepción de archivo. Esto le permite usar un adaptador de archivo para recibir el mensaje AS2, en lugar de un adaptador de HTTP, que es el que se utiliza normalmente. Para ello, esta solución escribe los encabezados HTTP en el mensaje AS2 en la propiedad de contexto InboundHTTPHeaders, según requiere el descodificador AS2.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo procesar los encabezados HTTP en un mensaje AS2 sin disponer de un adaptador de HTTP. En concreto, este ejemplo realiza lo siguiente:  
  
1.  Cuando coloca el mensaje de prueba en una carpeta de entrada, la ubicación de recepción de archivo lo recoge.  
  
2.  El componente de canalización personalizado en la canalización de recepción AS2 personalizada procesa el mensaje, que escribe los encabezados en la propiedad de contexto InboundHTTPHeaders.  
  
    > [!NOTE]
    >  Si se produce un error en el procesamiento del mensaje de nivel inferior del componente de canalización personalizada, puede que tenga dificultades al reanudar el procesamiento del mensaje debido a que ya se habrá convertido en codificación XML.  
  
3.  El descodificador AS2 en la canalización de recepción personalizada procesa el mensaje, que lee las propiedades en la propiedad de contexto InboundHTTPHeaders para realizar su procesamiento.  
  
4.  Un puerto de envío se suscribe a un mensaje XML que genera la canalización de recepción, lo envía a través de una canalización de envío de paso a través y lo coloca en una carpeta de salida.    
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Este ejemplo se encuentra en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] carpeta de instalación: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|AS2OverFile.csproj|El proyecto que contiene el código de componente de canalización personalizado.|  
|AS2OverFile.sln|La solución que contiene el proyecto AS2OverFile.btproj.|  
|Program.cs|Incluye las clases que representan los datos de los encabezados.|  
|SampleMessage.txt|Los mensajes de ejemplo que contienen encabezados HTTP.|  
  
## <a name="implementing-and-running-this-sample"></a>Implementar y ejecutar este ejemplo  
 Para implementar el ejemplo AS2 a través de archivo, necesita realizar lo siguiente:  
  
-   Generar e implementar el proyecto de BizTalk para este ejemplo, que crea el componente de canalización personalizado  
  
-   Crear una canalización personalizada mediante el componente de canalización personalizado, y generar e implementar un proyecto con esa canalización personalizada  
  
-   Crear carpetas de archivo de entrada y de salida  
  
-   Configurar un puerto de recepción y ubicación, y habilitar la ubicación de recepción  
  
-   Configurar un puerto de envío e iniciarlo  
  
-   Crear una entidad para enviar el mensaje de ejemplo  
  
#### <a name="to-build-a-custom-pipeline-with-the-as2-over-file-emulator-pipeline-component"></a>Para generar una canalización personalizada con el componente de canalización del emulador AS2 a través de archivo  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto AS2OverFile de la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File.  
  
2.  Cree un archivo de clave de nombre seguro, abra el cuadro de diálogo Propiedades para el proyecto AS2OverFile y asigne el archivo de clave al proyecto.  
  
3.  Generar el proyecto.  
  
4.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree un nuevo proyecto de Biztalk con el nombre AS2OverFile_Pipeline.  
  
5.  Haga clic en el proyecto AS2OverFile_Pipeline, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
6.  En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **archivos de canalización** en el panel izquierdo, seleccione **canalización de recepción** en el panel derecho, asigne el nombre de la canalización AS2OverFile_ Receive.btp y, a continuación, haga clic en **agregar**.  
  
7.  Haga clic en **vista** en la barra de menús y, a continuación, haga clic en **cuadro de herramientas** para mostrar el cuadro de herramientas.  
  
8.  En el cuadro de herramientas, haga clic en **componentes de canalización de BizTalk**y, a continuación, haga clic en **elegir elementos**.  
  
9. En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, haga clic en el **componentes de canalización de BizTalk** ficha. Haga clic en **emulador AS2 a través de archivo**y, a continuación, haga clic en **Aceptar**.  
  
10. Agregue el archivo AS2OverFile.dll a la caché de ensamblado global abriendo el símbolo de sistema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y ejecutando el comando `gacutil /if "<file name and path>"` en Microsoft.BizTalk.Sdk.Components.AS2OverFile.dll en la carpeta AS2 Over File\obj\Debug.  
  
11. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], arrastre el componente de canalización del emulador AS2 a través de archivo del cuadro de herramientas en el **Decode** fase de la canalización personalizada.  
  
12. Arrastre el componente de descodificador de AS2 en el **Decode** fase de la canalización personalizada, después del componente AS2 a través de archivo.  
  
    > [!NOTE]
    >  Si desea generar un MDN, agregue un desensamblador AS2 a la fase Desensamblar de la canalización personalizada. Si no devuelve un MDN, el desensamblador AS2 no es necesario.  
  
13. Cree un archivo de clave de nombre seguro, abra el cuadro de diálogo Propiedades para el proyecto AS2OverFile_Pipeline y asigne el archivo de clave al proyecto.  
  
14. Genere e implemente la canalización personalizada.  
  
15. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, agregue la canalización personalizada al nodo canalizaciones haciendo clic en el nodo de canalizaciones y, a continuación, haga clic en **actualizar**.  
  
#### <a name="to-implement-the-solution-for-this-sample"></a>Para implementar la solución para este ejemplo  
  
1.  En el Explorador de Windows, en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File, cree una carpeta de entrada y una carpeta de salida.  
  
2.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un puerto de recepción unidireccional con el nombre AS2OverFile_Receive. En el puerto de recepción, cree una ubicación de recepción con las siguientes propiedades:  
  
    |Propiedad|Configuración|  
    |--------------|-------------|  
    |Nombre|AS2OverFile_Receive|  
    |Tipo|FILE|  
    |Carpeta Recepción|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/In|  
    |Máscara de archivo|*.txt|  
    |Canalización de recepción|AS2OverFile|  
  
3.  En el nodo ubicaciones de recepción, haga la AS2OverFile_Receive ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
4.  En el nodo Puertos de envío, cree un puerto de envío unidireccional estático con las siguientes propiedades:  
  
    |Propiedad|Configuración|  
    |--------------|-------------|  
    |Nombre|AS2OverFile_Send|  
    |Tipo|FILE|  
    |Carpeta Recepción|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/Out|  
    |Máscara de archivo|%MessageID%.xml|  
    |Canalización de envío|Passthru|  
    |Filtro|BTS.REceivePortName == AS2OverFile_Receive|  
  
5.  En el nodo puertos de envío, haga clic en el puerto de envío AS2OverFile_Send y, a continuación, haga clic en **iniciar**.  
  
6.  En el nodo Entidades, cree una entidad con el nombre "Socio comercial". En la lista de alias, agregue un alias con un **nombre** de **valor From de EDIINT-AS2**, **calificador** de **AS2-de**y un ** Valor** de **asociado**.  
  
 BizTalk Server ahora está listo para trabajar con este ejemplo.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo AS2 a través de archivo.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Copie el archivo SampleMessage.txt en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File en la carpeta \AS2 Over File\In.  
  
2.  Compruebe que un mensaje XML de salida se coloca en la carpeta de salida \AS2 Over File\Out.  
  
3.  Abra el mensaje de entrada SampleMessage.txt en un editor de texto y abra el mensaje de salida \<GUID\>.xml en un editor de texto. Compruebe que el mensaje de entrada SampleMessage.txt tenga los encabezados HTTP (y AS2) y que el mensaje de salida no tenga los encabezados HTTP.  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 None  
  
## <a name="see-also"></a>Vea también  
 [EDI y AS2 (carpeta de ejemplos de BizTalk Server)](../core/edi-and-as2-biztalk-server-samples-folder.md)   
 [Envío de un mensaje AS2 a través de un puerto de envío de archivo](../core/sending-an-as2-message-over-a-file-send-port.md)