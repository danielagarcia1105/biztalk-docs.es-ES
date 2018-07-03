---
title: 'De sesión único: Evento 10788 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deeb8859-6b2e-452d-a7e5-0cb10de68bd2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1bf8d17abd7fd5652821b998cae34915e7777f2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019669"
---
# <a name="single-sign-on-event-10788"></a>De sesión único: Evento 10788
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                        Inicio de sesión único (SSO) empresarial                                                         |
| Versión del producto |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    Identificador del evento     |                                                                  10788                                                                   |
|  Origen del evento   |                                                                  ENTSSO                                                                  |
|    Componente    |                                                                   N/D                                                                    |
|  Nombre simbólico  |                                                       ENTSSO_E_DTC_IMPORT_FAILED1                                                        |
|  Texto del mensaje   | No se pudo importar una transacción de DTC. Compruebe que MSDTC está correctamente configurado para funcionamiento remoto. Para obtener información detallada, consulte la documentación. |
  
## <a name="explanation"></a>Explicación  
 No se pudo importar una transacción de DTC.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si MSDTC está configurado correctamente para funcionamiento remoto y consulte el registro de eventos en el equipo especificado para obtener información detallada.  
  
 Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).