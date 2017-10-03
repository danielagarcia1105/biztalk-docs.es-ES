---
title: "Cómo modificar la configuración de la limitación de memoria de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Bts10.settings.HostInstanceOrchestration
ms.assetid: f6953c68-7809-4518-87ec-e75c98884af3
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c48f1ec5e74ae577a7c1d130e22f3b4a1b53874c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a>Modificación de la configuración de limitación de la memoria de orquestación
El mecanismo de limitación de memoria de instancias de host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supervisa continuamente si se produce una condición de limitación, calcula la gravedad de dicha condición y aplica progresivamente la limitación de memoria de instancias de host dependiendo de la gravedad calculada. En este tema se proporcionan instrucciones paso a paso para modificar esta configuración mediante el panel de configuración.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a>Procedimiento para modificar la configuración de la limitación de la memoria de orquestación de una instancia de host  
  
1.  En el **consola de administración de BizTalk Server**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
2.  En el **panel de configuración de BizTalk** cuadro de diálogo, en la **instancias de Host** página, haga clic en el **limitación de memoria de orquestación** ficha.  
  
3.  Realice lo siguiente y, a continuación, haga clic en **aplicar** para aplicar las modificaciones y continuar en otra ficha. O haga clic en **Aceptar** para aplicar las modificaciones y salir del panel de configuración.  
  
    |Use|Para|Valores límite|Valor predeterminado|  
    |--------------|----------------|---------------------|-------------------|  
    |**Instancia de host**|En el cuadro de lista desplegable, seleccione la instancia en ejecución de un host en el equipo en tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|-|-|  
  
     **Físico**  
  
    |Use|Para|Valores límite|Valor predeterminado|  
    |--------------|----------------|---------------------|-------------------|  
    |**Uso óptimo**|Especifique el porcentaje de uso de la memoria física en que la limitación de deshidratación entra en efecto. Este es el porcentaje óptimo de memoria física que se va a usar para las instancias de host.|[0 – 100]|70|  
    |**Uso máximo**|Especifique el porcentaje de uso de memoria física en que la limitación de deshidratación es máxima. Este es el porcentaje máximo de memoria física que se va a usar para las instancias de host.<br /><br /> El valor mínimo de **uso máximo** debe ser **uso óptimo**.|(Uso óptimo – 100]<br /><br /> Excepto cuando ambas son 0 o 100.|85|  
  
     **Virtual**  
  
    |Use|Para|Valores límite|Valor predeterminado|  
    |--------------|----------------|---------------------|-------------------|  
    |**Uso óptimo**|Especifique el porcentaje de uso de memoria virtual en que la limitación de deshidratación entra en efecto.<br /><br /> En este momento, **TestThreshold** tiene el valor **MaxThreshold** y cualquier uso de memoria mayor **OptimalUsage** hace **TestThreshold**sea inferior a **MaxThreshold**.|[0 – 100]|65|  
    |**Uso máximo**|Especifique el porcentaje de uso de memoria virtual en que la limitación de deshidratación es máxima.<br /><br /> En este momento, **TestThreshold** tiene el valor **MinThreshold** y cualquier uso de memoria inferior a **MaximalUsage** hace **TestThreshold** debe ser mayor que **MinThreshold**.|(Uso óptimo – 100]<br /><br /> Excepto cuando ambas son 0 o 100.|85|  
  
    > [!NOTE]
    >  Para restaurar la configuración predeterminada, haga clic en **Restaurar valores predeterminados**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo modificar la configuración de la instancia de Host](../core/how-to-modify-host-instance-settings.md)