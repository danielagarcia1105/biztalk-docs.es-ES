---
title: 'De sesión único: Evento 10604 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eea14ab1-5a89-4a62-b414-1bcb36ea339e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48996ec333c9035e57393e270db06ca173cfc9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990589"
---
# <a name="single-sign-on-event-10604"></a>De sesión único: Evento 10604
## <a name="details"></a>Detalles  
  
|                 |                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                        Inicio de sesión único (SSO) empresarial                                         |
| Versión del producto |                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                        |
|    Identificador del evento     |                                                  10604                                                   |
|  Origen del evento   |                                                  ENTSSO                                                  |
|    Componente    |                                                   N/D                                                    |
|  Nombre simbólico  |                                      SSO_ERROR_SSOCSTX_OUT_OF_PROC                                       |
|  Texto del mensaje   | La aplicación COM+ "Servidor de ENTSSO" no está configurada correctamente. Debe ser una aplicación de biblioteca COM+. |
  
## <a name="explanation"></a>Explicación  
 La aplicación COM+ debe configurarse como una aplicación de biblioteca COM+.  
  
## <a name="user-action"></a>Acción del usuario  
 En Complemento MMC de ENTSSO, expanda la carpeta COM+ y busque el servidor de ENTSSO. Haga clic con el botón secundario en el servidor y, a continuación, haga clic en Propiedades. En lugar de Aplicación de servidor, seleccione Aplicación de biblioteca y, a continuación, haga clic en Aceptar.