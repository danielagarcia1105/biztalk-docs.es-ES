---
title: 'De sesión único: Evento 11043 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99faeaefdd029995944033cdb77c6636e716ed5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024546"
---
# <a name="single-sign-on-event-11043"></a>De sesión único: Evento 11043
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                             Inicio de sesión único (SSO) empresarial                                                                                                                                             |
| Versión del producto |                                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                             |
|    Identificador del evento     |                                                                                                                                                       11043                                                                                                                                                       |
|  Origen del evento   |                                                                                                                                                      ENTSSO                                                                                                                                                       |
|    Componente    |                                                                                                                                                        N/D                                                                                                                                                        |
|  Nombre simbólico  |                                                                                                                                       SSO_WARN_PS_ADAPTER_REPORTED_FAILURE                                                                                                                                        |
|  Texto del mensaje   | El adaptador de sincronización de contraseñas informó un error al intentar cambiar la contraseña externa. La contraseña externa no se actualizó en la base de datos de SSO.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta externa: %3 %r<br /><br /> Mensaje de error: %4 %r<br /><br /> Código de error: %5 |
  
## <a name="explanation"></a>Explicación  
 Cuando ENTSSO envía un cambio de contraseña a un adaptador de sincronización de contraseñas, la contraseña externa debe cambiarse correctamente antes de que ENTSSO la cambie en la base de datos de SSO. En este caso, esto no ocurrió.  
  
## <a name="user-action"></a>Acción del usuario  
 Tome nota de la información incluida en el mensaje de advertencia y consulte con el administrador del sistema.