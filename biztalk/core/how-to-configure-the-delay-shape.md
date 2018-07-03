---
title: Cómo configurar la forma retraso | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer], configuring
- Delay shape [Orchestration Designer]
- Delay shape [Orchestration Designer], timeouts
- Delay shape [Orchestration Designer], about Delay shape
- configuring [Orchestration Designer], Delay shapes
ms.assetid: 727be28d-932a-41d5-af3f-3ee6f7129a17
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c00e002418dac53295828a4cbed632a6de0c235
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993653"
---
# <a name="how-to-configure-the-delay-shape"></a>Cómo configurar la forma Retraso
![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")  
Forma Retraso  
  
 Hay dos maneras de especificar el tiempo de espera para un **retraso**:  
  
- Puede usar **System.DateTime**, lo que hace que la orquestación se pause hasta que la fecha especificada y se alcanza el tiempo.  
  
   System.DateTime.UtcNow.AddSeconds(60)  
  
  > [!NOTE]
  >  Retrasos se deben expresar en hora Universal coordinada (UTC) cuando se usa **DateTime**.  
  
- Puede usar **System.TimeSpan**, lo que hace que la orquestación para pausarse durante el período de tiempo especificado.  
  
   System.TimeSpan(0, 1, 0)  
  
  Si su **retraso** forma está dentro de un **escuchar** forma, no es necesario agregar un punto y coma al final de la expresión.  
  
  Para obtener más información acerca de **System.DateTime** y **System.TimeSpan**, consulte "DateTime (estructura)" y "TimeSpan (estructura)" en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.  
  
> [!NOTE]
>  En un entorno de instalación de varios equipos donde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server están instalados en equipos separados, la **retraso** puede finalizar antes de lo esperado debido a las horas en la forma [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las máquinas no están sincronizadas.  
> 
> [!NOTE]
>  En condiciones de sobrecarga, el tiempo de espera especificado en el **retraso** forma puede producirse más tarde que ha especificado. Esto se debe a la falta de subprocesos en condiciones de sobrecarga.  
  
### <a name="to-configure-a-delay-shape"></a>Para configurar una forma Retraso  
  
1.  Si el Editor de expresiones de BizTalk no está visible, haga clic en el **retraso** dar forma y haga clic en **editar retraso**, o en la ventana Propiedades, haga clic en el **puntos suspensivos** (**...**) botón el **expresión** propiedad.  
  
2.  En el Editor de expresiones de BizTalk, cree una expresión que devuelve un **System.DateTime** objeto o un **System.TimeSpan** objeto. Para obtener más información, consulte [requisitos y limitaciones para expresiones](../core/requirements-and-limitations-for-expressions.md).