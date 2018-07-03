---
title: 'De sesión único: Evento 11049 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b86cf3d5361a912cd976d8a27e83981b71237e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997509"
---
# <a name="single-sign-on-event-11049"></a>De sesión único: Evento 11049
## <a name="details"></a>Detalles  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  Nombre del producto   |                   Inicio de sesión único (SSO) empresarial                    |
| Versión del producto |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    Identificador del evento     |                             11049                              |
|  Origen del evento   |                             ENTSSO                             |
|    Componente    |                              N/D                               |
|  Nombre simbólico  |                      SSO_ERROR_DTC_FAILED                      |
|  Texto del mensaje   | No se pudo obtener MSDTC. SSO necesita MSDTC para funcionar correctamente. |
  
## <a name="explanation"></a>Explicación  
 El sistema ENTSSO no pudo conectarse con Microsoft DTC (Coordinador de transacciones distribuidas).  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si MSDTC se encuentra operativo actualmente.  
  
 Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).