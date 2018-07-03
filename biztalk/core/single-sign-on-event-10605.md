---
title: 'De sesión único: Evento 10605 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c578462759d2eeb69767d21191e028ef9e8ce1e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972517"
---
# <a name="single-sign-on-event-10605"></a>De sesión único: Evento 10605
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                       Inicio de sesión único (SSO) empresarial                                                                       |
| Versión del producto |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    Identificador del evento     |                                                                                 10605                                                                                 |
|  Origen del evento   |                                                                                ENTSSO                                                                                 |
|    Componente    |                                                                                  N/D                                                                                  |
|  Nombre simbólico  |                                                                         SSO_ERROR_DTC_IMPORT                                                                          |
|  Texto del mensaje   | No se pudo importar una transacción de DTC. Compruebe que MSDTC está correctamente configurado para funcionamiento remoto. Consulte la documentación de details.%r<br /><br /> Código de error: %1 |
  
## <a name="explanation"></a>Explicación  
 Existe un problema con Microsoft DTC (Coordinador de transacciones distribuidas).  
  
## <a name="user-action"></a>Acción del usuario  
 Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).