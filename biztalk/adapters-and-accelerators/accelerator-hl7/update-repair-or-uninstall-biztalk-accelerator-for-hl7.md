---
title: Actualizar, reparar o desinstalar el Acelerador de BizTalk para HL7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2fc84d2-1262-4a6e-ae9c-488a00ab4099
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a63f015541c93f1fb2000eed064aaa50df0fca86
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977317"
---
# <a name="update-repair-or-uninstall-biztalk-accelerator-for-hl7"></a>Actualizar, reparar o desinstalar el Acelerador de BizTalk para HL7

Cambiar, reparar o desinstalar el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].  
  
> [!IMPORTANT]
>  No olvide desinstalar [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] antes de desinstalar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] no se puede desinstalar si [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ya no está instalado.  

## <a name="prerequisites"></a>Requisitos previos
* Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  

* Esta cuenta de usuario también debe ser miembro del grupo Administradores en el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que almacena el Acelerador de BizTalk para HL7 datos.  
    
## <a name="update-an-existing-installation"></a>Actualizar una instalación existente

> [!NOTE]
>  Al modificar la instalación de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], el Tutorial to-End no se ejecuta automáticamente. 
> 
> Para ejecutar el tutorial y comprobar que la instalación modificada se ha ejecutado correctamente, ejecute el tutorial manualmente desde el ***\<unidad\>*** **\Program Files\Microsoft BizTalk \< versión\> acelerador HL7\SDK\End a otro tutorial** carpeta.
  
1. Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** como administrador 
  
2. En la página de bienvenida, seleccione **siguiente**.  
  
3. En **mantenimiento del programa**, seleccione **modificar**y, a continuación, seleccione **siguiente**.  
  
4. En **instalación personalizada**, seleccione las características que desea instalar, desactive las características no desee y, a continuación, seleccione **siguiente**.  
  
5. En el resumen, seleccione **siguiente**.  
  
6. Seleccione **Instalar**.  
  
7. Cuando haya finalizado, seleccione **Finalizar**.  

## <a name="repair-an-existing-installation"></a>Reparar una instalación existente
El [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] Asistente para repara una instalación mediante la corrección de los archivos ausentes o dañados, accesos directos o entradas del registro.  
  
1. Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** como administrador.  
  
2. En la página de bienvenida, seleccione **siguiente**.  
  
3. En **mantenimiento del programa**, seleccione **reparación**y, a continuación, seleccione **siguiente**.  
  
4. En **cuenta de servicio de registro**, vuelva a escribir la cuenta de usuario y, a continuación, seleccione **Aceptar**.  
  
5. Si se le solicita **tiene concedido al nombre de cuenta de inicio de sesión como un servicio adecuado**, a continuación, seleccione **Aceptar** para continuar.  
  
6. Cuando esté listo para reparar, seleccione **instalar**.  
  
7. Cuando haya completado, seleccione **finalizar**. 

  
## <a name="uninstall-btahl7"></a>Desinstalar BTAHL7  

> [!IMPORTANT]
>  Si hay una ubicación de recepción o puerto de envío mediante el tipo de transporte MLLP, el programa de instalación de BTAHL7 no quita el adaptador MLLP durante la desinstalación de BTAHL7. Antes de desinstalar, quitar todas las ubicaciones de recepción o envío puertos mediante el transporte MLLP. O bien, cambie el tipo de transporte de MLLP a otro tipo. A continuación, la desinstalación quitará el adaptador de MLLP.  
      
1. Abra **Programas y características**.  
  
2. Seleccione [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]y, a continuación, seleccione **desinstalar**.  
  
3. Seleccione **Sí** si se le pide que confirme. 
  
4. Cuando haya completado, seleccione **finalizar**.  
  
   > [!NOTE]
   >  BTAHL7 no desinstala automáticamente [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artefactos y ensamblados.  
  

  
## <a name="troubleshooting-installation-issues"></a>Solución de problemas de instalación  
 Si el servidor no puede validar si el usuario es un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] administrador, al desinstalar BTAHL7 devuelve el error siguiente: 
 
 `Fatal error during uninstallation`  
  
Para continuar con la desinstalación, haga lo siguiente:  
  
1. Inicie sesión como administrador local en el servidor.  
  
2. Desinstale [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
3. Desinstale [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].  
  
## <a name="see-also"></a>Vea también  
[Instalar o actualizar el Acelerador de Microsoft BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)