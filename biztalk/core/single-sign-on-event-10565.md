---
title: 'De sesión único: Evento 10565 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d279491-dc0d-44c4-a77e-a67498a3481d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d31b639853b845169c3360ec6367aee120a266d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008005"
---
# <a name="single-sign-on-event-10565"></a>De sesión único: Evento 10565
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                           Inicio de sesión único (SSO) empresarial                                                                                           |
| Versión del producto |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    Identificador del evento     |                                                                                                     10565                                                                                                     |
|  Origen del evento   |                                                                                                    ENTSSO                                                                                                     |
|    Componente    |                                                                                                      N/D                                                                                                      |
|  Nombre simbólico  |                                                                                       SSO_ERROR_SECRET_VALIDATE_FAILED                                                                                        |
|  Texto del mensaje   | No se pudo cargar el secreto desde el Registro. Es posible que se haya cambiado la cuenta de servicio para el servicio SSO o que el secreto esté dañado. Restaure el secreto desde el archivo de copia de seguridad.%r<br /><br /> MSID: %1 |
  
## <a name="explanation"></a>Explicación  
 Es probable que un administrador del sistema haya cambiado la cuenta del servicio SSO, lo que imposibilita el descifrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Busque a la persona que cambió la cuenta del servicio SSO y, después, restaure el secreto desde el archivo de copia de seguridad. Para obtener más información acerca de cómo restaurar el secreto, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).