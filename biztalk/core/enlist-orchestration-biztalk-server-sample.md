---
title: "Dar de alta una orquestación (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, enlisting
- examples, orchestrations
ms.assetid: d8d53e59-2313-40dd-a278-0a29d8eb4ce8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e8d85a49b410f0571e8e9cb0be816f1feda139e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="enlist-orchestration-biztalk-server-sample"></a>Dar de alta una orquestación (ejemplo de BizTalk Server)
El ejemplo para dar de alta una orquestación muestra cómo se da de alta una orquestación de BizTalk Server en un host.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo incluye una versión de Visual Basic Scripting Edition (VBScript) que tiene acceso al modelo de objeto de Instrumental de administración de Windows (WMI) y una versión de Visual C# que tiene acceso a la **System.Management** objetos proporcionados por .NET Framework. Ambas versiones obtienen acceso finalmente al proveedor WMI de BizTalk Server para llevar a cabo las siguientes operaciones:  
  
-   A partir de un nombre de orquestación y de ensamblado, consultar una orquestación de BizTalk Server implementada.  
  
-   Dar de alta esa orquestación en el host predeterminado.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Estos ejemplos se encuentran en las siguientes ubicaciones de SDK:  
  
-   Versión de VBScript: \< *ruta de ejemplos*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
-   Versión de Visual C#: \< *ruta de ejemplos*\>\Admin\WMI\Enlist Orchestration\CSharp\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> EnlistOrch.vbs|El archivo VBScript que toma parámetros para especificar una orquestación que se va a dar de alta en un host.|  
|En la carpeta \CSharp:<br /><br /> App.ico, AssemblyInfo.cs, BTSampleEnlistOrc.csproj, BTSampleEnlistOrc.sln, EnlistOrc.cs|Archivos de proyecto, de solución y de origen para generar una aplicación de línea de comandos de Visual C# que tome parámetros para especificar una orquestación que se va a dar de alta en un host.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 La versión de VBScript del ejemplo para dar de alta una orquestación consta de un archivo de secuencias de comandos de Visual Basic que no necesita generar o inicializar.  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a>Para generar la versión de Visual C# del ejemplo para dar de alta una orquestación  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución BTSampleEnlistOrc.sln.  
  
2.  En el **generar** menú, haga clic en **generar solución**.  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a>Para ejecutar el ejemplo para dar de alta una orquestación.  
  
1.  En una ventana de comandos, desplácese a una de las carpetas siguientes, dependiendo de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente:  
  
     \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
     \<*Ejemplos de ruta de acceso*\>AdminWMIEnlist OrchestrationCSharpbinDebug  
  
2.  Ejecute el archivo EnlistOrch.vbs que usa el programa Cscript, o ejecute el archivo EnlistOrc.exe, en función de si va a ejecutar la versión de VBScript o la versión de Visual C# de este ejemplo, respectivamente: En cualquier evento, pase los siguientes argumentos de línea de comandos:  
  
    -   **\<** ***OrchestrationName* \>.** El nombre de la orquestación que se va a dar de alta.  
  
    -   **\<** ***AssemblyName* \>.** El nombre del ensamblado en el que se ha implementado la orquestación. Si el nombre del ensamblado contiene espacios, enciérrelo entre comillas.  
  
         Por ejemplo: (VBScript):  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         -O bien- (Visual C#):  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración también puede realizarse mediante el uso de script que tiene acceso al modelo de objetos de WMI de Windows y con Visual C# que tiene acceso a la **System.Management** objetos proporcionados .NET Framework.  
  
 El archivo de secuencias de comandos EnlistOrch.vbs y el archivo de origen de Visual C# EnlistOrc.cs contienen comentarios detallados con más explicaciones sobre las operaciones que realizan. Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [Admin\WMI (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)