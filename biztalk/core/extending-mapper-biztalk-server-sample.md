---
title: Ampliar asignador (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, examples
- XML tools
- BizTalk Mapper, extending
- examples, BizTalk Mapper
- examples, XML tools
ms.assetid: 6010a13f-b715-4766-ad91-5aa9b98589e3
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f24f7f55e752e25ed06ec68c8eca40d2e7509683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-mapper-biztalk-server-sample"></a>Ampliar asignador (ejemplo de BizTalk Server)
El ejemplo de ampliación de asignador muestra cómo usar y ampliar el asignador de BizTalk. El ejemplo incluye varios archivos de asignación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (.btm), cada uno de los cuales muestra distintas características de Asignador de BizTalk.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo de ampliación de asignador usa el enrutamiento por contenidos (CBR) y no utiliza una orquestación. Mediante la especificación de un filtro en el puerto de envío de ejemplo, se conecta directamente al puerto de recepción de ejemplo. Se especifica una asignación en el puerto de envío que se va a aplicar al documento procesado.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso >*\XmlTools\ExtendingMapper  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|MapperClassLibrary\AssemblyInfo.cs, MapperClassLibrary\MapperClassLibrary.csproj, MapperClassLibrary\MapperHelper.cs, MapperClassLibrary\MapperClassLibrary.sln|Archivo de proyecto de Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]® y archivos de origen de Visual C#®.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).|  
|Destination.xsd|Archivo de esquema.|  
|ExtendingMapper.btproj, ExtendingMapper.sln|Proyecto de BizTalk y archivos de solución para este ejemplo.|  
|ExtendingMapper.xml|XML de origen.|  
|ExtendingMapperBinding.xml|XML de enlace.|  
|ExternalAssembly.xml|XML de ensamblado externo.|  
|OverridingMapXslt.btm|Archivo de asignación.|  
|OverridingMapXslt.xml|XML de asignación de reemplazos.|  
|OverridingMapXslt.xslt|Hoja de estilo de asignación de invalidación.|  
|Scriptor_CallExternalAssembly.btm|Archivo de asignación de ejemplo.|  
|Scriptor_GlobalVariableInInlineScript.btm|Archivo de asignación de ejemplo.|  
|Scriptor_InlineScripts.btm|Archivo de asignación de ejemplo.|  
|Scriptor_InlineXslt.btm|Archivo de asignación de ejemplo.|  
|Scriptor_InlineXsltCallingExternalAssembly.btm|Archivo de asignación de ejemplo.|  
|Scriptor_XsltCalltemplate.btm|Archivo de asignación de ejemplo.|  
|Setup.bat|Se utiliza para crear e inicializar el ejemplo.|  
|Source.xsd|Archivo de esquema.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo de ampliación de asignador.  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso >*\XmlTools\ExtendingMapper  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea las carpetas de entrada (\In) y de salida (\Out) para este ejemplo.  
  
    -   Compila e implementa el proyecto de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
     Si desea usar las asignaciones Scriptor_CallExternalAssembly.btm o Scriptor_InlineXsltCallingExternalAssembly.btm, abra ExtendingMapper.sln en Visual Studio y realice las siguientes modificaciones (de lo contrario, vaya al paso 3):  
  
    1.  En el Explorador de soluciones, abra Scriptor_CallExternalAssembly.btm.  
  
    2.  En la cuadrícula de asignador, seleccione el functoid de secuencias de comandos.  
  
    3.  En la cuadrícula de propiedades, seleccione la **Script** propiedad y haga clic en el botón de puntos suspensivos (...) para configurar la secuencia de comandos de functoid.  
  
    4.  En el **configurar Functoid de secuencias de comandos** cuadro de diálogo, seleccione la **configuración de Functoid de secuencia de comandos**y especifique lo siguiente:  
  
        |Establezca|Para esto|  
        |--------------|-------------|  
        |**Tipo de secuencia de comandos**|Ensamblado externo|  
        |**Ensamblado de script**|Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary|  
        |**Clase de secuencia de comandos**|Microsoft.Samples.BizTalk.ExtendingMapper.MapperHelper|  
        |**Método de script**|MyConcat|  
  
    5.  Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] **archivo** menú, elija **guardar** para guardar los cambios en el archivo de asignación y cierre la solución.  
  
3.  Presione cualquier tecla para continuar con Setup.bat.  
  
    > [!IMPORTANT]
    >  Si desea usar Scriptor_InlineXsltCallingExternalAssembly.btm, debe editar el archivo ExternalAssembly.xml. BizTalk usa ExternalAssembly.xml para asignar un espacio de nombres registrado de objeto de extensión de asignador a un ensamblado .NET. Puesto que se hace referencia al ensamblado dependiente por su nombre completo (incluido el token de clave pública, que se genera de forma automática), debe actualizar este valor. Si no desea usar Scriptor_InlineXsltCallingExternalAssembly.btm, no es necesario completar los pasos de la a a la e.  
  
4.  En el Explorador de Windows, vaya a \<carpeta Windows > \assembly\\.  
  
    1.  Haga clic en **Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary** y seleccione **propiedades**.  
  
    2.  Copie el valor del token de clave pública.  
  
    3.  En un editor de texto, abra  *\<ruta de ejemplos >*\XML Tools\ExtendingMapper\ExternalAssembly.xml.  
  
    4.  Seleccione el **AssemblyName, Version = 1.0.0.0, referencia cultural = neutral, PublicKeyToken = 68496d20c737d84b "**de atributo y reemplace el  **PublicKeyToken** valor con el token de clave pública valor que copió en el paso c..  
  
    5.  Guarde y cierre ExternalAssembly.xml.  
  
    > [!NOTE]
    >  Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.  
  
