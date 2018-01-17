---
title: Configurar la FileAct e interactuar adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3876ff-e8e4-47f4-9ca8-d4dad419ed67
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2bc3aa739bf6914ea9943d84d58d44b1506323
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="configure-the-fileact-and-interact-adapter"></a>Configurar la FileAct e interactuar adaptador
Configurar los diferentes artefactos utilizados por el [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] en tiempo de ejecución. 

  
## <a name="prerequisites"></a>Requisitos previos  
   
-   Instalar el[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]
  
-   Inicie sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo de administradores
  
-   Confirme que está ejecutando SQL Server
  
## <a name="step-1-configure-the-fileact-and-interact-adapter"></a>Paso 1: Configurar el adaptador de FileAct e InterAct  
  
1.  En el **FileAct de BizTalk de Microsoft e interactuar configuración del adaptador** asistente, vaya a **Introducción**. En el panel izquierdo, seleccione **en tiempo de ejecución** para configurar los componentes en tiempo de ejecución de los adaptadores.  
  
2.  En **configuración en tiempo de ejecución**, en **cuenta**, seleccione los puntos suspensivos […] para escribir el COM más la configuración para el modo de almacenamiento y reenvío.  
  
3.  En **las credenciales de usuario**, escriba el nombre de usuario (en el *ombre* formato) y una contraseña para la cuenta utilizada en COM además de la configuración. Seleccione **Aceptar**.  
  
    > [!NOTE]
    >  A **las credenciales de usuario** advertencia aparece si la cuenta que especificó tiene privilegios más elevados que se recomiendan. Seleccione **Sí** para continuar.
  
4.  Seleccione **aplicar configuración** para aplicar el COM más la configuración para el adaptador de interactuar and FileAct.  
  
5.  En el **resumen**, revise y seleccione **siguiente**.  
  
6.  Cuando se completa la configuración, revise la lista de componentes. Una marca de verificación significa que el componente está configurado correctamente. Una "X" significa que hay un problema con ese componente.  
  
    > [!NOTE]
    >  Use la **archivo de registro** vínculo para ver los eventos de configuración.  
  
7.  Seleccione **finalizar** para completar la configuración. El **Introducción** muestra el estado actual de la configuración de los componentes en tiempo de ejecución.  

A continuación, cree el host y las instancias de host para ejecutar estos adaptadores.

## <a name="step-2-create-the-host-and-host-instances"></a>Paso 2: Crear el host e instancias de host

Le recomendamos que cree un host dedicado para el adaptador de FileAct y un host independiente dedicado para el adaptador de InterAct. Para cada adaptador, cree al menos una instancia de host.  

[Administración de Hosts de BizTalk y las instancias de Host](../../core/managing-biztalk-hosts-and-host-instances.md) enumeran los pasos para crear hosts e instancias de host. 

Una vez creado, el siguiente paso es agregar el controlador de envío y usar al asociado de mensaje de cliente que creó en la puerta de enlace de Alliance de SWIFT (SAG).

## <a name="step-3-create-the-send-handler"></a>Paso 3: Crear el controlador de envío

Puede utilizar el FileAct y InterAct enviar propiedades del controlador como el envío valores de configuración de puerto, si no se establecen las propiedades en el FileAct individual o puerto de envío de interacción. 
  
1.  En el **administración de BizTalk Server** de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **deconfiguracióndeplataforma**y, a continuación, expanda **adaptadores**.  
  
2.  Seleccione el **FileAct** o **InterAct** adaptador. En el panel derecho, haga doble clic en el controlador de envío.  
  
3.  En el **nombre de Host** lista desplegable, seleccione el host que creó en la sección anterior. A continuación, seleccione **propiedades**.  
  
4.  En el **propiedades de transporte**, seleccione la **argumento** propiedad y escriba el siguiente argumento como:  
  
     `-SagMessagePartner <Client Message Partner created in SAG\>`
  
    > [!NOTE]
    >  Reemplace <`Client Message Partner created in SAG`> con el nombre del asociado de mensaje de cliente. Deje los valores predeterminados para el modo de cifrado, modo de FACrypto y propiedades LogMessages.  
  
5.  Seleccione **Aceptar** para guardar los cambios y, a continuación, cierre la ventana Propiedades. 
  
6.  En **configuración de plataforma**, seleccione **instancias de Host**.  
  
7. Reinicie las instancias de host: 

  - Haga clic en la instancia de host de FileAct y **reiniciar**
  - Haga clic en la instancia de host interactuar y **reiniciar**.  

A continuación, escriba los asociados de mensaje de servidor en el paramfile SWIFTNet para habilitar la FileAct y adaptadores de recepción interactuar.
  
## <a name="step-4-configure-the-swiftnet-param-file"></a>Paso 4: Configurar el archivo de param SWIFTNet

Para habilitar la FileAct e InterAct adaptadores de recepción para inicializar con los valores, el mensaje del servidor socios que creó en SAG deben especificarse en el paramfile SWIFTNet. El paramfile normalmente se encuentra en `c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`. Después de configurar la paramfile, iniciar **SnlReceiver.exe**.  
  
1. Abra la **SWIFTNet paramfile**. En la ubicación marcada con "***" agregue lo siguiente. Tenga en cuenta que la `AdapterType` valor puede ser `Interact` o `Fileact`.  
  
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
    >  Antes de empezar SNLreceiver, habilitar los puertos de recepción para el adaptador que usa (FileAct o que interactúen).  
  
2. Iniciar y detener SnlReceiver.exe:

    1.  En el escritorio, seleccione la **remota (API)** icono para abrir el símbolo del sistema de remota (API).  
  
    2.  En el símbolo del sistema, escriba `Swiftnet start`. Presione ENTRAR para iniciar SnlReceiver.exe.  
  
    3.  En el símbolo del sistema, escriba `Swiftnet stop`. Presione ENTRAR para detener SnlReceiver.exe.  

  
A continuación, actualice el archivo **autoexec.bat** para establecer las variables de entorno de SWIFT.

## <a name="step-5-update-autoexecbat-to-configure-the-receive-adapters"></a>Paso 5: Actualizar archivos autoexec.bat para configurar los adaptadores de recepción

Actualización de la **autoexec.bat** archivo para establecer las variables de entorno de SWIFT en el equipo donde instaló el [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] adaptadores de recepción. Las variables de entorno se generan a partir del sistema que tiene el adaptador de recepción que se instalan en la ruta de acceso `c:\SWIFTAlliance` con una instancia del adaptador de recepción denominado **ar1**. Actualizar las variables de entorno SWIFT correctamente para la configuración.  
  
 El siguiente es un ejemplo del archivo autoexe.bat:
  
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
  
## <a name="see-some-examples"></a>Se muestran algunos ejemplos
Para obtener ejemplos de mensajes de FileAct e InterAct, consulte [interactuar de ejemplo y los mensajes de FileAct](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md).  
  
## <a name="see-also"></a>Vea también  

[Instalar los adaptadores FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/install-the-fileact-and-interact-adapter.md)  
[Desinstalar o reparar el adaptador de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[Leer los problemas de instalación conocidos](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
