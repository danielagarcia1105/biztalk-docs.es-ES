---
title: Errores de tiempo de ejecución de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df75d019b9af36f4ef7fce21ea17dc1e9a8e7aac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999933"
---
# <a name="wcf-run-time-errors"></a>Errores de tiempo de ejecución de WCF
Información para diagnosticar y resolver eventos de tiempo de ejecución de WCF.  
  
## <a name="wcf-service-host-restarted"></a>Se reinició el host del Servicio WCF
  
|                 |                                   Detalles del error                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                       0x1FB0                                       |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                          BTS_I_WCF_SERVICE_HOST_RESTARTED                          |
|  Texto del mensaje   |                                         0                                          |
  
## <a name="explanation"></a>Explicación  
 Este mensaje ofrece una manera para que el adaptador de WCF escriba una entrada de registro de evento "informativo" (las API proporcionadas para los adaptadores permiten la creación de advertencias o errores, no información).  
  
## <a name="user-action"></a>Acción del usuario  
 Si ve este evento informativo en el registro de eventos, indica que la recuperación automática fue correcta. No se necesaria ninguna otra acción en relación a este mensaje.