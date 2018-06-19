---
title: Solución de problemas y problemas conocidos con el Acelerador de RosettaNet de BizTalk (BTARN) se instalación en el servidor BizTalk Server | Documentos de Microsoft"
description: Recomendaciones para la instalación de SQL, la cuenta de servicio para las instancias de host y los errores conocidos con la instalación de BTARN en BizTalk Server
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdca89c1a7a4ed3834103776f9f28c8631c5de0a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22210844"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a>Solucionar problemas de la instalación y consulte los problemas de instalación conocidos

  
## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a>No instale SQL Server en el equipo del controlador de dominio  
 Si instala a SQL Server en el mismo equipo que el equipo de controlador de dominio, devuelve el siguiente mensaje de error cuando intenta crear los puertos de envío SQL:  
  
```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  

```
  
> [!IMPORTANT]
>  No instale a SQL Server en el equipo del controlador de dominio.  
  
## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a>La cuenta de servicio para los grupos de aplicaciones debe ser la misma que la cuenta de servicio para las instancias de host y de host aislado  
 Si la cuenta de servicio establecidos para los grupos de aplicación de BTARN es diferente de la cuenta de Host aislado, BTARN no procesa correctamente los mensajes entrantes. Cuando la página .aspx de recepción llama a la canalización, la canalización no tiene acceso a los certificados apropiados. Por lo tanto, no descifrar el mensaje entrante ni validar la firma. Además, no podrá tener acceso a la base de datos de cuadro de mensajes.  
  

## <a name="known-install-issues"></a>Problemas de instalación conocidos

  
### <a name="btarn-http-front-end-feature-configuration-fails"></a>Se produce un error en la configuración de la característica de Front-End de BTARN HTTP  
 **Problema**  
  
 Si lleva a cabo una instalación personalizada para instalar solo la característica Front-end HTTP de BTARN, la configuración de BTARN puede dar error después de completarse la instalación con el siguiente mensaje: 

`Failed to create object for feature: WebApp`  
  
 **Resolución**  
  
Manualmente, copie los archivos y vuelva a configurar: 
  
1.  Copie los dos archivos siguientes desde un equipo de servidor BizTalk Server en el equipo en el que haya instalado la característica de Front-End de HTTP de BTARN:
  
    -   Microsoft.VC80.ATL.manifest  
  
    -   atl80.dll  
  
     Si Visual Studio está instalado en el mismo equipo que BizTalk Server, la carpeta de origen de los dos archivos es <*unidad*>: \Program Visual Studio < versión\>\VC\redist\x86\Microsoft.VC100.ATL .  
  
     Si Visual Studio no está instalado en el mismo equipo de BizTalk Server, la carpeta de origen de los dos archivos se encuentra en <*unidad*>: \WINDOWS\WinSxS.  
  
2.  Agregue los archivos que ha copiado al equipo donde instaló la característica Front-end HTTP de BTARN. De forma predeterminada, copie los archivos en <*unidad*>: \Program Acelerador de BizTalk para RosettaNet.  
  
3.  Una vez que haya copiado los archivos en el equipo Front-End HTTP, ejecute **Configuration.exe** nuevo.  
  
### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a>Algunos ensamblados de BTARN permanecen en la GAC después de desinstalar  
 **Problema**  
  
 Al desinstalar BTARN, algunos ensamblados permanecen en la caché global de ensamblados (GAC).  
  
 **Resolución**  
  
 Quite los ensamblados de la GAC antes de reinstalar BTARN.  
  
 Use la **BtarnClean** utilidad desde el SDK para quitar los ensamblados. La utilidad hace lo siguiente:  
  
-   Detiene y da de baja todas las orquestaciones de BTARN.  
  
-   Detiene y elimina todos los puertos asociados.  
  
-   Anula la implementación de todos los ensamblados de Microsoft.Solutions.BTARN.*.  
  
 Después de ejecutar la utilidad, si quedan ensamblados en la GAC, abra el Explorador de Windows, vaya a la carpeta "C:\Windows\Assembly" y elimine manualmente todos los ensamblados que comienzan con Microsoft.Solutions.BTARN.  
  
### <a name="service-unavailable-error-on-64-bit-os"></a>Error de servicio no disponible en sistemas operativos de 64 bits
 **Problema**  
  
 Es posible que obtenga un `Service Unavailable` error al intentar obtener acceso a HTTP de BTARN recibir una ubicación en sistemas operativos de Windows de 64 bits.  
  
 **Cause**  
  
 Esto problema puede deberse al filtro ISAPI "RPCProxy.dll".  
  
 **Resolución**  
  
Quite las referencias al filtro ISAPI del proxy RPC y reiniciar IIS:
  
1.  En el Administrador de Internet Information Services (IIS), haga clic en **sitios Web**y, a continuación, haga clic en **propiedades**.  
  
2.  En el **propiedades de sitio Web** cuadro de diálogo, haga clic en el **filtros ISAPI** ficha, quite **Proxy RPC** filtrar y, a continuación, haga clic en **Aceptar**.  
  
3.  Reinicie IIS.  
  
4.  Después de reiniciar IIS, intente obtener acceso a http://localhost. Debería obtener el mensaje 400 del explorador de Internet.  
  
### <a name="sql-server-mixed-mode-not-supported"></a>Modo mixto de SQL Server no admite  
BTARN no es compatible con SQL Server en modo mixto.  
  
### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a>Ejecutar setupx64.bat para configurar el ejemplo de orquestación PIPAutomation de doble acción 

Ejecutar setupx64.bat en \Program BizTalk Accelerator for rosettanet\sdk\pipautomation\doubleaction para configurar el ejemplo de orquestación de PIPAutomation de doble acción.
  
### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a>Descargar el archivo de instalación de BTARN desde la Web en una carpeta temporal  
 **Problema**  
  
 Si descarga el archivo ejecutable desde el Web autoextraíble de BTARN y guardarlo en la carpeta raíz del servidor BizTalk Server, al intentar ejecutar el archivo ejecutable, BizTalk **Asistente para la instalación** se ejecuta, en lugar del Asistente de instalación de BTARN.  
  
 **Resolución**  
  
 Descargue el ejecutable autoextraíble de BTARN y guarde el archivo en una carpeta temporal.
