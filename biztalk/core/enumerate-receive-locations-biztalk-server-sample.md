---
title: "Enumerar (ejemplo de BizTalk Server) de ubicaciones de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enumerating
- examples, receive locations
ms.assetid: 27ff8ac6-7e8e-4dde-84d1-d21bf417ddd7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a497b4b2d81ef2e6d0e62032b8c3939794451cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a>Enumerar (ejemplo de BizTalk Server) de ubicaciones de recepción
El ejemplo Enumerar ubicaciones de recepción demuestra cómo recuperar detalles sobre una o varias ubicaciones de recepción.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo incluye una versión de Visual Basic Scripting Edition (VBScript) que tiene acceso al modelo de objetos de WMI de Windows y una versión de Visual C# que tiene acceso a la **System.Management** objetos proporcionados por .NET Framework. Ambas versiones obtienen acceso finalmente al proveedor WMI de BizTalk Server para llevar a cabo las siguientes operaciones:  
  
-   Consultar el conjunto de ubicaciones de recepción configuradas, o bien una ubicación de recepción por su nombre.  
  
-   Recuperar y mostrar detalles sobre cada ubicación de recepción de interés.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Estos ejemplos se encuentran en las siguientes ubicaciones de SDK:  
  
-   Versión de VBScript: \< *ruta de ejemplos*> \Admin\WMI\Enumerate Receive Locations\VBScript\  
  
-   Versión Visual C#: \< *ruta de ejemplos*> \Admin\WMI\Enumerate Receive Locations\CSharp\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> EnumRecLocs.vbs|El archivo VBScript que recupera los detalles sobre todas las ubicaciones de recepción configuradas.|  
|En la carpeta \CSharp:<br /><br /> App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs|Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que recupere los detalles de todas las ubicaciones de recepción configuradas o de una ubicación de recepción específica.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 La versión de VBScript de la muestra Enumerar ubicaciones de recepción consta de un archivo de secuencias de comandos de Visual Basic que no necesita generar o inicializar.  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a>Para generar la versión de Visual C# del ejemplo Enumerar ubicaciones de recepción  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución BTSampleEnumerateRLs.sln.  
  
2.  En el **generar** menú, haga clic en **generar solución**.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a>Para ejecutar el ejemplo Enumerar ubicaciones de recepción  
  
1.  En una ventana de comandos, desplácese hasta una de las siguientes carpetas, en función de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente:  
  
     \<*Ejemplos de ruta de acceso*> \Admin\WMI\Enumerate recibir Locations\VBScript\  
  
     \<*Ejemplos de ruta de acceso*> \Admin\WMI\Enumerate recibir Locations\CSharp\bin\Debug\  
  
2.  Ejecute el archivo EnumRecLocs.vbs que usa el programa Cscript, o ejecute el archivo EnumRl.exe, en función de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente: Para la versión de Visual C#, pase uno de los dos siguientes argumentos de línea de comandos:  
  
    -   **\<ReceiveLocationName >.** El nombre de la ubicación de recepción para la que se mostrarán los detalles. Si el nombre de la ubicación de recepción contiene espacios, enciérrelo entre comillas.  
  
    -   **/?.** Muestra la Ayuda.  
  
         Por ejemplo (VBScript):  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         -O bien- (Visual C#):  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         -O bien- (Visual C#):  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  La versión de VBScript de este ejemplo no acepta ningún parámetro de línea de comandos y, por lo tanto, sólo es capaz de recuperar y mostrar detalles de todas las ubicaciones de recepción configuradas.  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración también puede realizarse mediante el uso de script que tiene acceso al modelo de objetos de WMI de Windows y con Visual C# que tiene acceso a la **System.Management** objetos proporcionados .NET Framework.  
  
 El archivo de secuencias de comandos EnumRecLocs.vbs y el archivo de origen de Visual C# EnumRLs.cs contienen comentarios detallados con más explicaciones sobre las operaciones que realizan. Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [WMI de administración (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)