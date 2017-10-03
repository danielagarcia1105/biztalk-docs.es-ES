---
title: "Mensaje de Error de instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation, error message
- error messages, installation
ms.assetid: 593b033f-03da-43ae-a948-f87aa5e4bccd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d3f7bbe9440c737b803eb1e6ae04e96449bf4f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installation-error-message"></a>Mensaje de error de instalación
Tras instalar el adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service, definir una ubicación de recepción o de envío puede dar lugar al siguiente error:  
  
 El motor de mensajería no se pudo agregar una dirección URL de recepción "\< dirección URL de ubicación de envío/recepción >" para el adaptador "TIBCO EMS". Motivo: "ensamblado de nombre de archivo o TIBCO. EMS o uno de sus dependencias no se encontró."  
  
## <a name="possible-causes"></a>Posibles causas  
 Este error se suele producir por una de las siguientes causas.  
  
### <a name="assembly-not-in-gac"></a>Ensamblado no en la GAC  
 El adaptador de BizTalk para TIBCO EMS es una aplicación .NET Framework y utiliza el ensamblado de .NET Framework, TIBCO.EMS. Este ensamblado debe estar presente en la caché de ensamblados global (GAC) de .NET Framework para que .NET Framework lo busque en el tiempo de ejecución.  
  
#### <a name="solution"></a>Solución  
 Para determinar si el ensamblado está presente en la GAC, abra un símbolo del sistema y escriba el siguiente comando:  
  
 `GACUTIL /L TIBCO.EMS`  
  
 Si el resultado no muestra ningún elemento, debe agregar el ensamblado a la GAC. Para ello, abra un símbolo del sistema, cambie los directorios al directorio de instalación TIBCO EMS clients\cs (la ubicación de instalación predeterminada es C:\TIBCO\EMS\Clients\CS) y ejecute el siguiente comando:  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a>Versión distinta de ensamblado en la GAC  
 El ensamblado TIBCO.EMS.dll está en la GAC, pero es una versión distinta de la que se usa para crear el adaptador de BizTalk para TIBCO EMS. Si TIBCO.EMS.dll que se ha instalado en el equipo es de una versión del producto 4.2 o superior, debe ser compatible con la versión utilizada para crear el adaptador (puede verificar dicha información con TIBCO).  
  
#### <a name="solution"></a>Solución  
 .NET Framework proporciona una forma para solucionar este problema. Se llama *redirección de enlace*, que utiliza un archivo de configuración.  
  
 Siga estos pasos para eliminar el mensaje de error:  
  
1.  Con un editor de texto, abra el archivo BTSNTSVC.exe.config.  
  
     El archivo se encuentra en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directorio (la ubicación de instalación predeterminada es: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]).  
  
2.  Agregue la siguiente entrada al archivo BTSNTSVC.exe.config, como un elemento secundario de la \<assemblyBinding > elemento:  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 Si no se ha modificado previamente el archivo BTSNTSVC.exe.config, el \<assemblyBinding > elemento no sería similar al siguiente:  
  
```  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
    <probing privatePath="BizTalk Assemblies;Developer  
        Tools;Tracking;Tracking\interop" />  
    <dependentAssembly>  
        <assemblyIdentity name='TIBCO.EMS'  
            publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
        <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
            newVersion='1.0.0.0' />  
    </dependentAssembly>  
</assemblyBinding>  
```  
  
1.  En un símbolo del sistema, escriba el comando: `GACUTIL /L TIBCO.EMS`.  
  
2.  Copie el número de versión del ensamblado TIBCO.EMS desde la salida.  
  
    > [!CAUTION]
    >  Aparecen dos números de versión: uno es el número de versión de la utilidad gacutil. Desea que el segundo número de versión, que aparece justo después **versión =**.  
  
3.  Pegue el número de versión en el archivo BTSNTSVC.exe.config, entre comillas, justo después de **newVersion =** (caracteres en negrita en el ejemplo XML anterior).  
  
4.  Guarde el archivo BTSNTSVC.exe.config modificado.  
  
5.  Reinicie el host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de TIBCO Enterprise Message Service](../core/troubleshooting-tibco-enterprise-message-service.md)