#### <a name="to-configure-enlist-and-start-the-send-port"></a>Para configurar, dé de alta e inicie el puerto de envío  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, seleccione **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, haga clic para expandir **administración de BizTalk Server**, haga clic para expandir **grupo de BizTalk [\<nombreDeServidor >:\<base de datos de administración >]**y haga clic para expandir **aplicaciones**.  
  
3.  Haga clic para expandir **ExtendingMapperApplication**y, a continuación, haga clic en **puertos de envío**.  
  
4.  En el panel derecho, haga clic en **puertos de envío**y, a continuación, haga clic en **propiedades**.  
  
5.  En el **ExtendingMapperSP – propiedades de puerto de envío** cuadro de diálogo, haga clic en el **asignaciones de salida** página.  
  
     En el **mapa** columna, seleccione la asignación requerida de la lista desplegable y, a continuación, haga clic en **Aceptar**. Las asignaciones se describen en la siguiente tabla.  
  
    |Asignar para aplicar propiedad|Description|  
    |---------------------------|-----------------|  
    |Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_CallExternalAssembly|Muestra cómo llamar a una función en un ensamblado .NET externo desde una **secuencias de comandos** functoid en una asignación, en función de los parámetros de entrada para este functoid. Esto ayuda a separar de forma clara la lógica de procesamiento del archivo de asignación. Este archivo de asignación usa el ensamblado MapperClassLibrary.dll que se proporciona con este ejemplo.|  
    |Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineScripts|Muestra cómo escribir secuencias de comandos simple dentro de **secuencias de comandos** functoids en un archivo de asignación con lenguajes .NET como C#, Visual Basic.NET y JScript.NET.|  
    |Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_GlobalVariableInInlineScript|Muestra cómo utilizar las variables globales en las secuencias de comandos de **secuencias de comandos** functoids. Las variables globales se usan normalmente para mantener la información de estado en un archivo de asignación en distintos **secuencias de comandos** functoids.|  
    |Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineXslt|Muestra cómo construir la estructura del documento de destino con XSLT en línea sin formato dentro de un **secuencias de comandos** functoid en el mapa. Puede construir algunas partes del documento de destino mediante **secuencias de comandos** functoids con XSLT en línea siempre que no sea posible hacerlo en el asignador de BizTalk con otros functoids.|  
    |Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_XsltCalltemplate|Muestra cómo crear la estructura del documento de destino mediante una plantilla de llamada XSLT en un **secuencias de comandos** functoid en el mapa. La ventaja de una plantilla de llamada XSLT en XSLT en línea es que la plantilla de llamada puede aceptar parámetros, por lo que puede crear la estructura basándose en parámetros de entrada para el **secuencias de comandos** functoid. Puede construir algunas partes del documento de destino mediante **secuencias de comandos** functoids con XSLT en línea siempre que no sea posible hacerlo en el asignador de BizTalk con otros functoids.|  
    |Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineXsltCallingExternalAssembly|Muestra cómo llamar a un ensamblado .NET externo desde dentro el XSLT en línea de un **secuencias de comandos** functoid en un mapa. Explica cómo puede invalidar la **XML de extensión personalizada** propiedad de la cuadrícula del asignador de BizTalk con el archivo de extensión personalizada ExternalAssembly_extxml.xml que contiene los detalles del ensamblado .NET externo para invocar. Puede construir algunas partes del documento de destino mediante **secuencias de comandos** functoids con XSLT en línea siempre que no sea posible hacerlo en la interfaz de usuario del asignador mediante otros functoids.|  
    |Microsoft.Samples.BizTalk.ExtendingMapper. OverridingMapXslt|Muestra cómo invalidar por completo el XSLT compilado del archivo de Asignador de BizTalk con un archivo XSLT personalizado. Puede hacerlo mediante el reemplazo de la **ruta de XSL personalizada**propiedad y, opcionalmente, el **XML de extensión personalizada** propiedad de la cuadrícula del asignador de BizTalk. El archivo XSLT personalizado proporcionado se incluye en el ensamblado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] compilado del proyecto que desee usar en tiempo de ejecución. En este caso, se omite el contenido del archivo de asignación (.btm). Este archivo de asignación usa OverridingMapXslt.xslt y OverridingMapXslt.xml para el **ruta de XSL personalizada** y **XML de extensión personalizada** propiedades, respectivamente.<br /><br /> Es posible validar un archivo de asignación en el Explorador de soluciones. A continuación, puede usar como un archivo de plantilla que puede modificar y utilizar para la **ruta de XSL personalizada** propiedad de la cuadrícula del asignador de BizTalk. Puede recurrir a esta opción siempre que no sea posible producir este XSLT mediante el Asignador de BizTalk.|  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo de ampliación de asignador.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Copia del archivo de la entrada ExtendingMapper.xml en la carpeta de entrada en  *\<ruta de ejemplos >*\XmlTools\ExtendingMapper\In.  
  
2.  Observe que el archivo se transforman y enrutan a la  *\<ruta de ejemplos >*carpeta \XmlTools\ExtendingMapper\Out. La transformación que se produce se basa en la asignación que ha aplicado.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md)