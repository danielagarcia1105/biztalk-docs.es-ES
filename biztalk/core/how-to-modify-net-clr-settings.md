---
title: Cómo modificar la configuración de .NET CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceCLR
ms.assetid: 085743d8-27a6-4d8b-98c7-bb5b5c75848c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe3d54aa508d45211277377c2f2d8880c37044d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015157"
---
# <a name="how-to-modify-net-clr-settings"></a>Modificación de la configuración de .NET CLR
Para actualizar la cantidad de subprocesos de Windows disponibles en el grupo de subprocesos .NET asociado a una instancia del host de BizTalk, puede modificar los valores de hospedaje de Common Runtime Language (CLR) apropiados desde el panel de configuración de BizTalk. En este tema se proporciona el procedimiento paso a paso para modificar esta configuración.  

## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  

### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a>Procedimiento para modificar la configuración de .NET CLR de una instancia de host  

1. En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  

2. En el **panel de configuración de BizTalk** cuadro de diálogo el **instancia de Host** pestaña, haga clic en el **.NET CLR** ficha.  

3. Haga lo siguiente y haga clic en **aplicar** para aplicar las modificaciones y continuar en otra pestaña. O haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  


   |     Use      |                                                                                Para                                                                                | Valores límite | Valor predeterminado | Actualizar lógica |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|---------------|
   | **Instancia de host** | En el cuadro de lista desplegable, seleccione la instancia en ejecución de un host en el equipo en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. |        -        |       -       |       -       |

    **Configuración de subprocesos**  

   |Use|Para|Valores límite|Valor predeterminado|Actualizar lógica|  
   |--------------|----------------|---------------------|-------------------|-------------------|  
   |**Max. subprocesos de trabajo**|Especifique el número máximo de subprocesos de trabajo de .NET CLR.|[Subprocesos de trabajo mín., 500]|25|Migre la configuración del registro de instancias de host a la configuración de instancias de host, ignore Versión, Tipo, Marcas y MinCompletionPortThreads.|  
   |**Subprocesos de trabajo mín.**|Especifique el número mínimo de subprocesos de trabajo de .NET CLR.|[0, 500]|5|Migre la configuración del registro de instancias de host a la configuración de instancias de host, ignore Versión, Tipo, Marcas y MinCompletionPortThreads.|  
   |**Max. Subprocesos de E/S**|Especifique el número máximo de subprocesos de E/S.|[Subprocesos de E/S mín., 1000]|250|Migre la configuración del registro de instancias de host a la configuración de instancias de host, ignore Versión, Tipo, Marcas y MinCompletionPortThreads.|  
   |**Min. Subprocesos de E/S**|Especifique el número mínimo de subprocesos de E/S.|[0, 1000]|25|Migre la configuración del registro de instancias de host a la configuración de instancias de host, ignore Versión, Tipo, Marcas y MinCompletionPortThreads.|  

    La configuración de .NET CLR se realiza por CPU principal.  

   > [!NOTE]
   >  Para restaurar la configuración predeterminada, haga clic en **Restaurar valores predeterminados**.  

   > [!NOTE]
   >  **Subprocesos de trabajo** se usan para controlar los elementos de trabajo en cola y **subprocesos de E/S** son subprocesos dedicados de devolución de llamada asociados con un puerto de terminación de E/S para controlar una solicitud de E/S asincrónica completada.  

   > [!NOTE]
   >  Si se actualiza BizTalk desde una versión anterior, los valores de la HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$*hostname*\CLR se establecerá la clave del registro de hospedaje en el panel de configuración.  

## <a name="see-also"></a>Vea también  
 [Cómo modificar la configuración de la instancia de Host](../core/how-to-modify-host-instance-settings.md)