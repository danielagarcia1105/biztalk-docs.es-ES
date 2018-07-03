---
title: Configurar la FileAct e InterAct adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d3876ff-e8e4-47f4-9ca8-d4dad419ed67
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d62e4cf0896e755a0ec8ece00d6a2140210b463
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974605"
---
# <a name="configure-the-fileact-and-interact-adapter"></a>Configurar la FileAct e InterAct de adaptador
Configurar los diferentes artefactos usados por la [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] en tiempo de ejecución. 

  
## <a name="prerequisites"></a>Requisitos previos  
   
- Instale la [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]
  
- Inicie sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo de administradores
  
- Confirme que se está ejecutando SQL Server
  
## <a name="step-1-configure-the-fileact-and-interact-adapter"></a>Paso 1: Configurar el adaptador de FileAct e InterAct  
  
1.  En el **Microsoft BizTalk FileAct y configuración del adaptador interactúe** asistente, vaya a **Introducción**. En el panel izquierdo, seleccione **en tiempo de ejecución** para configurar los componentes en tiempo de ejecución de los adaptadores.  
  
2.  En **configuración en tiempo de ejecución**, en **cuenta**, seleccione los puntos suspensivos […] para introducir el COM plus configuración para el modo de avance y Store.  
  
3.  En **las credenciales de usuario**, escriba el nombre de usuario (en el *ombre* formato) y la contraseña de la cuenta usada en el COM además la configuración. Seleccione **Aceptar**.  
  
    > [!NOTE]
    >  Un **las credenciales de usuario** advertencia aparece si la cuenta especificada tiene más privilegios que se recomiendan. Seleccione **Sí** para continuar.
  
4.  Seleccione **aplicar configuración** para aplicar el COM plus configuración al adaptador interactuar y FileAct.  
  
5.  En el **resumen**, revise y seleccione **siguiente**.  
  
6.  Cuando se complete la configuración, revise la lista de componentes. Una marca de verificación significa que el componente está configurado correctamente. Una "X" significa que hay un problema con ese componente.  
  
    > [!NOTE]
    >  Use la **Logfile** vínculo para ver los eventos de configuración.  
  
7.  Seleccione **finalizar** para completar la configuración. El **Introducción** muestra el estado actual de la configuración de los componentes en tiempo de ejecución.  

A continuación, cree el host y las instancias de host para ejecutar estos adaptadores.

## <a name="step-2-create-the-host-and-host-instances"></a>Paso 2: Crear el host y las instancias de host

Le recomendamos que cree un host dedicado para el adaptador de FileAct y un host independiente dedicado para el adaptador de InterAct. Para cada adaptador, cree al menos una instancia de host.  

[Administración de Hosts de BizTalk y las instancias de Host](../../core/managing-biztalk-hosts-and-host-instances.md) enumeran los pasos para crear hosts e instancias de host. 

Una vez creado, el siguiente paso es agregar el controlador de envío y usar al asociado de mensaje de cliente que creó en la puerta de enlace de Alliance SWIFT (SAG).

## <a name="step-3-create-the-send-handler"></a>Paso 3: Crear el controlador de envío

Utilice el FileAct y InterAct enviar propiedades del controlador como el envío valores de configuración de puerto, si no se establecen las propiedades en el FileAct individual o puerto de envío InterAct. 
  
1. En el **administración de BizTalk Server** de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **deconfiguracióndeplataforma**y, a continuación, expanda **adaptadores**.  
  
2. Seleccione el **FileAct** o **InterAct** adaptador. En el panel derecho, haga doble clic en el controlador de envío.  
  
3. En el **nombre de Host** lista desplegable, seleccione el host que creó en la sección anterior. A continuación, seleccione **propiedades**.  
  
4. En el **propiedades de transporte**, seleccione el **argumento** propiedad y escriba el siguiente argumento como:  
  
    `-SagMessagePartner <Client Message Partner created in SAG\>`
  
   > [!NOTE]
   >  Reemplace <`Client Message Partner created in SAG`> con el nombre del asociado de mensaje de cliente. Deje los valores predeterminados para el modo criptográfico y modo FACrypto LogMessages propiedades.  
  
5. Seleccione **Aceptar** para guardar los cambios y, después, cierre la ventana Propiedades. 
  
6. En **configuración de plataforma**, seleccione **instancias de Host**.  
  
7. Reinicie las instancias de host: 

   - Haga clic en la instancia de host de FileAct y **reiniciar**
   - Haga clic en la instancia de host de interacción y **reiniciar**.  

A continuación, escriba los asociados de mensaje de servidor en el archivo de parámetros de SWIFTNet para habilitar la FileAct y adaptadores de recepción InterAct.
  
## <a name="step-4-configure-the-swiftnet-param-file"></a>Paso 4: Configurar el archivo de parámetros de SWIFTNet

