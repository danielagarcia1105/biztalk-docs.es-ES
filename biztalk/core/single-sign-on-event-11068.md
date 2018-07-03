---
title: 'De sesión único: Evento 11068 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 218da642493981211de4a0e10b504ea8f434945f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020498"
---
# <a name="single-sign-on-event-11068"></a>De sesión único: Evento 11068
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                      Inicio de sesión único (SSO) empresarial                                                                      |
| Versión del producto |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    Identificador del evento     |                                                                                11068                                                                                |
|  Origen del evento   |                                                                               ENTSSO                                                                                |
|    Componente    |                                                                                 N/D                                                                                 |
|  Nombre simbólico  |                                                          SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE                                                          |
|  Texto del mensaje   | Acceso denegado al servidor de búsqueda. Este servidor de SSO actualmente no está configurado para permitir búsqueda remota. Use 'ssoconfig -remoteLookup yes' o la MMC de administración de SSO.%r |
  
## <a name="explanation"></a>Explicación  
 Se denegó el acceso al servidor de búsqueda porque el servidor de ENTSSO no está configurado para permitir búsqueda remota.  
  
## <a name="user-action"></a>Acción del usuario  
 Para permitir búsqueda remota, en el **servidores complemento**, **avanzadas** ficha, seleccione **Permitir búsqueda remota**.  
  
 Para obtener más información, consulte [cómo usar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).