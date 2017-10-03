---
title: Crear un previos o posteriores a la secuencia de comandos de procesamiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scripts, post-processing
- scripts, pre-processing
- scripts, warnings
- scripts, applications
- applications, scripts
- scripts, deploying
- deploying, scripts
ms.assetid: d5fbaec8-fbfe-4ceb-8ba8-0933baa37a1f
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532c730d5a654512610a37c9dac783fbc6a76d6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-pre--or-post-processing-script"></a>Crear secuencias de comandos previas y posteriores al procesamiento
Puede crear una secuencia de comandos para realizar acciones cuando se implementa una aplicación y, a continuación, definir en qué momento se ejecutará durante el proceso de implementación. Puede incluir tanto código de limpieza como código de instalación en la misma secuencia de comandos si utiliza variables de entorno para delimitar el código. También puede pasar argumentos de línea de comandos a la secuencia.  
  
> [!CAUTION]
>  Siempre debería escribir en modo silencioso las secuencias de comandos orientadas a los sistemas de producción. Esto se debe a que las secuencias de comandos que esperan la entrada del usuario provocarán que las bases de datos de BizTalk se bloqueen y permanezcan inaccesibles hasta que se reciba la entrada.  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a>Especificar en qué momento se ejecutará una secuencia de comandos durante la implementación  
 Especifique en qué momento se ejecutará una secuencia de comandos cuando agregue la secuencia a una aplicación agregándola como System.BizTalk:PreProcessingScript (secuencia de comandos previa al procesamiento) o como System.BizTalk:PostProcessingScript (secuencia de comandos posterior al procesamiento).  
  
 Las secuencias de comandos previas y posteriores al procesamiento se ejecutan de la siguiente forma:  
  
-   Las secuencias de comandos previas al procesamiento se ejecutan al principio del proceso de importación o de instalación.  
  
-   Las secuencias de comandos posteriores al procesamiento se ejecutan al final del proceso de importación o de instalación.  
  
-   Durante la desinstalación, todas las secuencias se ejecutan en el orden inverso al que se ejecutan durante la instalación. Por lo tanto, las secuencias de comandos posteriores al procesamiento se ejecutan al principio del proceso de desinstalación y las secuencias de comandos previas al procesamiento lo hacen al final.  
  
-   Si se produce un error en la instalación, se llama a las secuencias de comandos en el orden inverso con la acción adecuada para deshacer.  
  
 Una vez invocado, una secuencia de comandos previa y posteriores al procesamiento determina el estado de implementación (instalar, importar, eliminar, desinstalar, Deshacer importación o deshacer instalación) se está ejecutando mediante la comprobación de las variables de entorno BTAD_ChangeRequestAction, BTAD_InstallMode, y BTAD_HostClass, como se describe en [estado de implementación de indique de Variables de entorno de cómo](../core/how-environment-variables-indicate-deployment-state.md). Para obtener información de referencia acerca de las variables, consulte [las Variables de entorno de secuencia de comandos previas y posteriores al procesamiento](../core/pre-and-post-processing-script-environment-variables.md).  
  
 Para obtener instrucciones sobre cómo agregar una secuencia de comandos a una aplicación, consulte [cómo agregar un prefijo o procesamiento posterior a la secuencia de comandos a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).  
  
> [!NOTE]
>  Si desea incluir argumentos de línea de comandos en una secuencia de comandos, debe utilizar el comando AddResource para agregar la secuencia como se explica más adelante en este tema.  
  
## <a name="supported-script-file-extensions"></a>Extensiones de archivos de secuencias de comandos admitidas  
 Se admiten las siguientes extensiones de archivo de script: .com, .exe, .bat, .cmd, .vbs, .vbe, .js, .jse, .wsf y WSH. Este conjunto de extensiones se define en la variable de entorno PATHEXT.  
  
## <a name="logging-errors"></a>Errores de registro  
 Se recomienda configurar todas las secuencias de comandos para que registren errores en un archivo. Windows Installer no registra los errores que se generan en las secuencias de comandos. Una vez que se ejecute la secuencia de comandos, debería comprobar la existencia de errores que deban solucionarse en estos registros.  
  
 Para que le ayude a determinar en qué momento se produce el error, puede incluir la fecha y la hora en el archivo de registro.  
  
 Utilice el siguiente código para especificar un archivo de registro y, a continuación, registre un error en él.  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 En el siguiente ejemplo, cuando el token de clave pública no está definido, se realiza una entrada en el archivo de registro especificado. En el archivo de registro, la fecha y la hora aparecen en la misma línea del texto "La clave pública debería estar definida en la secuencia de comandos".  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 También puede agregar la línea `exit /b 1` a una secuencia de comandos para generar un código de error de Windows Installer, lo que provocará que se revierta.  
  
 En el siguiente ejemplo, si no se ha definido el token de clave público, la secuencia de comandos devolverá un error a Windows Installer y el instalador se revertirá.  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a>Incluir código de limpieza y de instalación en la misma secuencia de comandos  
 Debido a que las secuencias de comandos se ejecutan en orden inverso durante la instalación y la desinstalación, puede incluir el código de limpieza y de instalación en la misma secuencia de comandos dentro de una instrucción condicional. Por ejemplo, puede colocar el código de instalación dentro de una instrucción condicional que comprueba el modo de instalación de la siguiente forma:  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 Puede calificar el código de limpieza dentro de una instrucción condicional que comprueba el modo de instalación de la siguiente forma:  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a>Pasar argumentos de línea de comandos  
 Puede pasar argumentos de línea de comandos a la secuencia de comandos especificando el siguiente parámetro cuando utilice el comando BTSTask AddResource para agregar la secuencia de comandos a la aplicación. Cuando lo haga, los argumentos pasan a la secuencia de comandos cuando ésta se invoca.  
  
 **/ Property: args =**"*lista de argumentos*"  
  
> [!NOTE]
>  Si tiene varias secuencias de comandos previas o posteriores al procesamientos en una aplicación, no se ejecutan en un orden determinado.  
  
> [!IMPORTANT]
>  No debería utilizar los comandos BTSTask en secuencias de comandos, especialmente los que se ejecutan durante la importación ya que las secuencias de comandos no están dadas de alta en la misma transacción como importación.  
  
 Para obtener instrucciones sobre cómo usar el comando AddResource para agregar una secuencia de comandos a una aplicación, consulte [comando AddResource: secuencia de comandos de preprocesamiento](../core/addresource-command-preprocessing-script.md). Consulte también [comando AddResource: secuencias de comandos](../core/addresource-command-postprocessing-script.md)  
  
## <a name="see-also"></a>Vea también  
 [Uso de secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicación](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [Plantilla (ejemplo de implementación de aplicaciones)](../core/template-application-deployment-sample.md)