Para habilitar el FileAct e InterAct adaptadores para inicializar con los valores, el mensaje de servidor asociados creados en SAG deben especificarse en el archivo de parámetros de SWIFTNet de recepción. El archivo de parámetros se encuentra normalmente en `c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`. Después de configurar el archivo de parámetros, iniciar **SnlReceiver.exe**.  
  
1. Abra el **el archivo de parámetros de SWIFTNet**. En la ubicación marcada con "***" agregue lo siguiente. Tenga en cuenta que el `AdapterType` valor puede ser `Interact` o `Fileact`.  
  
     ```spawn "snlreceiver -SagMessagePartner <Server MessagePartnerName\> -AdapterMode <AdapterType\>"```  
       
  
   ```  
    username:snlowner  
    subsystem_name:SampleSubsystem  
    #subsystem_group: SampleSubsystem  
    #subsystem_dependency:Support,Swarm  
    subsystem_nature:critical  
    subsystem_start:  
    ***  
    *END  
    subsystem_stop:  
    *KILL9:snlreceiver  
    *END  
    subsystem_status:  
    *NB:1:snlreceiver  
    *END  
    start_event:SNL001:subsystem SampleSubsystem is up  
    stop_event:SNL002:subsystem SampleSubsystem is down  
   ```  
  
> [!NOTE]
>  Antes de empezar SNLreceiver, habilite los puertos de recepción para el adaptador está utilizando (FileAct o interacción).  
  
2. Iniciar y detener SnlReceiver.exe:

    1.  En el escritorio, seleccione el **API remota** icono para abrir el símbolo de la API remota.  
  
    2.  En el símbolo del sistema, escriba `Swiftnet start`. Presione ENTRAR para iniciar SnlReceiver.exe.  
  
    3.  En el símbolo del sistema, escriba `Swiftnet stop`. Presione ENTRAR para detener SnlReceiver.exe.  

  
A continuación, actualice el archivo **autoexec.bat** para establecer las variables de entorno de SWIFT.

## <a name="step-5-update-autoexecbat-to-configure-the-receive-adapters"></a>Paso 5: Actualización autoexec.bat para configurar los adaptadores de recepción

Actualización de la **autoexec.bat** archivo para establecer las variables de entorno de SWIFT en el equipo donde instaló el [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] adaptadores de recepción. Las variables de entorno se generan desde el sistema que tiene el adaptador de recepción que se instalan en la ruta de acceso `c:\SWIFTAlliance` con una instancia del adaptador de recepción denominado **ar1**. Actualice las variables de entorno SWIFT apropiado para su configuración.  
  
 Este es un ejemplo del archivo autoexe.bat:
  
```  
SET COMPUTERNAME=<Machine Name>  
SET GENLOG_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET GENUTIL_DIR=C:\SWIFTAlliance\RA\bin  
SET HOMEDRIVE=C:  
SET LOGONSERVER=\\SERVERNAME  
SET OSA_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET OSA_INSTANCE=Ra1  
SET PKIEXECDIR=C:\SWIFTAlliance\RA  
SET SAGRA_HOME=C:\SWIFTAlliance\RA  
SET SESSIONNAME=RDP-Tcp#1  
SET SLP_ENV=DEFAULT  
SET SLP_FILE=server.slp  
SET SNL_DOMAIN_NAME=Ra1  
SET SPK_DATA_DIR=C:\SWIFTAlliance\RA\data\pki  
SET SWNET_BIN_PATH=C:\SWIFTAlliance\RA\Ra1\bin  
SET SWNET_CFG_PATH=C:\SWIFTAlliance\RA\Ra1\cfg  
SET SWNET_HOME=C:\SWIFTAlliance\RA  
SET SWNET_HOST=HOSTNAME  
SET SWNET_INST=Ra1  
SET SWNET_LOG_PATH=C:\SWIFTAlliance\RA\Ra1\log  
SET SWNET_SLP_PATH=C:\SWIFTAlliance\RA\data\  
SET SWNET_VERSION=5.0.20  
SET SWTRACE=C:\SWIFTAlliance\RA\Ra1\log  
SET Path=%PATH%;C:\SWIFTAlliance\RA\bin  
SET Path=%PATH%;C:\SWIFTAlliance\RA\lib  
  
```  
  
## <a name="see-some-examples"></a>Vea algunos ejemplos
Para obtener ejemplos de FileAct e InterAct de mensajes, vea [interactuar de ejemplo y los mensajes de FileAct](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md).  
  
## <a name="see-also"></a>Vea también  

[Instalar los adaptadores FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/install-the-fileact-and-interact-adapter.md)  
[Desinstalar o reparar el adaptador de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[Leer los problemas de instalación conocidos](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
