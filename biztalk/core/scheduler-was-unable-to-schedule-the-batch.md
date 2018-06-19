---
title: El programador no pudo programar el lote | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac6d79c-c995-4c95-a4da-ee2f50b9a13a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bef1df18d88f8497fde440383d63bc64eefdd69a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269196"
---
# <a name="scheduler-was-unable-to-schedule-the-batch"></a>El programador no ha podido programar el lote.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|-|  
|Texto del mensaje|El programador no ha podido programar el lote.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el programador no pudo determinar la siguiente repetición de una liberación por lotes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el programa de liberación por lotes es válido:  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y haga clic en **partes**.  
  
3.  Haga clic con el botón secundario en la entidad correcta.  
  
4.  Haga clic en **Propiedades**.  
  
5.  En el [*nombre de la entidad*] **propiedades de la entidad** cuadro de diálogo, en el panel izquierdo, haga clic en **puertos de envío**.  
  
6.  Escriba el nombre de puerto de envío en el **puertos de envío** lista.  
  
7.  Haga clic en **Aceptar**.